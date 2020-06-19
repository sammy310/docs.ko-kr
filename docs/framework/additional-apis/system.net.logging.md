---
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
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990474"
---
# <a name="logging-class"></a><span data-ttu-id="cb8f7-102">로깅 클래스</span><span class="sxs-lookup"><span data-stu-id="cb8f7-102">Logging class</span></span>

<span data-ttu-id="cb8f7-103">추적 로깅 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="cb8f7-104">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cb8f7-105">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="cb8f7-106">연결 방법</span><span class="sxs-lookup"><span data-stu-id="cb8f7-106">Associate method</span></span>

<span data-ttu-id="cb8f7-107">두 개체가 서로 연결 된 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-108">Parameters</span></span>

- <span data-ttu-id="cb8f7-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-110">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-112">와 연결할 개체 `objB` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="cb8f7-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-114">와 연결할 개체 `objA` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="cb8f7-115">Enter (TraceSource, object, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="cb8f7-116">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-117">Parameters</span></span>

- <span data-ttu-id="cb8f7-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-119">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-121">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-121">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-123">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-123">The method that is being entered.</span></span>

- <span data-ttu-id="cb8f7-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-125">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="cb8f7-126">Enter (TraceSource, object, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="cb8f7-127">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-128">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-128">Parameters</span></span>

- <span data-ttu-id="cb8f7-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-130">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-132">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-132">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-134">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-134">The method that is being entered.</span></span>

- <span data-ttu-id="cb8f7-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-136">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="cb8f7-137">Enter (TraceSource, string, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="cb8f7-138">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-139">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-139">Parameters</span></span>

- <span data-ttu-id="cb8f7-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-141">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-143">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-143">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-145">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-145">The method that is being entered.</span></span>

- <span data-ttu-id="cb8f7-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-147">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="cb8f7-148">Enter (TraceSource, string, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="cb8f7-149">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-150">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-150">Parameters</span></span>

- <span data-ttu-id="cb8f7-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-152">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-154">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-154">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-156">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-156">The method that is being entered.</span></span>

- <span data-ttu-id="cb8f7-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-158">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="cb8f7-159">Enter (TraceSource, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="cb8f7-160">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-161">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-161">Parameters</span></span>

- <span data-ttu-id="cb8f7-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-163">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-165">입력 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-165">The method that is being entered.</span></span>

- <span data-ttu-id="cb8f7-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-167">메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="cb8f7-168">Enter (TraceSource, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="cb8f7-169">메서드에 대 한 로그를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-170">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-170">Parameters</span></span>

- <span data-ttu-id="cb8f7-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-172">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-174">추적 소스에 기록할 입구 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="cb8f7-175">Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-175">Exception method</span></span>

<span data-ttu-id="cb8f7-176">예외를 기록 하 고 들여쓰기를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-177">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-177">Parameters</span></span>

- <span data-ttu-id="cb8f7-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-179">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-181">예외를 throw 한 메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="cb8f7-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-183">예외를 throw 한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-183">The method that threw the exception.</span></span>

- <span data-ttu-id="cb8f7-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="cb8f7-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="cb8f7-185">throw된 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="cb8f7-186">Exit (TraceSource, object, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="cb8f7-187">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-188">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-188">Parameters</span></span>

- <span data-ttu-id="cb8f7-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-190">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-192">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-192">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-194">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-194">The method that is being exited.</span></span>

- <span data-ttu-id="cb8f7-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-196">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="cb8f7-197">Exit (TraceSource, string, string, object) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="cb8f7-198">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-199">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-199">Parameters</span></span>

- <span data-ttu-id="cb8f7-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-201">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-203">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-203">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-205">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-205">The method that is being exited.</span></span>

- <span data-ttu-id="cb8f7-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-207">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="cb8f7-208">Exit (TraceSource, object, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="cb8f7-209">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-210">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-210">Parameters</span></span>

- <span data-ttu-id="cb8f7-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-212">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="cb8f7-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="cb8f7-214">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-214">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-216">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-216">The method that is being exited.</span></span>

- <span data-ttu-id="cb8f7-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-218">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="cb8f7-219">Exit (TraceSource, string, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="cb8f7-220">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-221">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-221">Parameters</span></span>

- <span data-ttu-id="cb8f7-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-223">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-225">메서드가 호출 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-225">The object that the method was called on.</span></span>

- <span data-ttu-id="cb8f7-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-227">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-227">The method that is being exited.</span></span>

- <span data-ttu-id="cb8f7-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-229">메서드가 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="cb8f7-230">Exit (TraceSource, string, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="cb8f7-231">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-232">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-232">Parameters</span></span>

- <span data-ttu-id="cb8f7-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-234">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-236">종료 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-236">The method that is being exited.</span></span>

- <span data-ttu-id="cb8f7-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-238">종료 되는 메서드에 전달 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="cb8f7-239">Exit (TraceSource, string) 메서드</span><span class="sxs-lookup"><span data-stu-id="cb8f7-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="cb8f7-240">함수에서 로그를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="cb8f7-241">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb8f7-241">Parameters</span></span>

- <span data-ttu-id="cb8f7-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="cb8f7-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="cb8f7-243">이벤트를 로깅할 추적 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="cb8f7-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cb8f7-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="cb8f7-245">추적 소스에 기록할 종료 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="cb8f7-246">Http 속성</span><span class="sxs-lookup"><span data-stu-id="cb8f7-246">Http property</span></span>

<span data-ttu-id="cb8f7-247">"System .Net. Http"의 추적 소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="cb8f7-248">속성 값</span><span class="sxs-lookup"><span data-stu-id="cb8f7-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="cb8f7-249">"System .Net. Http"의 추적 소스 이거나, `null` 로깅을 사용할 수 없으면입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="cb8f7-250">On 속성</span><span class="sxs-lookup"><span data-stu-id="cb8f7-250">On property</span></span>

<span data-ttu-id="cb8f7-251">로깅을 사용할 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="cb8f7-252">속성 값</span><span class="sxs-lookup"><span data-stu-id="cb8f7-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="cb8f7-253">로깅을 사용할 수 있으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb8f7-254">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb8f7-254">Requirements</span></span>

<span data-ttu-id="cb8f7-255">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="cb8f7-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="cb8f7-256">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="cb8f7-256">**Assembly:** System (in System.dll)</span></span>
