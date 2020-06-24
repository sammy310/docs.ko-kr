---
title: 데이터 계약 알려진 형식
description: 데이터 계약 모델에서 KnownTypeAttribute 클래스를 사용 하 여 WCF에서 deserialization 하는 동안 포함할 형식을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
ms.openlocfilehash: 52b0caaaac976893dcf5ef5c228ccc4f53bdbe9e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247483"
---
# <a name="data-contract-known-types"></a><span data-ttu-id="d7cfd-103">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="d7cfd-103">Data Contract Known Types</span></span>
<span data-ttu-id="d7cfd-104"><xref:System.Runtime.Serialization.KnownTypeAttribute> 클래스를 사용하면 고려 사항에 포함해야 하는 형식을 deserialization을 수행하는 동안 미리 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-104">The <xref:System.Runtime.Serialization.KnownTypeAttribute> class allows you to specify, in advance, the types that should be included for consideration during deserialization.</span></span> <span data-ttu-id="d7cfd-105">작업 예제는 [Known Types](../samples/known-types.md) 예제를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-105">For a working example, see the [Known Types](../samples/known-types.md) example.</span></span>  
  
 <span data-ttu-id="d7cfd-106">일반적으로 클라이언트와 서비스 간에 매개 변수와 반환 값을 전달할 때 두 엔드포인트는 전송할 데이터의 모든 데이터 계약을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-106">Normally, when passing parameters and return values between a client and a service, both endpoints share all of the data contracts of the data to be transmitted.</span></span> <span data-ttu-id="d7cfd-107">그러나 다음과 같은 경우는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-107">However, this is not the case in the following circumstances:</span></span>  
  
- <span data-ttu-id="d7cfd-108">보낸 데이터 계약은 필요한 데이터 계약에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-108">The sent data contract is derived from the expected data contract.</span></span> <span data-ttu-id="d7cfd-109">자세한 내용은 [데이터 계약 동등성](data-contract-equivalence.md)의 상속에 대 한 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-109">For more information, see the section about inheritance in [Data Contract Equivalence](data-contract-equivalence.md)).</span></span> <span data-ttu-id="d7cfd-110">이 경우 전송한 데이터에는 수신하는 엔드포인트에서 필요한 것과 동일한 데이터 계약이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-110">In that case, the transmitted data does not have the same data contract as expected by the receiving endpoint.</span></span>  
  
- <span data-ttu-id="d7cfd-111">전송할 정보에 대해 선언된 형식은 클래스, 구조체 또는 열거형이 아니라 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-111">The declared type for the information to be transmitted is an interface, as opposed to a class, structure, or enumeration.</span></span> <span data-ttu-id="d7cfd-112">따라서 인터페이스를 구현하는 형식을 실제로 보냈는지 미리 알 수 없으므로 수신하는 엔드포인트에서 전송된 데이터에 대한 데이터 계약을 미리 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-112">Therefore, it cannot be known in advance which type that implements the interface is actually sent and therefore, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span>  
  
- <span data-ttu-id="d7cfd-113">전송할 정보에 대해 선언된 형식은 <xref:System.Object>입니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-113">The declared type for the information to be transmitted is <xref:System.Object>.</span></span> <span data-ttu-id="d7cfd-114">모든 형식은 <xref:System.Object>에서 상속되며 실제로 보낸 형식을 미리 알 수 없으므로 수신하는 엔드포인트에서 전송된 데이터에 대한 데이터 계약을 미리 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-114">Because every type inherits from <xref:System.Object>, and it cannot be known in advance which type is actually sent, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span> <span data-ttu-id="d7cfd-115">이것은 첫 번째 항목의 특별한 경우입니다. 모든 데이터 계약은 <xref:System.Object>에 대해 생성되는 빈 데이터 계약인 기본값에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-115">This is a special case of the first item: Every data contract derives from the default, a blank data contract that is generated for <xref:System.Object>.</span></span>  
  
- <span data-ttu-id="d7cfd-116">.NET Framework 형식을 포함 하는 일부 형식에는 앞의 세 범주 중 하나에 있는 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-116">Some types, which include .NET Framework types, have members that are in one of the preceding three categories.</span></span> <span data-ttu-id="d7cfd-117">예를 들어 <xref:System.Collections.Hashtable> 은 <xref:System.Object> 를 사용하여 해시 테이블에 실제 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-117">For example, <xref:System.Collections.Hashtable> uses <xref:System.Object> to store the actual objects in the hash table.</span></span> <span data-ttu-id="d7cfd-118">이러한 형식을 serialize할 때 받는 쪽에서 이러한 멤버에 대한 데이터 계약을 미리 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-118">When serializing these types, the receiving side cannot determine in advance the data contract for these members.</span></span>  
  
## <a name="the-knowntypeattribute-class"></a><span data-ttu-id="d7cfd-119">KnownTypeAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="d7cfd-119">The KnownTypeAttribute Class</span></span>  
 <span data-ttu-id="d7cfd-120">데이터가 수신 끝점에 도착 하면 WCF 런타임에서는 CLR (공용 언어 런타임) 형식의 인스턴스로 데이터를 deserialize 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-120">When data arrives at a receiving endpoint, the WCF runtime attempts to deserialize the data into an instance of a common language runtime (CLR) type.</span></span> <span data-ttu-id="d7cfd-121">deserialization을 위해 인스턴스화되는 형식은 메시지 내용이 따르는 데이터 계약을 확인하도록 들어오는 메시지를 먼저 검사하여 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-121">The type that is instantiated for deserialization is chosen by first inspecting the incoming message to determine the data contract to which the contents of the message conform.</span></span> <span data-ttu-id="d7cfd-122">그런 다음 deserialization 엔진은 메시지 내용과 호환되는 데이터 계약을 구현하는 CLR 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-122">The deserialization engine then attempts to find a CLR type that implements a data contract compatible with the message contents.</span></span> <span data-ttu-id="d7cfd-123">이 프로세스 중에 역직렬화 엔진에서 허용하는 후보 형식 집합을 역직렬 변환기의 "알려진 형식" 집합이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-123">The set of candidate types that the deserialization engine allows for during this process is referred to as the deserializer's set of "known types."</span></span>  
  
 <span data-ttu-id="d7cfd-124">deserialization 엔진에 형식을 알리는 한 가지 방법은 <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-124">One way to let the deserialization engine know about a type is by using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="d7cfd-125">특성은 개별 데이터 멤버에 적용될 수 없고 전체 데이터 계약 형식에만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-125">The attribute cannot be applied to individual data members, only to whole data contract types.</span></span> <span data-ttu-id="d7cfd-126">특성은 클래스 또는 구조체일 수 있는 *외부 형식* 에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-126">The attribute is applied to an *outer type* that can be a class or a structure.</span></span> <span data-ttu-id="d7cfd-127">가장 기본적인 사용법에서 특성을 적용하면 형식이 "알려진 형식"으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-127">In its most basic usage, applying the attribute specifies a type as a "known type."</span></span> <span data-ttu-id="d7cfd-128">이렇게 하면 외부 형식의 개체 또는 해당 멤버를 통해 참조되는 개체가 역직렬화될 때마다 알려진 형식이 알려진 형식 집합의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-128">This causes the known type to be a part of the set of known types whenever an object of the outer type or any object referred to through its members is being deserialized.</span></span> <span data-ttu-id="d7cfd-129">두 개 이상의 <xref:System.Runtime.Serialization.KnownTypeAttribute> 특성을 같은 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-129">More than one <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute can be applied to the same type.</span></span>  
  
## <a name="known-types-and-primitives"></a><span data-ttu-id="d7cfd-130">알려진 형식 및 기본 형식</span><span class="sxs-lookup"><span data-stu-id="d7cfd-130">Known Types and Primitives</span></span>  
 <span data-ttu-id="d7cfd-131">기본 형식과 기본 형식으로 처리되는 특정 형식(예: <xref:System.DateTime> 및 <xref:System.Xml.XmlElement>)은 항상 "알려진" 형식이므로 이 메커니즘을 통해 추가되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-131">Primitive types, as well as certain types treated as primitives (for example, <xref:System.DateTime> and <xref:System.Xml.XmlElement>) are always "known" and never have to be added through this mechanism.</span></span> <span data-ttu-id="d7cfd-132">그러나 기본 형식 배열은 명시적으로 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-132">However, arrays of primitive types have to be added explicitly.</span></span> <span data-ttu-id="d7cfd-133">대부분의 컬렉션은 배열과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-133">Most collections are considered equivalent to arrays.</span></span> <span data-ttu-id="d7cfd-134">제네릭이 아닌 컬렉션은 <xref:System.Object>의 배열과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-134">(Non-generic collections are considered equivalent to arrays of <xref:System.Object>).</span></span> <span data-ttu-id="d7cfd-135">기본 형식, 기본 배열 및 기본 컬렉션 사용 예제는 예제 4를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-135">For an example of the using primitives, primitive arrays, and primitive collections, see Example 4.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7cfd-136">다른 기본 형식과 달리 <xref:System.DateTimeOffset> 구조체는 기본적으로 알려진 형식이 아니므로 이 형식을 알려진 형식 목록에 수동으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-136">Unlike other primitive types, the <xref:System.DateTimeOffset> structure is not a known type by default, so it must be manually added to the list of known types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d7cfd-137">예제</span><span class="sxs-lookup"><span data-stu-id="d7cfd-137">Examples</span></span>  
 <span data-ttu-id="d7cfd-138">다음 예제에서는 사용 중인 <xref:System.Runtime.Serialization.KnownTypeAttribute> 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-138">The following examples show the <xref:System.Runtime.Serialization.KnownTypeAttribute> class in use.</span></span>  
  
#### <a name="example-1"></a><span data-ttu-id="d7cfd-139">예 1</span><span class="sxs-lookup"><span data-stu-id="d7cfd-139">Example 1</span></span>  
 <span data-ttu-id="d7cfd-140">상속 관계가 있는 세 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-140">There are three classes with an inheritance relationship.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 <span data-ttu-id="d7cfd-141">`CompanyLogo` 멤버가 `ShapeOfLogo` 또는 `CircleType` 개체로 설정된 경우 역직렬화 엔진이 데이터 계약 이름 "Circle" 또는 "Triangle"을 포함하는 형식을 인식하지 않으므로 다음 `TriangleType` 클래스를 직렬화할 수 있지만 역직렬화할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-141">The following `CompanyLogo` class can be serialized, but cannot be deserialized if the `ShapeOfLogo` member is set to either a `CircleType` or a `TriangleType` object, because the deserialization engine does not recognize any types with data contract names "Circle" or "Triangle."</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 <span data-ttu-id="d7cfd-142">`CompanyLogo` 형식을 쓰는 올바른 방법은 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-142">The correct way to write the `CompanyLogo` type is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 <span data-ttu-id="d7cfd-143">외부 형식 `CompanyLogo2` 가 역직렬화될 때마다 역직렬화 엔진이 `CircleType` 및 `TriangleType` 에 대해 알고 있으므로, "Circle" 및 "Triangle" 데이터 계약에 일치하는 형식을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-143">Whenever the outer type `CompanyLogo2` is being deserialized, the deserialization engine knows about `CircleType` and `TriangleType` and, therefore, is able to find matching types for the "Circle" and "Triangle" data contracts.</span></span>  
  
#### <a name="example-2"></a><span data-ttu-id="d7cfd-144">예제 2</span><span class="sxs-lookup"><span data-stu-id="d7cfd-144">Example 2</span></span>  
 <span data-ttu-id="d7cfd-145">다음 예제에서 `CustomerTypeA` 및 `CustomerTypeB` 에 모두 `Customer` 데이터 계약이 있어도 `CustomerTypeB` 만 역직렬화 엔진에 알려지므로 `PurchaseOrder` 가 역직렬화될 때마다 `CustomerTypeB` 의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-145">In the following example, even though both `CustomerTypeA` and `CustomerTypeB` have the `Customer` data contract, an instance of `CustomerTypeB` is created whenever a `PurchaseOrder` is deserialized, because only `CustomerTypeB` is known to the deserialization engine.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a><span data-ttu-id="d7cfd-146">예제 3</span><span class="sxs-lookup"><span data-stu-id="d7cfd-146">Example 3</span></span>  
 <span data-ttu-id="d7cfd-147">다음 예제에서 <xref:System.Collections.Hashtable> 은 해당 콘텐츠를 내부적으로 <xref:System.Object>로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-147">In the following example, a <xref:System.Collections.Hashtable> stores its contents internally as <xref:System.Object>.</span></span> <span data-ttu-id="d7cfd-148">해시 테이블을 성공적으로 역직렬화하려면 역직렬화 엔진이 해시 테이블에서 발생할 수 있는 가능한 형식 집합을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-148">To successfully deserialize a hash table, the deserialization engine must know the set of possible types that can occur there.</span></span> <span data-ttu-id="d7cfd-149">이 경우 `Book` 및 `Magazine` 개체만 `Catalog`에 저장되므로 이러한 개체가 <xref:System.Runtime.Serialization.KnownTypeAttribute> 특성을 사용하여 추가된다는 것을 미리 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-149">In this case, we know in advance that only `Book` and `Magazine` objects are stored in the `Catalog`, so those are added using the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a><span data-ttu-id="d7cfd-150">예제 4</span><span class="sxs-lookup"><span data-stu-id="d7cfd-150">Example 4</span></span>  
 <span data-ttu-id="d7cfd-151">다음 예제에서 데이터 계약은 숫자와 숫자에 수행할 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-151">In the following example, a data contract stores a number and an operation to perform on the number.</span></span> <span data-ttu-id="d7cfd-152">`Numbers` 데이터 멤버는 정수, 정수 배열 또는 정수를 포함하는 <xref:System.Collections.Generic.List%601> 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-152">The `Numbers` data member can be an integer, an array of integers, or a <xref:System.Collections.Generic.List%601> that contains integers.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="d7cfd-153">이는 SVCUTIL.EXE를 사용하여 WCF 프록시를 생성하는 경우 클라이언트 쪽에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-153">This will only work on the client side if SVCUTIL.EXE is used to generate a WCF proxy.</span></span> <span data-ttu-id="d7cfd-154">SVCUTIL.EXE는 서비스에서 알려진 형식을 비롯한 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-154">SVCUTIL.EXE retrieves metadata from the service including any known types.</span></span> <span data-ttu-id="d7cfd-155">이 정보가 없으면 클라이언트가 형식을 역직렬화할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-155">Without this information a client will not be able to deserialize the types.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 <span data-ttu-id="d7cfd-156">이것은 애플리케이션 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-156">This is the application code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a><span data-ttu-id="d7cfd-157">알려진 형식, 상속 및 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7cfd-157">Known Types, Inheritance, and Interfaces</span></span>  
 <span data-ttu-id="d7cfd-158">알려진 형식이 `KnownTypeAttribute` 특성을 사용하여 특정 형식과 연결되면 이 알려진 형식은 해당 형식의 모든 파생 형식과도 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-158">When a known type is associated with a particular type using the `KnownTypeAttribute` attribute, the known type is also associated with all of the derived types of that type.</span></span> <span data-ttu-id="d7cfd-159">예를 들어 다음과 같은 코드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-159">For example, see the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 <span data-ttu-id="d7cfd-160">`DoubleDrawing` 필드에서 `KnownTypeAttribute` 및 `Square` 을 사용할 `Circle` 특성이 기본 클래스( `AdditionalShape` )에 이미 적용되었기 때문에`Drawing`클래스에는 이러한 특성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-160">The `DoubleDrawing` class does not require the `KnownTypeAttribute` attribute to use `Square` and `Circle` in the `AdditionalShape` field, because the base class (`Drawing`) already has these attributes applied.</span></span>  
  
 <span data-ttu-id="d7cfd-161">알려진 형식은 인터페이스가 아닌 클래스와 구조체에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-161">Known types can be associated only with classes and structures, not interfaces.</span></span>  
  
## <a name="known-types-using-open-generic-methods"></a><span data-ttu-id="d7cfd-162">개방형 제네릭 메서드를 사용한 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="d7cfd-162">Known Types Using Open Generic Methods</span></span>  
 <span data-ttu-id="d7cfd-163">제네릭 형식을 알려진 형식으로 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-163">It may be necessary to add a generic type as a known type.</span></span> <span data-ttu-id="d7cfd-164">하지만 개방형 제네릭 형식은 `KnownTypeAttribute` 특성에 대한 매개 변수로 전달될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-164">However, an open generic type cannot be passed as a parameter to the `KnownTypeAttribute` attribute.</span></span>  
  
 <span data-ttu-id="d7cfd-165">이 문제는 대체 메커니즘을 사용하여 해결할 수 있습니다. 알려진 형식 컬렉션에 추가할 형식 목록을 반환하는 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-165">This problem can be solved by using an alternative mechanism: Write a method that returns a list of types to add to the known types collection.</span></span> <span data-ttu-id="d7cfd-166">그런 다음 몇 가지 제한 사항으로 인해 이 메서드 이름이 `KnownTypeAttribute` 특성에 대한 문자열 인수로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-166">The name of the method is then specified as a string argument to the `KnownTypeAttribute` attribute due to some restrictions.</span></span>  
  
 <span data-ttu-id="d7cfd-167">이 메서드는 `KnownTypeAttribute` 특성이 적용되는 형식에 있어야 하고, static 메서드여야 하며, 매개 변수를 취하지 않아야 하고, <xref:System.Collections.IEnumerable> 의 <xref:System.Type>에 할당될 수 있는 개체를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-167">The method must exist on the type to which the `KnownTypeAttribute` attribute is applied, must be static, must accept no parameters, and must return an object that can be assigned to <xref:System.Collections.IEnumerable> of <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="d7cfd-168">`KnownTypeAttribute` 특성을 메서드 이름과 결합하거나 `KnownTypeAttribute` 특성을 같은 형식의 실제 형식과 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-168">You cannot combine the `KnownTypeAttribute` attribute with a method name and `KnownTypeAttribute` attributes with actual types on the same type.</span></span> <span data-ttu-id="d7cfd-169">또한 메서드 이름이 있는 두 개 이상의 `KnownTypeAttribute` 를 같은 형식에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-169">Furthermore, you cannot apply more than one `KnownTypeAttribute` with a method name to the same type.</span></span>  
  
 <span data-ttu-id="d7cfd-170">다음 클래스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-170">See the following class.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 <span data-ttu-id="d7cfd-171">`theDrawing` 필드에는 제네릭 클래스 `ColorDrawing` 과 제네릭 클래스 `BlackAndWhiteDrawing`의 인스턴스가 포함되어 있으며, 모두 제네릭 클래스 `Drawing`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-171">The `theDrawing` field contains instances of a generic class `ColorDrawing` and a generic class `BlackAndWhiteDrawing`, both of which inherit from a generic class `Drawing`.</span></span> <span data-ttu-id="d7cfd-172">일반적으로 두 클래스 모두 알려진 형식에 추가해야 하지만 다음 예제는 올바른 특성 구문이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-172">Normally, both must be added to known types, but the following is not valid syntax for attributes.</span></span>  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 <span data-ttu-id="d7cfd-173">그러므로 이러한 형식을 반환할 메서드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-173">Thus, a method must be created to return these types.</span></span> <span data-ttu-id="d7cfd-174">이 형식을 쓰는 올바른 방법은 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-174">The correct way to write this type, then, is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a><span data-ttu-id="d7cfd-175">알려진 형식을 추가하는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="d7cfd-175">Additional Ways to Add Known Types</span></span>  
 <span data-ttu-id="d7cfd-176">또한 구성 파일을 통해 알려진 형식을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-176">Additionally, known types can be added through a configuration file.</span></span> <span data-ttu-id="d7cfd-177">이는 WCF (Windows Communication Foundation)에서 타사 형식 라이브러리를 사용 하는 경우와 같이 적절 한 deserialization에 알려진 형식이 필요한 형식을 제어 하지 않을 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-177">This is useful when you do not control the type that requires known types for proper deserialization, such as when using third-party type libraries with Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="d7cfd-178">다음 구성 파일에서는 구성 파일에 알려진 형식을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-178">The following configuration file shows how to specify a known type in a configuration file.</span></span>  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 <span data-ttu-id="d7cfd-179">앞의 구성 파일에서는 `MyCompany.Library.Shape` 라는 데이터 계약 형식이 `MyCompany.Library.Circle` 을 알려진 형식으로 포함하도록 선언되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7cfd-179">In the preceding configuration file a data contract type called `MyCompany.Library.Shape` is declared to have `MyCompany.Library.Circle` as a known type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cfd-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7cfd-180">See also</span></span>

- <xref:System.Runtime.Serialization.KnownTypeAttribute>
- <xref:System.Collections.Hashtable>
- <xref:System.Object>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>
- [<span data-ttu-id="d7cfd-181">알려진 유형</span><span class="sxs-lookup"><span data-stu-id="d7cfd-181">Known Types</span></span>](../samples/known-types.md)
- [<span data-ttu-id="d7cfd-182">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="d7cfd-182">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="d7cfd-183">서비스 계약 디자인</span><span class="sxs-lookup"><span data-stu-id="d7cfd-183">Designing Service Contracts</span></span>](../designing-service-contracts.md)
