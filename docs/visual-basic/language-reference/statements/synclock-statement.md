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
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352814"
---
# <a name="synclock-statement"></a><span data-ttu-id="c6e5f-102">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="c6e5f-102">SyncLock Statement</span></span>
<span data-ttu-id="c6e5f-103">블록을 실행 하기 전에 문 블록에 대 한 단독 잠금을 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6e5f-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="c6e5f-105">요소</span><span class="sxs-lookup"><span data-stu-id="c6e5f-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="c6e5f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-106">Required.</span></span> <span data-ttu-id="c6e5f-107">개체 참조로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="c6e5f-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-108">Optional.</span></span> <span data-ttu-id="c6e5f-109">잠금을 획득할 때 실행할 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="c6e5f-110">`SyncLock` 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6e5f-111">설명</span><span class="sxs-lookup"><span data-stu-id="c6e5f-111">Remarks</span></span>  
 <span data-ttu-id="c6e5f-112">`SyncLock` 문을 사용 하면 여러 스레드가 동시에 문 블록을 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="c6e5f-113">`SyncLock`는 다른 스레드가 실행 하지 않을 때까지 각 스레드가 블록을 입력 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="c6e5f-114">`SyncLock`은 두 개 이상의 스레드에서 데이터를 동시에 업데이트 하지 않도록 보호 하는 데 가장 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="c6e5f-115">데이터를 조작 하는 문이 중단 없이 완료 되어야 하는 경우에는 `SyncLock` 블록 안에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="c6e5f-116">배타적 잠금으로 보호 되는 문 블록은 *임계 영역*이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c6e5f-117">규칙</span><span class="sxs-lookup"><span data-stu-id="c6e5f-117">Rules</span></span>  
  
- <span data-ttu-id="c6e5f-118">분기.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-118">Branching.</span></span> <span data-ttu-id="c6e5f-119">블록 외부에서 `SyncLock` 블록으로 분기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="c6e5f-120">잠금 개체 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-120">Lock Object Value.</span></span> <span data-ttu-id="c6e5f-121">`lockobject` 값은 `Nothing`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="c6e5f-122">Lock 개체는 `SyncLock` 문에서 사용 하기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="c6e5f-123">`SyncLock` 블록을 실행 하는 동안 `lockobject`의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="c6e5f-124">이 메커니즘을 사용 하려면 lock 개체가 변경 되지 않은 상태로 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="c6e5f-125">`SyncLock` 블록에는 [wait](../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c6e5f-126">동작</span><span class="sxs-lookup"><span data-stu-id="c6e5f-126">Behavior</span></span>  
  
- <span data-ttu-id="c6e5f-127">방법일.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-127">Mechanism.</span></span> <span data-ttu-id="c6e5f-128">스레드가 `SyncLock` 문에 도달 하면 `lockobject` 식을 계산 하 고 식에서 반환 하는 개체에 대 한 배타적 잠금을 획득할 때까지 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="c6e5f-129">다른 스레드가 `SyncLock` 문에 도달 하면 첫 번째 스레드가 `End SyncLock` 문을 실행할 때까지 잠금을 획득 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="c6e5f-130">보호 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-130">Protected Data.</span></span> <span data-ttu-id="c6e5f-131">`lockobject` `Shared` 변수인 경우에는 다른 스레드가 실행 하는 동안 클래스의 모든 인스턴스에서 스레드가 `SyncLock` 블록을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="c6e5f-132">이는 모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="c6e5f-133">`lockobject` 인스턴스 변수인 경우 (`Shared`아님) 잠금은 현재 인스턴스에서 실행 되는 스레드가 동일한 인스턴스의 다른 스레드와 동시에 `SyncLock` 블록을 실행 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="c6e5f-134">그러면 개별 인스턴스에 의해 유지 관리 되는 데이터가 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="c6e5f-135">취득 및 릴리스.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-135">Acquisition and Release.</span></span> <span data-ttu-id="c6e5f-136">`SyncLock` 블록은 `Try` 블록이 `lockobject`에 대 한 배타적 잠금을 획득 하 고 `Finally` 블록이이를 해제 하는 `Try...Finally` 생성 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="c6e5f-137">이로 인해 `SyncLock` 블록은 블록을 종료 하는 방법에 관계 없이 잠금 해제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="c6e5f-138">처리 되지 않은 예외의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="c6e5f-139">프레임 워크 호출.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-139">Framework Calls.</span></span> <span data-ttu-id="c6e5f-140">`SyncLock` 블록은 <xref:System.Threading> 네임 스페이스에서 `Monitor` 클래스의 `Enter` 및 `Exit` 메서드를 호출 하 여 배타적 잠금을 획득 하 고 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="c6e5f-141">프로그래밍 방법</span><span class="sxs-lookup"><span data-stu-id="c6e5f-141">Programming Practices</span></span>  
 <span data-ttu-id="c6e5f-142">`lockobject` 식은 항상 클래스에 독점적으로 속하는 개체로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="c6e5f-143">현재 인스턴스에 속하는 데이터를 보호 하기 위해 `Private` 개체 변수를 선언 하거나 모든 인스턴스에 공통 된 데이터를 보호 하기 위해 `Private Shared` 개체 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="c6e5f-144">`Me` 키워드를 사용 하 여 인스턴스 데이터에 대 한 잠금 개체를 제공 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="c6e5f-145">클래스 외부의 코드에 클래스의 인스턴스에 대 한 참조가 있는 경우 해당 참조를 다른 데이터를 보호 하는 것과 완전히 다른 `SyncLock` 블록의 잠금 개체로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="c6e5f-146">이러한 방식으로 클래스와 다른 클래스는 관련 없는 `SyncLock` 블록을 실행 하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="c6e5f-147">동일한 문자열을 사용 하는 프로세스의 다른 코드가 동일한 잠금을 공유 하기 때문에 문자열에 대 한 잠금과 잠금은 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="c6e5f-148">또한 `Me.GetType` 메서드를 사용 하 여 공유 데이터에 대 한 잠금 개체를 제공 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="c6e5f-149">이는 `GetType` 항상 지정 된 클래스 이름에 대해 같은 `Type` 개체를 반환 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="c6e5f-150">외부 코드는 클래스에서 `GetType`를 호출 하 고 사용 하는 것과 동일한 잠금 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="c6e5f-151">이로 인해 두 클래스가 `SyncLock` 블록에서 서로 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c6e5f-152">예</span><span class="sxs-lookup"><span data-stu-id="c6e5f-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6e5f-153">설명</span><span class="sxs-lookup"><span data-stu-id="c6e5f-153">Description</span></span>  
 <span data-ttu-id="c6e5f-154">다음 예제에서는 간단한 메시지 목록을 유지 관리 하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="c6e5f-155">배열에 있는 메시지와 해당 배열의 마지막으로 사용 된 요소를 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="c6e5f-156">`addAnotherMessage` 프로시저는 마지막 요소를 증가 시키고 새 메시지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="c6e5f-157">이러한 두 작업은 `SyncLock` 및 `End SyncLock` 문으로 보호 됩니다. 마지막 요소를 증가 시킨 후에는 새 메시지를 저장 해야 다른 스레드가 마지막 요소를 다시 증가 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="c6e5f-158">`simpleMessageList` 클래스가 모든 인스턴스 간에 메시지 목록 하나를 공유 하는 경우 변수 `messagesList` 및 `messagesLast`는 `Shared`으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="c6e5f-159">이 경우 모든 인스턴스에서 사용 되는 단일 잠금 개체가 되도록 `messagesLock` 변수를 `Shared`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6e5f-160">코드</span><span class="sxs-lookup"><span data-stu-id="c6e5f-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="c6e5f-161">설명</span><span class="sxs-lookup"><span data-stu-id="c6e5f-161">Description</span></span>  
 <span data-ttu-id="c6e5f-162">다음 예제에서는 스레드와 `SyncLock`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="c6e5f-163">`SyncLock` 문이 있으면 문 블록은 임계 섹션이 되며 `balance` 음수가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="c6e5f-164">`SyncLock` 및 `End SyncLock` 문을 주석으로 처리 하 여 `SyncLock` 키워드를 종료 하는 효과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e5f-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6e5f-165">코드</span><span class="sxs-lookup"><span data-stu-id="c6e5f-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="c6e5f-166">주석</span><span class="sxs-lookup"><span data-stu-id="c6e5f-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e5f-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6e5f-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="c6e5f-168">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="c6e5f-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
