---
title: IsTrue 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: cb8ad8cb4a1ec13611edfcc3de7f4b7eb33fc553
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829930"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="d89f2-102">IsTrue 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d89f2-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="d89f2-103">식이 인지 결정 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="d89f2-104">호출할 수 없습니다 `IsTrue` 명시적으로 코드 에서만 Visual Basic 컴파일러는 데 사용할 수에서 코드를 생성할 `OrElse` 절.</span><span class="sxs-lookup"><span data-stu-id="d89f2-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="d89f2-105">클래스 또는 구조체 정의 다음에 있는 해당 유형의 변수를 사용 하는 경우는 `OrElse` 정의 해야 절 `IsTrue` 해당 클래스 또는 구조체에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="d89f2-106">컴파일러에서 고려 하는 `IsTrue` 및 `IsFalse` 연산자는 *일치 하는 쌍*합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="d89f2-107">이 그 중 하나를 정의 하는 경우 정의 해야 합니다도 다른 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="d89f2-108">IsTrue 컴파일러 사용</span><span class="sxs-lookup"><span data-stu-id="d89f2-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="d89f2-109">클래스 또는 구조체를 정의한 경우에 해당 형식에서 변수의 사용할 수 있습니다는 `For`, `If`를 `Else If`, 또는 `While` 문, 또는 `When` 절.</span><span class="sxs-lookup"><span data-stu-id="d89f2-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="d89f2-110">이렇게 하면 컴파일러 형식으로 변환 하는 연산자가 필요는 `Boolean` 값 조건을 테스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="d89f2-111">다음 순서 대로 연산자를 적절 한 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="d89f2-112">클래스 또는 구조체에서 확대 변환 연산자 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="d89f2-113">클래스 또는 구조체에서 확대 변환 연산자 `Boolean?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="d89f2-114">`IsTrue` 클래스 또는 구조체에서 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="d89f2-115">로 축소 변환 `Boolean?` 변환에서 포함 하지 않는 `Boolean` 에 `Boolean?`입니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="d89f2-116">클래스 또는 구조체에서 축소 변환 연산자 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="d89f2-117">으로 변환이 정의 하지 않은 경우 `Boolean` 요소나 `IsTrue` 연산자, 컴파일러에서 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d89f2-118">합니다 `IsTrue` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="d89f2-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="d89f2-119">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d89f2-120">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d89f2-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d89f2-121">예제</span><span class="sxs-lookup"><span data-stu-id="d89f2-121">Example</span></span>  
 <span data-ttu-id="d89f2-122">다음 코드 예제에 대 한 정의 포함 하는 구조체의 윤곽선을 정의 합니다 `IsFalse` 고 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d89f2-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="d89f2-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="d89f2-123">See also</span></span>

- [<span data-ttu-id="d89f2-124">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="d89f2-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="d89f2-125">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="d89f2-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="d89f2-126">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="d89f2-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
