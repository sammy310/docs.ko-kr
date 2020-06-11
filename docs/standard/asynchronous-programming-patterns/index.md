---
title: 비동기 프로그래밍 패턴
description: .NET의 TAP(작업 기반 비동기 패턴), EAP(이벤트 기반 비동기 패턴) 및 APM(비동기 프로그래밍 모델)에 대해 알아보세요.
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: bd4d44d8de8a64be82e9ce6af593a86719b59fcf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84583507"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="2b755-103">비동기 프로그래밍 패턴</span><span class="sxs-lookup"><span data-stu-id="2b755-103">Asynchronous programming patterns</span></span>

<span data-ttu-id="2b755-104">.NET에서는 비동기 작업을 수행하기 위한 세 가지 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-104">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="2b755-105">단일 메서드를 사용하여 비동기 작업 시작과 완료를 나타내는 **TAP(작업 기반 비동기 패턴)** .</span><span class="sxs-lookup"><span data-stu-id="2b755-105">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="2b755-106">TAP는 .NET Framework 4에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-106">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="2b755-107">**.NET에서 비동기 프로그램에 권장되는 방법입니다.**</span><span class="sxs-lookup"><span data-stu-id="2b755-107">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="2b755-108">C#의 [async](../../csharp/language-reference/keywords/async.md) 및 [await](../../csharp/language-reference/operators/await.md) 키워드와 Visual Basic의 [Async](../../visual-basic/language-reference/modifiers/async.md) 및 [Await](../../visual-basic/language-reference/operators/await-operator.md) 연산자는 TAP에 대한 언어 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-108">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="2b755-109">자세한 내용은 [TAP(작업 기반 비동기 패턴)](task-based-asynchronous-pattern-tap.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b755-109">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="2b755-110">비동기 동작을 제공하기 위한 이벤트 기반 레거시 모델인 **EAP(이벤트 기반 비동기 패턴)** .</span><span class="sxs-lookup"><span data-stu-id="2b755-110">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="2b755-111">이 패턴에서는 `Async` 접미사가 있는 메서드가 필요하며 하나 이상의 이벤트, 이벤트 처리기 대리자 형식 및 `EventArg`에서 파생된 형식도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-111">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="2b755-112">EAP는 .NET Framework 2.0에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-112">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="2b755-113">이 패턴 역시 신규 개발에서는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-113">It's no longer recommended for new development.</span></span> <span data-ttu-id="2b755-114">자세한 내용은 [EAP(이벤트 기반 비동기 패턴)](event-based-asynchronous-pattern-eap.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b755-114">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="2b755-115"><xref:System.IAsyncResult> 인터페이스를 사용하여 비동기 동작을 제공하는 레거시 모델인 **APM(비동기 프로그래밍 모델)** 패턴(<xref:System.IAsyncResult> 패턴이라고도 함).</span><span class="sxs-lookup"><span data-stu-id="2b755-115">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="2b755-116">이 패턴에서는 동기 작업에 `Begin` 및 `End` 메소드(예를 들어 비동기 쓰기 작업을 구현하는 `BeginWrite` 및 `EndWrite`)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-116">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="2b755-117">신규 개발에서는 이 패턴을 더 이상 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-117">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="2b755-118">자세한 내용은 [APM(비동기 프로그래밍 모델)](asynchronous-programming-model-apm.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b755-118">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="2b755-119">패턴 비교</span><span class="sxs-lookup"><span data-stu-id="2b755-119">Comparison of patterns</span></span>

<span data-ttu-id="2b755-120">위의 세 가지 패턴 모델이 비동기 작업을 수행하는 방법을 빠르게 비교하려는 경우 지정한 오프셋에서부터 지정된 양의 데이터를 제공된 버퍼로 읽어 들이는 `Read` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-120">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="2b755-121">이 메서드에 해당하는 TAP 코드는 다음의 단일 `ReadAsync` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-121">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="2b755-122">그리고 이 메서드에 해당하는 EAP 코드는 다음 형식 및 멤버 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-122">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="2b755-123">해당하는 APM 코드는 `BeginRead` 및 `EndRead` 메소드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b755-123">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="2b755-124">참조</span><span class="sxs-lookup"><span data-stu-id="2b755-124">See also</span></span>

- [<span data-ttu-id="2b755-125">비동기에 대한 자세한 설명</span><span class="sxs-lookup"><span data-stu-id="2b755-125">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="2b755-126">C#의 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2b755-126">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="2b755-127">F#의 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2b755-127">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="2b755-128">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b755-128">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
