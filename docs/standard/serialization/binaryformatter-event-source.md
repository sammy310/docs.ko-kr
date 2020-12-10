---
title: BinaryFormatter 이벤트 원본
description: BinaryFormatter 이벤트 원본을 사용하여 직렬화 또는 역직렬화가 발생할 때 기록하는 방법을 알아봅니다.
ms.date: 12/03/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 9ae2af77b6cfc270207fb0f2969ada8c2eca1153
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740393"
---
# <a name="binaryformatter-event-source"></a><span data-ttu-id="e7667-103">BinaryFormatter 이벤트 원본</span><span class="sxs-lookup"><span data-stu-id="e7667-103">BinaryFormatter event source</span></span>

<span data-ttu-id="e7667-104">.NET 5.0부터 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>에는 개체 직렬화 또는 역직렬화가 발생하는 경우에 대한 가시성을 제공하는 기본 제공 <xref:System.Diagnostics.Tracing.EventSource>가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-104">Starting with .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> includes a built-in <xref:System.Diagnostics.Tracing.EventSource> that gives you visibility into when an object serialization or deserialization is occurring.</span></span> <span data-ttu-id="e7667-105">앱은 <xref:System.Diagnostics.Tracing.EventListener> 파생 형식을 사용하여 이러한 알림을 수신하고 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-105">Apps can use <xref:System.Diagnostics.Tracing.EventListener>-derived types to listen for these notifications and log them.</span></span>

<span data-ttu-id="e7667-106">이 기능은 <xref:System.Runtime.Serialization.SerializationBinder> 또는 <xref:System.Runtime.Serialization.ISerializationSurrogate>를 대체하지 않으며, 직렬화되거나 역직렬화되는 데이터를 수정하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-106">This functionality is not a substitute for a <xref:System.Runtime.Serialization.SerializationBinder> or an <xref:System.Runtime.Serialization.ISerializationSurrogate> and can't be used to modify the data being serialized or deserialized.</span></span> <span data-ttu-id="e7667-107">대신 이 이벤트 시스템은 직렬화 또는 역직렬화되는 형식에 대한 인사이트를 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-107">Rather, this eventing system is intended to provide insight into the types being serialized or deserialized.</span></span> <span data-ttu-id="e7667-108">타사 라이브러리 코드에서 발생하는 호출 같이 `BinaryFormatter` 인프라에 대한 의도하지 않은 호출을 검색하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-108">It can also be used to detect unintended calls into the `BinaryFormatter` infrastructure, such as calls originating from third-party library code.</span></span>

## <a name="description-of-events"></a><span data-ttu-id="e7667-109">이벤트 설명</span><span class="sxs-lookup"><span data-stu-id="e7667-109">Description of events</span></span>

<span data-ttu-id="e7667-110">`BinaryFormatter` 이벤트 원본에는 잘 알려진 이름 `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-110">The `BinaryFormatter` event source has the well-known name `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span></span> <span data-ttu-id="e7667-111">수신기는 6개의 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-111">Listeners may subscribe to 6 events.</span></span>

### <a name="serializationstart-event-id--10"></a><span data-ttu-id="e7667-112">SerializationStart 이벤트(id = `10`)</span><span class="sxs-lookup"><span data-stu-id="e7667-112">SerializationStart event (id = `10`)</span></span>

<span data-ttu-id="e7667-113"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>가 호출되고 직렬화 프로세스를 시작한 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-113">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> has been called and has started the serialization process.</span></span> <span data-ttu-id="e7667-114">이 이벤트는 `SerializationEnd` 이벤트와 쌍을 이룹니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-114">This event is paired with the `SerializationEnd` event.</span></span> <span data-ttu-id="e7667-115">개체가 자체 직렬화 루틴 내에서 `BinaryFormatter.Serialize`를 호출하는 경우 `SerializationStart` 이벤트를 재귀적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-115">The `SerializationStart` event can be called recursively if an object calls `BinaryFormatter.Serialize` within its own serialization routine.</span></span>

<span data-ttu-id="e7667-116">이 이벤트에는 페이로드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-116">This event doesn't contain a payload.</span></span>

### <a name="serializationend-event-id--11"></a><span data-ttu-id="e7667-117">SerializationEnd 이벤트(id = `11`)</span><span class="sxs-lookup"><span data-stu-id="e7667-117">SerializationEnd event (id = `11`)</span></span>

<span data-ttu-id="e7667-118">`BinaryFormatter.Serialize`가 작업을 완료했을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-118">Raised when `BinaryFormatter.Serialize` has completed its work.</span></span> <span data-ttu-id="e7667-119">`SerializationEnd`의 각 항목은 짝이 없는 마지막 `SerializationStart` 이벤트의 완료를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-119">Each occurrence of `SerializationEnd` denotes the completion of the last unpaired `SerializationStart` event.</span></span>

<span data-ttu-id="e7667-120">이 이벤트에는 페이로드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-120">This event doesn't contain a payload.</span></span>

### <a name="serializingobject-event-id--12"></a><span data-ttu-id="e7667-121">SerializingObject 이벤트(id = `12`)</span><span class="sxs-lookup"><span data-stu-id="e7667-121">SerializingObject event (id = `12`)</span></span>

<span data-ttu-id="e7667-122">`BinaryFormatter.Serialize`가 기본 형식이 아닌 형식을 직렬화하는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-122">Raised when `BinaryFormatter.Serialize` is in the process of serializing a non-primitive type.</span></span> <span data-ttu-id="e7667-123">`BinaryFormatter` 인프라는 `string` 및 `int`와 같은 특정 형식을 특수 처리하며, 이러한 형식이 발견될 때 이 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-123">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="e7667-124">이 이벤트는 사용자 정의 형식 및 `BinaryFormatter`가 고유하게 이해하지 못하는 다른 형식의 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-124">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="e7667-125">이 이벤트는 `SerializationStart` 이벤트와 `SerializationEnd` 이벤트 사이에서 0번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-125">This event may be raised zero or more times between `SerializationStart` and `SerializationEnd` events.</span></span>

<span data-ttu-id="e7667-126">이 이벤트에는 인수가 하나 있는 페이로드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-126">This event contains a payload with one argument:</span></span>

* <span data-ttu-id="e7667-127">`typeName`(`string`): 직렬화되는 형식의 정규화된 어셈블리 이름(<xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> 참조)입니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-127">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being serialized.</span></span>

### <a name="deserializationstart-event-id--20"></a><span data-ttu-id="e7667-128">DeserializationStart 이벤트(id = `20`)</span><span class="sxs-lookup"><span data-stu-id="e7667-128">DeserializationStart event (id = `20`)</span></span>

<span data-ttu-id="e7667-129"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>가 호출되고 역직렬화 프로세스를 시작한 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-129">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> has been called and has started the deserialization process.</span></span> <span data-ttu-id="e7667-130">이 이벤트는 `DeserializationEnd` 이벤트와 쌍을 이룹니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-130">This event is paired with the `DeserializationEnd` event.</span></span> <span data-ttu-id="e7667-131">개체가 자체 역직렬화 루틴 내에서 `BinaryFormatter.Deserialize`를 호출하는 경우 `DeserializationStart` 이벤트를 재귀적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-131">The `DeserializationStart` event can be called recursively if an object calls `BinaryFormatter.Deserialize` within its own deserialization routine.</span></span>

<span data-ttu-id="e7667-132">이 이벤트에는 페이로드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-132">This event doesn't contain a payload.</span></span>

### <a name="deserializationend-event-id--21"></a><span data-ttu-id="e7667-133">DeserializationEnd 이벤트(id = `21`)</span><span class="sxs-lookup"><span data-stu-id="e7667-133">DeserializationEnd event (id = `21`)</span></span>

<span data-ttu-id="e7667-134">`BinaryFormatter.Deserialize`가 작업을 완료했을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-134">Raised when `BinaryFormatter.Deserialize` has completed its work.</span></span> <span data-ttu-id="e7667-135">`DeserializationEnd`의 각 항목은 짝이 없는 마지막 `DeserializationStart` 이벤트의 완료를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-135">Each occurrence of `DeserializationEnd` denotes the completion of the last unpaired `DeserializationStart` event.</span></span>

<span data-ttu-id="e7667-136">이 이벤트에는 페이로드가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-136">This event doesn't contain a payload.</span></span>

### <a name="deserializingobject-event-id--22"></a><span data-ttu-id="e7667-137">DeserializingObject 이벤트(id = `22`)</span><span class="sxs-lookup"><span data-stu-id="e7667-137">DeserializingObject event (id = `22`)</span></span>

<span data-ttu-id="e7667-138">`BinaryFormatter.Deserialize`가 기본 형식이 아닌 형식을 역직렬화하는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-138">Raised when `BinaryFormatter.Deserialize` is in the process of deserializing a non-primitive type.</span></span> <span data-ttu-id="e7667-139">`BinaryFormatter` 인프라는 `string` 및 `int`와 같은 특정 형식을 특수 처리하며, 이러한 형식이 발견될 때 이 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-139">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="e7667-140">이 이벤트는 사용자 정의 형식 및 `BinaryFormatter`가 고유하게 이해하지 못하는 다른 형식의 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-140">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="e7667-141">이 이벤트는 `DeserializationStart` 이벤트와 `DeserializationEnd` 이벤트 사이에서 0번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-141">This event may be raised zero or more times between `DeserializationStart` and `DeserializationEnd` events.</span></span>

<span data-ttu-id="e7667-142">이 이벤트에는 인수가 하나 있는 페이로드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-142">This event contains a payload with one argument.</span></span>

* <span data-ttu-id="e7667-143">`typeName`(`string`): 역직렬화되는 형식의 정규화된 어셈블리 이름(<xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> 참조)입니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-143">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being deserialized.</span></span>

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a><span data-ttu-id="e7667-144">\[고급\] 알림의 하위 집합 구독</span><span class="sxs-lookup"><span data-stu-id="e7667-144">\[Advanced\] Subscribing to a subset of notifications</span></span>

<span data-ttu-id="e7667-145">알림 하위 집합만 구독하려는 수신기는 사용할 키워드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-145">Listeners who wish to subscribe to only a subset of notifications can choose which keywords to enable.</span></span>

* <span data-ttu-id="e7667-146">`Serialization` = `(EventKeywords)1`: `SerializationStart`, `SerializationEnd` 및 `SerializingObject` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-146">`Serialization` = `(EventKeywords)1`: Raises the `SerializationStart`, `SerializationEnd`, and `SerializingObject` events.</span></span>
* <span data-ttu-id="e7667-147">`Deserialization` = `(EventKeywords)2`: `DeserializationStart`, `DeserializationEnd` 및 `DeserializingObject` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-147">`Deserialization` = `(EventKeywords)2`: Raises the `DeserializationStart`, `DeserializationEnd`, and `DeserializingObject` events.</span></span>

<span data-ttu-id="e7667-148">`EventListener` 등록 중에 키워드 필터를 제공하지 않으면 모든 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-148">If no keyword filters are provided during `EventListener` registration, all events are raised.</span></span>

<span data-ttu-id="e7667-149">자세한 내용은 <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7667-149">For more information, see <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span></span>

## <a name="sample-code"></a><span data-ttu-id="e7667-150">예제 코드</span><span class="sxs-lookup"><span data-stu-id="e7667-150">Sample code</span></span>

<span data-ttu-id="e7667-151">코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-151">The following code:</span></span>

- <span data-ttu-id="e7667-152">`System.Console`에 쓰는 `EventListener` 파생 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-152">creates an `EventListener`-derived type that writes to `System.Console`,</span></span>
- <span data-ttu-id="e7667-153">해당 수신기가 `BinaryFormatter`에서 생성된 알림을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-153">subscribes that listener to `BinaryFormatter`-produced notifications,</span></span>
- <span data-ttu-id="e7667-154">`BinaryFormatter`를 사용하여 단순 개체 그래프를 직렬화 및 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-154">serializes and deserializes a simple object graph using `BinaryFormatter`, and</span></span>
- <span data-ttu-id="e7667-155">발생한 이벤트를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-155">analyzes the events that have been raised.</span></span>

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

<span data-ttu-id="e7667-156">위 코드의 출력은 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-156">The preceding code produces output similar to the following example:</span></span>

```output
Event SerializationStart (id=10) received.
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializationStop (id=11) received.
Event DeserializationStart (id=20) received.
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializationStop (id=21) received.
Rehydrated person Logan Edwards
Favorite book: A Tale of Two Cities by Charles Dickens, list price 10.25
```

<span data-ttu-id="e7667-157">이 샘플에서 콘솔 기반 `EventListener`는 직렬화가 시작되고, `Person` 및 `Book`의 인스턴스가 직렬화된 다음 직렬화가 완료됨을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-157">In this sample, the console-based `EventListener` logs that serialization starts, instances of `Person` and `Book` are serialized, and then serialization completes.</span></span> <span data-ttu-id="e7667-158">마찬가지로 역직렬화가 시작되면 `Person` 및 `Book` 인스턴스가 역직렬화된 다음 역직렬화가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-158">Similarly, once deserialization has started, instances of `Person` and `Book` are deserialized, and then deserialization completes.</span></span>

<span data-ttu-id="e7667-159">그런 다음 앱은 역직렬화된 `Person`에 포함된 값을 출력하여 실제로 개체가 올바로 직렬화 및 역직렬화되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7667-159">The app then prints the values contained in the deserialized `Person` to demonstrate that the object did in fact serialize and deserialize properly.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7667-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7667-160">See also</span></span>

<span data-ttu-id="e7667-161">`EventListener`를 사용하여 `EventSource` 기반 알림을 수신하는 방법에 대한 자세한 내용은 [`EventListener` 클래스](xref:System.Diagnostics.Tracing.EventListener)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7667-161">For more information on using `EventListener` to receive `EventSource`-based notifications, see [the `EventListener` class](xref:System.Diagnostics.Tracing.EventListener).</span></span>
