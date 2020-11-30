---
title: 관리되는 스레딩을 구현하는 최선의 방법
description: .NET의 관리형 스레딩 모범 사례를 알아봅니다. 많은 스레드를 조정하거나 스레드 차단을 처리하는 등의 상황을 해결합니다.
ms.date: 10/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET], design guidelines
- threading [.NET], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: 88cbf266d15a10ff7c56e07a30161e0a800989d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708051"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="fdc88-104">관리 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="fdc88-104">Managed threading best practices</span></span>

<span data-ttu-id="fdc88-105">다중 스레딩에는 신중한 프로그래밍이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-105">Multithreading requires careful programming.</span></span> <span data-ttu-id="fdc88-106">대부분의 작업의 경우 스레드 풀 스레드로 실행에 대한 요청을 큐에 대기시켜 복잡성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-106">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="fdc88-107">이 항목에서는 다중 스레드의 작업 조정 또는 차단되는 스레드 처리 등의 더욱 어려운 상황을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-107">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdc88-108">.NET Framework 4부터 작업 병렬 라이브러리 및 PLINQ는 다중 스레드 프로그래밍의 일부 복잡성 및 위험을 줄여주는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-108">Starting with .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="fdc88-109">자세한 내용은 [.NET의 병렬 프로그래밍](../parallel-programming/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-109">For more information, see [Parallel Programming in .NET](../parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="fdc88-110">교착 상태 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="fdc88-110">Deadlocks and race conditions</span></span>  

 <span data-ttu-id="fdc88-111">다중 스레딩은 처리량 및 응답성을 사용하여 문제를 해결하지만 이 과정에서 교착 상태 및 경합 상태의 새로운 문제를 유발합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-111">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="fdc88-112">교착 상태</span><span class="sxs-lookup"><span data-stu-id="fdc88-112">Deadlocks</span></span>  

 <span data-ttu-id="fdc88-113">교착 상태는 두 개의 각 스레드가 다른 스레드가 이미 잠근 리소스를 잠그려고 할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-113">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="fdc88-114">두 스레드는 더 이상 진행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-114">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="fdc88-115">관리되는 스레딩 클래스의 많은 메서드는 교착 상태를 감지하는 데 도움이 되는 시간 제한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-115">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="fdc88-116">예를 들어 다음 코드는 `lockObject`라는 개체에 대한 잠금을 획득하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-116">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="fdc88-117">잠금이 300밀리초 내에 획득되지 않으면 <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-117">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a><span data-ttu-id="fdc88-118">경합 조건</span><span class="sxs-lookup"><span data-stu-id="fdc88-118">Race conditions</span></span>  

 <span data-ttu-id="fdc88-119">경합 상태는 두 개 이상의 스레드에 의존하는 프로그램의 결과가 특정 코드 블록에 먼저 도달하는 경우에 발생하는 버그입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-119">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="fdc88-120">프로그램을 여러 번 실행하면 서로 다른 결과를 생성하며 지정된 실행의 결과는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-120">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="fdc88-121">경합 상태의 간단한 예는 필드를 증가시키는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-121">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="fdc88-122">클래스에 `objCt++;`(C#) 또는 `objCt += 1`(Visual Basic)과 같은 코드를 사용하는, 클래스의 인스턴스가 생성될 때마다 증가되는 개인 **정적** 필드(Visual Basic에서 **Shared**)가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-122">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="fdc88-123">이 작업은 `objCt`에서 레지스터로 값을 로드하고, 값을 증가시키고 `objCt`에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-123">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="fdc88-124">다중 스레드 애플리케이션에서 값을 로드하고 증가시킨 스레드는 세 단계 모두를 수행하는 다른 스레드에 의해 선점될 수 있습니다. 첫 번째 스레드가 실행을 다시 시작하고 해당 값을 저장할 때 그 사이에 값이 변경된 사실을 고려하지 않고 `objCt`를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-124">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="fdc88-125">이 특정 경합 상태는 <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>와 같은 <xref:System.Threading.Interlocked> 클래스의 메서드를 사용하여 쉽게 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-125">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fdc88-126">다중 스레딩 간에 데이터를 동기화하는 다른 기술에 대해 알아보려면 [다중 스레딩을 위한 데이터 동기화](synchronizing-data-for-multithreading.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-126">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="fdc88-127">경합 상태는 다중 스레드의 작업을 동기화할 때에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-127">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="fdc88-128">코드 줄을 작성할 때마다 줄을 실행하기 전에(또는 줄을 구성하는 개별 컴퓨터 명령 전에) 스레드가 선점되었고 다른 스레드가 먼저 사용한 경우 발생할 수 있는 상황을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-128">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="fdc88-129">정적 멤버 및 정적 생성자</span><span class="sxs-lookup"><span data-stu-id="fdc88-129">Static members and static constructors</span></span>  

 <span data-ttu-id="fdc88-130">클래스는 해당 클래스 생성자(C#에서 `static` 생성자, Visual Basic에서 `Shared Sub New`)가 실행을 완료할 때까지 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-130">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="fdc88-131">초기화되지 않는 형식에서 코드의 실행을 방지하려면 공용 언어 런타임은 클래스 생성자가 실행을 완료할 때까지 다른 스레드에서 클래스의 `static` 멤버(Visual Basic에서 `Shared` 멤버)로 모든 호출을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-131">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="fdc88-132">예를 들어 클래스 생성자가 새 스레드를 시작하고 스레드 프로시저가 클래스의 `static` 멤버를 호출하는 경우 새 스레드는 클래스 생성자가 완료할 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-132">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="fdc88-133">이는 `static` 생성자를 가질 수 있는 모든 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-133">This applies to any type that can have a `static` constructor.</span></span>  

## <a name="number-of-processors"></a><span data-ttu-id="fdc88-134">프로세서 수</span><span class="sxs-lookup"><span data-stu-id="fdc88-134">Number of processors</span></span>

<span data-ttu-id="fdc88-135">시스템에 다중 프로세서 또는 하나의 프로세스만 사용할 수 있는지 여부에 따라 다중 스레드 아키텍처가 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-135">Whether there are multiple processors or only one processor available on a system can influence multithreaded architecture.</span></span> <span data-ttu-id="fdc88-136">자세한 내용은 [프로세서의 수](/previous-versions/dotnet/netframework-1.1/1c9txz50(v=vs.71)#number-of-processors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-136">For more information, see [Number of Processors](/previous-versions/dotnet/netframework-1.1/1c9txz50(v=vs.71)#number-of-processors).</span></span>

<span data-ttu-id="fdc88-137">런타임 시 사용 가능한 프로세서 수를 확인하려면 <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-137">Use the <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> property to determine the number of processors available at run time.</span></span>
  
## <a name="general-recommendations"></a><span data-ttu-id="fdc88-138">일반 권장 사항</span><span class="sxs-lookup"><span data-stu-id="fdc88-138">General recommendations</span></span>  

 <span data-ttu-id="fdc88-139">다중 스레드를 사용하는 경우 다음 지침을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-139">Consider the following guidelines when using multiple threads:</span></span>  
  
- <span data-ttu-id="fdc88-140">다른 스레드를 종료하는 데 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-140">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="fdc88-141">다른 스레드에서 **Abort** 를 호출하는 것은 해당 처리에서 해당 스레드가 어떤 지점에 도달했는지 알지 못하면서 해당 스레드에서 예외를 throw하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-141">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
- <span data-ttu-id="fdc88-142">여러 스레드의 활동을 동기화하는 데 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-142">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="fdc88-143"><xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.Monitor>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-143">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
- <span data-ttu-id="fdc88-144">기본 프로그램(예: 이벤트 사용)에서 작업자 스레드의 실행을 제어하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-144">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="fdc88-145">대신 작업자 스레드가 작업을 확보할 때까지 대기하고, 실행하고, 완료되면 프로그램의 다른 부분에 알릴 수 있도록 프로그램을 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-145">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="fdc88-146">작업자 스레드가 차단되지 않는 경우 스레드 풀 스레드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-146">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="fdc88-147"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType>은 작업자 스레드가 차단되는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-147"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
- <span data-ttu-id="fdc88-148">잠금 개체로 형식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-148">Don't use types as lock objects.</span></span> <span data-ttu-id="fdc88-149">즉, C#에서 `lock(typeof(X))` 또는 Visual Basic에서 `SyncLock(GetType(X))`과 같은 코드를 피하거나 <xref:System.Type> 개체와 함께 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-149">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="fdc88-150">제공된 형식의 경우 애플리케이션 도메인당 <xref:System.Type?displayProperty=nameWithType> 인스턴스가 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-150">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="fdc88-151">잠금을 사용하는 형식이 공용인 경우 개인 외의 코드는 잠금을 사용할 수 있으며 교착 상태가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-151">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="fdc88-152">추가 문제는 [최선의 안정성 구현 방법](../../framework/performance/reliability-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-152">For additional issues, see [Reliability Best Practices](../../framework/performance/reliability-best-practices.md).</span></span>  
  
- <span data-ttu-id="fdc88-153">인스턴스를 잠글 때 주의합니다(예: C#에서 `lock(this)` 또는 Visual Basic에서 `SyncLock(Me)`).</span><span class="sxs-lookup"><span data-stu-id="fdc88-153">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="fdc88-154">형식 외부의 애플리케이션에 있는 다른 코드가 개체에서 잠금을 사용하는 경우 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-154">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
- <span data-ttu-id="fdc88-155">모니터링을 시작한 스레드가 모니터링 중에 있는 동안 예외가 발생한 경우에도 항상 해당 모니터링을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-155">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="fdc88-156">C# [lock](../../csharp/language-reference/keywords/lock-statement.md) 문 및 Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) 문은 <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>이 호출되었는지 확인하는 **finally** 블록을 사용하여 이 동작을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-156">The C# [lock](../../csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="fdc88-157">**Exit** 이 호출될지 확인할 수 없는 경우 **뮤텍스** 를 사용하도록 설계를 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-157">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="fdc88-158">뮤텍스는 현재 소유하고 있는 스레드가 종료되면 자동으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-158">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
- <span data-ttu-id="fdc88-159">다른 리소스를 필요로 하는 작업에 대해 다중 스레드를 사용하고 단일 리소스에 다중 스레드를 할당하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-159">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="fdc88-160">예를 들어 해당 스레드는 I/O 작업 중에 차단되어 다른 스레드의 실행을 허용하므로 I/O와 관련된 모든 작업은 자체 스레드를 소유함으로써 이익을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-160">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="fdc88-161">사용자 입력은 전용 스레드를 활용하는 다른 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-161">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="fdc88-162">단일 프로세서 컴퓨터에서 집중적 계산을 포함하는 작업은 사용자 입력 및 I/O와 관련된 작업과 공존하지만 여러 계산 집약적인 작업은 서로 경쟁합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-162">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
- <span data-ttu-id="fdc88-163">간단한 상태 변경에 `lock` 문(Visual Basic의 `SyncLock`)을 사용하는 대신 <xref:System.Threading.Interlocked> 클래스의 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-163">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="fdc88-164">`lock` 문은 좋은 일반 용도의 도구이지만 <xref:System.Threading.Interlocked> 클래스는 원자성이어야 하는 업데이트에 더 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-164">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="fdc88-165">경합이 없는 경우 내부적으로 단일 잠금 접두사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-165">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="fdc88-166">코드 검토에서 다음 예제에서와 같은 코드를 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-166">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="fdc88-167">첫 번째 예제에서 상태 변수가 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-167">In the first example, a state variable is incremented:</span></span>  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)
    {  
        myField++;  
    }  
    ```  
  
     <span data-ttu-id="fdc88-168">다음과 같이 `lock` 문 대신 <xref:System.Threading.Interlocked.Increment%2A> 메서드를 사용하여 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-168">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="fdc88-169">1보다 큰 원자성 증분에 <xref:System.Threading.Interlocked.Add%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-169">Use the <xref:System.Threading.Interlocked.Add%2A> method for atomic increments larger than 1.</span></span>  
  
     <span data-ttu-id="fdc88-170">두 번째 예제에서 참조 형식 변수는 null 참조인 경우에만 업데이트됩니다(Visual Basic에서 `Nothing`).</span><span class="sxs-lookup"><span data-stu-id="fdc88-170">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            x ??= y;
        }  
    }  
    ```  
  
     <span data-ttu-id="fdc88-171">다음과 같이 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드를 대신 사용하여 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-171">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="fdc88-172"><xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> 메서드 오버로드는 참조 형식에 대해 형식이 안전한 대안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-172">The <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> method overload provides a type-safe alternative for reference types.</span></span>
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="fdc88-173">클래스 라이브러리에 대한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="fdc88-173">Recommendations for class libraries</span></span>  

 <span data-ttu-id="fdc88-174">다중 스레딩에 대한 클래스 라이브러리를 설계할 때 다음 지침을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-174">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
- <span data-ttu-id="fdc88-175">가능한 경우 동기화의 필요성을 피합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-175">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="fdc88-176">많이 사용되는 코드의 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-176">This is especially true for heavily used code.</span></span> <span data-ttu-id="fdc88-177">예를 들어 경합 상태를 제거하는 대신 허용하도록 알고리즘을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-177">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="fdc88-178">불필요한 동기화는 성능을 저하시키고 교착 상태 및 경합 상태의 가능성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-178">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
- <span data-ttu-id="fdc88-179">기본적으로 정적 데이터(Visual Basic에서 `Shared`)를 스레드로부터 안전하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-179">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
- <span data-ttu-id="fdc88-180">기본적으로 인스턴스 데이터를 스레드로부터 안전하게 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-180">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="fdc88-181">스레드로부터 안전한 코드를 만드는 잠금을 추가하면 성능을 저하시키고 잠금 경합이 증가하고 교착 상태가 발생할 가능성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-181">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="fdc88-182">공용 애플리케이션 모델에서 한 번에 하나의 스레드만이 스레드 보안의 필요성을 최소화하는 사용자 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-182">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="fdc88-183">이러한 이유로 .NET 클래스 라이브러리는 기본적으로 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-183">For this reason, the .NET class libraries are not thread safe by default.</span></span>  
  
- <span data-ttu-id="fdc88-184">정적 상태를 변경하는 정적 메서드를 제공 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fdc88-184">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="fdc88-185">일반적인 서버 시나리오에서 정적 상태는 요청 간 공유되며 여러 스레드가 동시에 해당 코드를 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-185">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="fdc88-186">스레드 버그가 발생할 가능성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-186">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="fdc88-187">요청 간에 공유되지 않는 인스턴스로 데이터를 캡슐화하는 디자인 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-187">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="fdc88-188">또한 정적 데이터가 동기화되는 경우 상태를 변경하는 정적 메서드 간 호출은 성능에 부정적인 영향을 주어 교착 상태 또는 중복된 동기화를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc88-188">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc88-189">참조</span><span class="sxs-lookup"><span data-stu-id="fdc88-189">See also</span></span>

- [<span data-ttu-id="fdc88-190">스레딩</span><span class="sxs-lookup"><span data-stu-id="fdc88-190">Threading</span></span>](index.md)
- [<span data-ttu-id="fdc88-191">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="fdc88-191">Threads and Threading</span></span>](threads-and-threading.md)
