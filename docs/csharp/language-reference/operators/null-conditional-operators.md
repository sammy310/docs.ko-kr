---
title: Null 조건 연산자 - C# 참조
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 9cbf8a0f860f0bc0328cd98e558b20b5e8e1bf8f
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348845"
---
# <a name="-and--null-conditional-operators-c-reference"></a><span data-ttu-id="69ab8-102">?.</span><span class="sxs-lookup"><span data-stu-id="69ab8-102">?.</span></span> <span data-ttu-id="69ab8-103">및 ?[] Null 조건 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="69ab8-103">and ?[] null-conditional operators (C# Reference)</span></span>

<span data-ttu-id="69ab8-104">멤버 액세스(`?.`) 또는 인덱스(`?[]`) 작업을 수행하기 전에 Null에서 왼쪽 피연산자의 값을 테스트합니다. 왼쪽 피연산자가 `null`로 계산하는 경우 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="69ab8-105">이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

<span data-ttu-id="69ab8-106">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="69ab8-107">조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 null을 반환하면 체인 실행의 나머지 부분이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="69ab8-108">다음 예제에서 `E`는 `A`, `B` 또는 `C`가 Null로 평가되는 경우 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

<span data-ttu-id="69ab8-109">또한 Null 조건부 멤버 액세스는 훨씬 더 적은 코드를 사용하여 스레드로부터 안전한 방식으로 대리자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="69ab8-110">이전 방식에서는 다음과 같은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-110">The old way requires code like the following:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

<span data-ttu-id="69ab8-111">새로운 방식은 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-111">The new way is much simpler:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="69ab8-112">새로운 방식은 컴파일러가 `PropertyChanged`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="69ab8-113">null 조건부 대리자 호출 구문 `PropertyChanged?(e)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="69ab8-114">언어 사양</span><span class="sxs-lookup"><span data-stu-id="69ab8-114">Language specifications</span></span>

<span data-ttu-id="69ab8-115">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [Null 결합 연산자](~/_csharplang/spec/expressions.md#null-conditional-operator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69ab8-115">For more information, see [Null-conditional operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="69ab8-116">C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="69ab8-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="69ab8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69ab8-117">See also</span></span>

- [<span data-ttu-id="69ab8-118">??(Null 병합 연산자)</span><span class="sxs-lookup"><span data-stu-id="69ab8-118">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="69ab8-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="69ab8-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="69ab8-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="69ab8-120">C# Programming Guide</span></span>](../../programming-guide/index.md)