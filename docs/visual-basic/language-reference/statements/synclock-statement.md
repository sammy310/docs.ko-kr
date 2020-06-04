---
title: SyncLock 문
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: fd932a20af274faf2b56136a94675b28399989b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404163"
---
# <a name="synclock-statement"></a><span data-ttu-id="3f5e9-102">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="3f5e9-102">SyncLock Statement</span></span>
<span data-ttu-id="3f5e9-103">블록을 실행 하기 전에 문 블록에 대 한 단독 잠금을 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f5e9-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="3f5e9-105">부분</span><span class="sxs-lookup"><span data-stu-id="3f5e9-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="3f5e9-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-106">Required.</span></span> <span data-ttu-id="3f5e9-107">개체 참조로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="3f5e9-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-108">Optional.</span></span> <span data-ttu-id="3f5e9-109">잠금을 획득할 때 실행할 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="3f5e9-110">블록을 종료 `SyncLock` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f5e9-111">설명</span><span class="sxs-lookup"><span data-stu-id="3f5e9-111">Remarks</span></span>  
 <span data-ttu-id="3f5e9-112">문을 사용 하면 `SyncLock` 여러 스레드가 동시에 문 블록을 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="3f5e9-113">`SyncLock`다른 스레드가 실행 하지 않을 때까지 각 스레드가 블록을 입력 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="3f5e9-114">의 가장 일반적인 용도는 `SyncLock` 두 개 이상의 스레드에서 데이터를 동시에 업데이트 하지 않도록 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="3f5e9-115">데이터를 조작 하는 문이 중단 없이 완료로 이동 해야 하는 경우 블록 안에 배치 합니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="3f5e9-116">배타적 잠금으로 보호 되는 문 블록은 *임계 영역*이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3f5e9-117">규칙</span><span class="sxs-lookup"><span data-stu-id="3f5e9-117">Rules</span></span>  
  
- <span data-ttu-id="3f5e9-118">분기.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-118">Branching.</span></span> <span data-ttu-id="3f5e9-119">블록 외부에서 블록으로 분기할 수 없습니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="3f5e9-120">잠금 개체 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-120">Lock Object Value.</span></span> <span data-ttu-id="3f5e9-121">값은 `lockobject` 일 수 없습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="3f5e9-122">문에서 사용 하기 전에 lock 개체를 만들어야 합니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="3f5e9-123">`lockobject`블록을 실행 하는 동안의 값은 변경할 수 없습니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="3f5e9-124">이 메커니즘을 사용 하려면 lock 개체가 변경 되지 않은 상태로 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="3f5e9-125">블록에는 [wait](../operators/await-operator.md) 연산자를 사용할 수 없습니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-125">You can't use the [Await](../operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3f5e9-126">동작</span><span class="sxs-lookup"><span data-stu-id="3f5e9-126">Behavior</span></span>  
  
- <span data-ttu-id="3f5e9-127">방법일.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-127">Mechanism.</span></span> <span data-ttu-id="3f5e9-128">스레드가 문에 도달 하면 `SyncLock` 식을 계산 하 `lockobject` 고 식에서 반환 되는 개체에 대 한 배타적 잠금을 획득할 때까지 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="3f5e9-129">다른 스레드가 문에 도달 하면 `SyncLock` 첫 번째 스레드가 문을 실행할 때까지 잠금을 획득 하지 않습니다 `End SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="3f5e9-130">보호 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-130">Protected Data.</span></span> <span data-ttu-id="3f5e9-131">`lockobject`가 변수인 경우 `Shared` 단독 잠금은 클래스의 모든 인스턴스에서 스레드가 실행 되는 동안 블록을 실행 하는 것을 방지 합니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="3f5e9-132">이는 모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="3f5e9-133">`lockobject`가이 아닌 인스턴스 변수인 경우 `Shared` 잠금은 현재 인스턴스에서 실행 되는 스레드가 `SyncLock` 같은 인스턴스의 다른 스레드와 동시에 블록을 실행 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="3f5e9-134">그러면 개별 인스턴스에 의해 유지 관리 되는 데이터가 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="3f5e9-135">취득 및 릴리스.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-135">Acquisition and Release.</span></span> <span data-ttu-id="3f5e9-136">블록은 `SyncLock` `Try...Finally` `Try` 블록이에서 배타적 잠금을 획득 하 고 블록에서 해제 하는 생성 처럼 동작 `lockobject` `Finally` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="3f5e9-137">따라서 블록을 `SyncLock` 종료 하는 방법에 관계 없이 블록은 잠금 해제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="3f5e9-138">처리 되지 않은 예외의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="3f5e9-139">프레임 워크 호출.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-139">Framework Calls.</span></span> <span data-ttu-id="3f5e9-140">`SyncLock`블록은 `Enter` `Exit` `Monitor` 네임 스페이스에서 클래스의 및 메서드를 호출 하 여 단독 잠금을 획득 하 고 해제 합니다 <xref:System.Threading> .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="3f5e9-141">프로그래밍 방법</span><span class="sxs-lookup"><span data-stu-id="3f5e9-141">Programming Practices</span></span>  
 <span data-ttu-id="3f5e9-142">`lockobject`식은 항상 클래스에 독점적으로 속하는 개체로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="3f5e9-143">`Private`현재 인스턴스에 속하는 데이터를 보호 하기 위해 개체 변수를 선언 하거나 개체 변수를 선언 하 여 `Private Shared` 모든 인스턴스에 공통적인 데이터를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="3f5e9-144">키워드를 사용 하 여 `Me` 인스턴스 데이터에 대 한 잠금 개체를 제공 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="3f5e9-145">클래스 외부의 코드에 클래스의 인스턴스에 대 한 참조가 있는 경우 해당 참조를 `SyncLock` 다른 데이터를 보호 하는 것과 완전히 다른 블록에 대 한 잠금 개체로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="3f5e9-146">이러한 방식으로 클래스와 다른 클래스는 관련 되지 않은 블록을 실행 하지 못하도록 차단할 수 있습니다 `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="3f5e9-147">동일한 문자열을 사용 하는 프로세스의 다른 코드가 동일한 잠금을 공유 하기 때문에 문자열에 대 한 잠금과 잠금은 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="3f5e9-148">또한 메서드를 사용 하 여 `Me.GetType` 공유 데이터에 대 한 잠금 개체를 제공 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="3f5e9-149">이는 `GetType` 항상 `Type` 지정 된 클래스 이름에 대해 같은 개체를 반환 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="3f5e9-150">외부 코드는 `GetType` 클래스에 대해를 호출 하 고 사용 하는 것과 동일한 잠금 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="3f5e9-151">이로 인해 두 클래스가 해당 블록에서 서로 차단 `SyncLock` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3f5e9-152">예</span><span class="sxs-lookup"><span data-stu-id="3f5e9-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="3f5e9-153">Description</span><span class="sxs-lookup"><span data-stu-id="3f5e9-153">Description</span></span>  
 <span data-ttu-id="3f5e9-154">다음 예제에서는 간단한 메시지 목록을 유지 관리 하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="3f5e9-155">배열에 있는 메시지와 해당 배열의 마지막으로 사용 된 요소를 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="3f5e9-156">이 `addAnotherMessage` 프로시저는 마지막 요소를 증가 시키고 새 메시지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="3f5e9-157">이러한 두 작업은 `SyncLock` 및 문으로 보호 됩니다 `End SyncLock` . 마지막 요소를 증가 시킨 후에는 새 메시지를 저장 해야 다른 스레드가 마지막 요소를 다시 증가 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="3f5e9-158">`simpleMessageList`클래스가 모든 인스턴스 간에 메시지 목록 하나를 공유 하는 경우 및 변수는 `messagesList` `messagesLast` 로 선언 됩니다 `Shared` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="3f5e9-159">이 경우 변수는 `messagesLock` 여야 `Shared` 하므로 모든 인스턴스에서 단일 잠금 개체가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3f5e9-160">코드</span><span class="sxs-lookup"><span data-stu-id="3f5e9-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="3f5e9-161">Description</span><span class="sxs-lookup"><span data-stu-id="3f5e9-161">Description</span></span>  
 <span data-ttu-id="3f5e9-162">다음 예제에서는 및 스레드를 사용 `SyncLock` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="3f5e9-163">`SyncLock`문이 있으면 문 블록은 임계 섹션이 되며 `balance` 음수가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f5e9-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="3f5e9-164">및 문을 주석으로 처리 하 여 키워드를 종료 하는 효과를 확인할 수 있습니다 `SyncLock` `End SyncLock` `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="3f5e9-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3f5e9-165">코드</span><span class="sxs-lookup"><span data-stu-id="3f5e9-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="3f5e9-166">주석</span><span class="sxs-lookup"><span data-stu-id="3f5e9-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5e9-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f5e9-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="3f5e9-168">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="3f5e9-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
