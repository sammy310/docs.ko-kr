---
title: Null 조건부 연산자 (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 4815fe7ad337634cfb56127fbd24a47a37fdd74b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062936"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="68a23-102">?.</span><span class="sxs-lookup"><span data-stu-id="68a23-102">?.</span></span> <span data-ttu-id="68a23-103">및? null 조건부 연산자 () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a23-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="68a23-104">Null에 대 한 왼쪽 피연산자의 값을 테스트 (`Nothing`)는 멤버 액세스를 수행 하기 전에 (`?.`) 또는 인덱스 (`?()`) 작업; 반환 `Nothing` 왼쪽 피연산자가 `Nothing`입니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="68a23-105">일반적으로 값 형식을 반환 하는 식에서 null 조건부 연산자를 반환 하는 <xref:System.Nullable%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="68a23-106">이러한 연산자는 데이터 구조에서 아래로 내려가는 경우에 특히 null 검사를 처리 하는 작은 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="68a23-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="68a23-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="68a23-108">반면 null 조건부 연산자 없이 이러한 식의 첫 번째에 대 한 대체 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="68a23-109">Null 일 수를 해당 개체에 대해 부울 멤버의 값을 기반으로 하는 개체에 대 한 작업을 수행 해야 하는 경우에 따라 (부울 속성을 같은 `IsAllowedFreeShipping` 다음 예제의):</span><span class="sxs-lookup"><span data-stu-id="68a23-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
  Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
  
  If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
   ApplyFreeShippingToOrders(customer)
  End If
```

<span data-ttu-id="68a23-110">코드 단축 하 고 수동으로 다음과 같이 null 조건부 연산자를 사용 하 여 null 검사를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
 Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
 
 If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="68a23-111">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="68a23-112">조건부 멤버 액세스 및 인덱스 작업의 체인에 하나의 작업에서 반환 하는 경우 `Nothing`, 나머지 체인의 실행이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="68a23-113">다음 예에서 `C(E)` 하는 경우 평가 되지 않습니다 `A`를 `B`, 또는 `C` 로 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="68a23-114">Null 조건부 멤버 액세스에 대 한 또 다른 용도 훨씬 더 적은 코드를 사용 하 여 스레드로부터 안전한 방식으로 대리자를 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="68a23-115">다음 예제에서는 두 가지 형식 정의 `NewsBroadcaster` 및 `NewsReceiver`합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="68a23-116">뉴스 항목에서 수신자에 게 전송 되는 `NewsBroadcaster.SendNews` 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

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

<span data-ttu-id="68a23-117">요소가 없을 경우는 `SendNews` 호출 목록에는 `SendNews` throw 대리자는 <xref:System.NullReferenceException>합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="68a23-118">Null 조건부 연산자를 코드 대리자 호출 목록 없음을 확인 했습니다 다음과 같은 `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="68a23-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="68a23-119">새로운 방식은 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-119">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="68a23-120">새로운 방식은 컴파일러가 `SendNews`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="68a23-121">null 조건부 대리자 호출 구문 `SendNews?(String)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a23-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="68a23-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="68a23-122">See also</span></span>

- [<span data-ttu-id="68a23-123">연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a23-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="68a23-124">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68a23-124">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="68a23-125">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="68a23-125">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
