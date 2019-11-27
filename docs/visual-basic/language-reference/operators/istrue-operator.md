---
title: IsTrue 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349506"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="e55c4-102">IsTrue 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e55c4-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="e55c4-103">식이 `True`되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="e55c4-104">`IsTrue`는 코드에서 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는이를 사용 하 여 `OrElse` 절에서 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="e55c4-105">클래스 또는 구조체를 정의 하 고 `OrElse` 절에서 해당 형식의 변수를 사용 하는 경우 해당 클래스 또는 구조체에서 `IsTrue`를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="e55c4-106">컴파일러는 `IsTrue` 및 `IsFalse` 연산자를 일치 하는 *쌍*으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="e55c4-107">즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="e55c4-108">IsTrue의 컴파일러 사용</span><span class="sxs-lookup"><span data-stu-id="e55c4-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="e55c4-109">클래스 또는 구조체를 정의 하는 경우 `For`, `If`, `Else If`또는 `While` 문이나 `When` 절에서 해당 형식의 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="e55c4-110">이 작업을 수행 하는 경우 컴파일러는 조건을 테스트할 수 있도록 형식을 `Boolean` 값으로 변환 하는 연산자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="e55c4-111">다음 순서에 따라 적합 한 연산자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="e55c4-112">클래스 또는 구조체의 확대 변환 연산자를 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="e55c4-113">클래스 또는 구조체의 확대 변환 연산자를 `Boolean?`합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="e55c4-114">클래스 또는 구조체의 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="e55c4-115">`Boolean`에서 `Boolean?`로의 변환이 포함 되지 않는 `Boolean?`로의 축소 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="e55c4-116">클래스 또는 구조체에서 `Boolean`하는 축소 변환 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="e55c4-117">`Boolean` 또는 `IsTrue` 연산자에 대 한 변환을 정의 하지 않은 경우 컴파일러는 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e55c4-118">`IsTrue` 연산자는 *오버 로드*될 수 있습니다. 즉, 클래스 또는 구조체의 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="e55c4-119">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e55c4-120">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e55c4-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e55c4-121">예제</span><span class="sxs-lookup"><span data-stu-id="e55c4-121">Example</span></span>  
 <span data-ttu-id="e55c4-122">다음 코드 예제에서는 `IsFalse` 및 `IsTrue` 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e55c4-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e55c4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e55c4-123">See also</span></span>

- [<span data-ttu-id="e55c4-124">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="e55c4-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="e55c4-125">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e55c4-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e55c4-126">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="e55c4-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
