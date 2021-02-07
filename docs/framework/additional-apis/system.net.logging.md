---
description: '자세한 정보: 로깅 클래스'
title: Logging 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 1ae3079ab21502ee3f5bf71db57f0695da9a8571
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726210"
---
# <a name="logging-class"></a><span data-ttu-id="a4869-103">Logging 클래스</span><span class="sxs-lookup"><span data-stu-id="a4869-103">Logging class</span></span>

<span data-ttu-id="a4869-104">추적 로깅 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-104">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="a4869-105">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a4869-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="a4869-107">연결 방법</span><span class="sxs-lookup"><span data-stu-id="a4869-107">Associate method</span></span>

<span data-ttu-id="a4869-108">두 개체가 서로 연결 된 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-108">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="a4869-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-109">Parameters</span></span>

- <span data-ttu-id="a4869-110">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-110">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-111">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-111">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-112">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-112">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-113">와 연결할 개체 `objB` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-113">The object to associate with `objB`.</span></span>

- <span data-ttu-id="a4869-114">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-114">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-115">와 연결할 개체 `objA` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-115">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="a4869-116">Enter (TraceSource, object, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-116">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="a4869-117">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-117">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="a4869-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-118">Parameters</span></span>

- <span data-ttu-id="a4869-119">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-119">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-120">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-120">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-121">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-121">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-122">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-122">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-123">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-123">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-124">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-124">The method that is being entered.</span></span>

- <span data-ttu-id="a4869-125">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-125">`param` <xref:System.String></span></span>

  <span data-ttu-id="a4869-126">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-126">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="a4869-127">Enter (TraceSource, object, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-127">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="a4869-128">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-128">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="a4869-129">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-129">Parameters</span></span>

- <span data-ttu-id="a4869-130">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-130">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-131">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-131">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-132">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-132">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-133">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-133">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-134">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-134">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-135">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-135">The method that is being entered.</span></span>

- <span data-ttu-id="a4869-136">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-136">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-137">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-137">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="a4869-138">Enter (TraceSource, string, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-138">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="a4869-139">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-139">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="a4869-140">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-140">Parameters</span></span>

- <span data-ttu-id="a4869-141">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-141">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-142">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-142">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-143">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-143">`obj` <xref:System.String></span></span>

  <span data-ttu-id="a4869-144">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-144">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-145">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-145">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-146">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-146">The method that is being entered.</span></span>

- <span data-ttu-id="a4869-147">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-147">`param` <xref:System.String></span></span>

  <span data-ttu-id="a4869-148">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-148">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="a4869-149">Enter (TraceSource, string, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-149">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="a4869-150">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-150">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="a4869-151">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-151">Parameters</span></span>

- <span data-ttu-id="a4869-152">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-152">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-153">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-153">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-154">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-154">`obj` <xref:System.String></span></span>

  <span data-ttu-id="a4869-155">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-155">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-156">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-156">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-157">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-157">The method that is being entered.</span></span>

- <span data-ttu-id="a4869-158">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-158">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-159">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-159">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="a4869-160">Enter (TraceSource, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-160">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="a4869-161">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-161">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="a4869-162">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-162">Parameters</span></span>

- <span data-ttu-id="a4869-163">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-163">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-164">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-164">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-165">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-165">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-166">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-166">The method that is being entered.</span></span>

- <span data-ttu-id="a4869-167">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-167">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="a4869-168">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-168">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="a4869-169">Enter (TraceSource, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-169">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="a4869-170">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-170">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="a4869-171">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-171">Parameters</span></span>

- <span data-ttu-id="a4869-172">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-172">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-173">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-173">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-174">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-174">`msg` <xref:System.String></span></span>

  <span data-ttu-id="a4869-175">추적 소스에 기록할 입구 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-175">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="a4869-176">Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-176">Exception method</span></span>

<span data-ttu-id="a4869-177">예외를 기록 하 고 들여쓰기를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-177">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="a4869-178">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-178">Parameters</span></span>

- <span data-ttu-id="a4869-179">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-179">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-180">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-180">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-181">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-181">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-182">예외를 throw 한 메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-182">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="a4869-183">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-183">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-184">예외를 throw 한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-184">The method that threw the exception.</span></span>

- <span data-ttu-id="a4869-185">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="a4869-185">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="a4869-186">throw된 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-186">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="a4869-187">Exit (TraceSource, object, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-187">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="a4869-188">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-188">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="a4869-189">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-189">Parameters</span></span>

- <span data-ttu-id="a4869-190">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-190">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-191">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-191">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-192">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-192">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-193">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-193">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-194">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-194">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-195">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-195">The method that is being exited.</span></span>

- <span data-ttu-id="a4869-196">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-196">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-197">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-197">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="a4869-198">Exit (TraceSource, string, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-198">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="a4869-199">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-199">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="a4869-200">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-200">Parameters</span></span>

- <span data-ttu-id="a4869-201">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-201">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-202">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-202">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-203">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-203">`obj` <xref:System.String></span></span>

  <span data-ttu-id="a4869-204">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-204">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-205">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-205">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-206">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-206">The method that is being exited.</span></span>

- <span data-ttu-id="a4869-207">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-207">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-208">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-208">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="a4869-209">Exit (TraceSource, object, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-209">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="a4869-210">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-210">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="a4869-211">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-211">Parameters</span></span>

- <span data-ttu-id="a4869-212">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-212">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-213">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-213">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-214">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="a4869-214">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="a4869-215">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-215">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-216">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-216">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-217">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-217">The method that is being exited.</span></span>

- <span data-ttu-id="a4869-218">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-218">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="a4869-219">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-219">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="a4869-220">Exit (TraceSource, string, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-220">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="a4869-221">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-221">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="a4869-222">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-222">Parameters</span></span>

- <span data-ttu-id="a4869-223">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-223">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-224">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-224">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-225">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-225">`obj` <xref:System.String></span></span>

  <span data-ttu-id="a4869-226">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-226">The object that the method was called on.</span></span>

- <span data-ttu-id="a4869-227">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-227">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-228">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-228">The method that is being exited.</span></span>

- <span data-ttu-id="a4869-229">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-229">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="a4869-230">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-230">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="a4869-231">Exit (TraceSource, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-231">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="a4869-232">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-232">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="a4869-233">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-233">Parameters</span></span>

- <span data-ttu-id="a4869-234">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-234">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-235">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-235">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-236">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-236">`method` <xref:System.String></span></span>

  <span data-ttu-id="a4869-237">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-237">The method that is being exited.</span></span>

- <span data-ttu-id="a4869-238">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-238">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="a4869-239">종료 되는 메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-239">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="a4869-240">Exit (TraceSource, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="a4869-240">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="a4869-241">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-241">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="a4869-242">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4869-242">Parameters</span></span>

- <span data-ttu-id="a4869-243">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="a4869-243">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="a4869-244">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-244">The trace source to log the event to.</span></span>

- <span data-ttu-id="a4869-245">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a4869-245">`msg` <xref:System.String></span></span>

  <span data-ttu-id="a4869-246">추적 소스에 기록할 종료 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-246">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="a4869-247">Http 속성</span><span class="sxs-lookup"><span data-stu-id="a4869-247">Http property</span></span>

<span data-ttu-id="a4869-248">"System .Net. Http"의 추적 소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-248">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="a4869-249">속성 값</span><span class="sxs-lookup"><span data-stu-id="a4869-249">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="a4869-250">"System .Net. Http"의 추적 소스 이거나, `null` 로깅을 사용할 수 없으면입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-250">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="a4869-251">On 속성</span><span class="sxs-lookup"><span data-stu-id="a4869-251">On property</span></span>

<span data-ttu-id="a4869-252">로깅을 사용할 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-252">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="a4869-253">속성 값</span><span class="sxs-lookup"><span data-stu-id="a4869-253">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="a4869-254">로깅을 사용할 수 있으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4869-254">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4869-255">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4869-255">Requirements</span></span>

<span data-ttu-id="a4869-256">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a4869-256">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a4869-257">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a4869-257">**Assembly:** System (in System.dll)</span></span>
