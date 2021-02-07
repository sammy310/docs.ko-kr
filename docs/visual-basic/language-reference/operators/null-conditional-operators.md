---
description: 에 대해 자세히 알아보세요. 하거나? () null 조건 연산자 (Visual Basic)
title: Null 조건 연산자
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 558b8921d0da4089505dd1035cb6039af24a2802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665369"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="fc65e-104">?.</span><span class="sxs-lookup"><span data-stu-id="fc65e-104">?.</span></span> <span data-ttu-id="fc65e-105">하거나? () null 조건 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc65e-105">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="fc65e-106">`Nothing`멤버 액세스 () 또는 인덱스 () 작업을 수행 하기 전에 null ()의 왼쪽 피연산자 값을 테스트 `?.` `?()` 하 고, `Nothing` 왼쪽 피연산자가로 계산 되 면를 반환 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-106">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="fc65e-107">일반적으로 값 형식을 반환 하는 식에서 null 조건 연산자는를 반환 합니다 <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="fc65e-107">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="fc65e-108">이러한 연산자는 null 검사를 처리 하는 코드를 작성 하는 데 도움이 됩니다. 특히 데이터 구조체로 내림차순으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-108">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="fc65e-109">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="fc65e-109">For example:</span></span>

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

<span data-ttu-id="fc65e-110">비교를 위해 null 조건 연산자가 없는 첫 번째 식의 대체 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-110">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="fc65e-111">다음 예제의 부울 속성과 같이 해당 개체에 대 한 부울 멤버의 값을 기반으로 하 여 null 일 수 있는 개체에 대 한 작업을 수행 해야 하는 경우가 있습니다 `IsAllowedFreeShipping` .</span><span class="sxs-lookup"><span data-stu-id="fc65e-111">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

<span data-ttu-id="fc65e-112">다음과 같이 null 조건 연산자를 사용 하 여 코드를 줄이고 null을 수동으로 확인 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-112">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="fc65e-113">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-113">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="fc65e-114">조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업이 반환 `Nothing` 되 면 나머지 체인 실행이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-114">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="fc65e-115">다음 예에서는, `C(E)` `A` 또는가 `B` `C` 로 계산 되는 경우이 계산 되지 않습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="fc65e-115">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E)
```

<span data-ttu-id="fc65e-116">Null 조건부 멤버 액세스의 또 다른 용도는 훨씬 낮은 코드를 사용 하 여 스레드로부터 안전한 방식으로 대리자를 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-116">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="fc65e-117">다음 예제에서는 및 라는 두 가지 형식을 정의 합니다 `NewsBroadcaster` `NewsReceiver` .</span><span class="sxs-lookup"><span data-stu-id="fc65e-117">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="fc65e-118">뉴스 항목은 대리자에 의해 수신자에 게 전송 됩니다 `NewsBroadcaster.SendNews` .</span><span class="sxs-lookup"><span data-stu-id="fc65e-118">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="fc65e-119">호출 목록에 요소가 없으면 `SendNews` `SendNews` 대리자는을 throw <xref:System.NullReferenceException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-119">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="fc65e-120">Null 조건부 연산자 이전에 다음과 같은 코드는 대리자 호출 목록이이 아닌 것으로 확인 되었습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="fc65e-120">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

<span data-ttu-id="fc65e-121">새로운 방식은 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-121">The new way is much simpler:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="fc65e-122">새로운 방식은 컴파일러가 `SendNews`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-122">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="fc65e-123">null 조건부 대리자 호출 구문 `SendNews?(String)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc65e-123">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc65e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc65e-124">See also</span></span>

- [<span data-ttu-id="fc65e-125">연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc65e-125">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="fc65e-126">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fc65e-126">Visual Basic Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fc65e-127">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="fc65e-127">Visual Basic Language Reference</span></span>](../index.md)
