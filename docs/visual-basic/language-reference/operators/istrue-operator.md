---
title: IsTrue 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bc129d3a3aec76285d5ea8fb727fc72c3064c9cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370650"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="c600f-102">IsTrue 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c600f-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="c600f-103">식이 인지 여부를 확인 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="c600f-104">`IsTrue`코드에서 명시적으로 호출할 수는 없지만 Visual Basic 컴파일러는이를 사용 하 여 절에서 코드를 생성할 수 있습니다 `OrElse` .</span><span class="sxs-lookup"><span data-stu-id="c600f-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="c600f-105">클래스 또는 구조체를 정의한 다음 해당 형식의 변수를 절에서 사용 하는 경우 `OrElse` `IsTrue` 해당 클래스 또는 구조체에 대해를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="c600f-106">컴파일러는 `IsTrue` 및 연산자를 `IsFalse` 일치 하는 *쌍*으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="c600f-107">즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="c600f-108">IsTrue의 컴파일러 사용</span><span class="sxs-lookup"><span data-stu-id="c600f-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="c600f-109">클래스 또는 구조체를 정의한 경우 `For` ,, `If` `Else If` 또는 `While` 문이나 `When` 절에서 해당 형식의 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="c600f-110">이 작업을 수행 하는 경우 컴파일러는 `Boolean` 조건을 테스트할 수 있도록 형식을 값으로 변환 하는 연산자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="c600f-111">다음 순서에 따라 적합 한 연산자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="c600f-112">클래스 또는 구조체에서로의 확대 변환 연산자 `Boolean` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="c600f-113">클래스 또는 구조체에서로의 확대 변환 연산자 `Boolean?` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="c600f-114">`IsTrue`클래스 또는 구조체의 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="c600f-115">로의 축소 변환은 `Boolean?` 에서로의 변환이 포함 되지 않습니다 `Boolean` `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="c600f-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="c600f-116">클래스 또는 구조체에서로의 축소 변환 연산자 `Boolean` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="c600f-117">또는 연산자로의 변환이 정의 되지 않은 경우 `Boolean` `IsTrue` 컴파일러는 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c600f-118">`IsTrue`연산자를 *오버 로드할*수 있습니다. 즉, 해당 피연산자의 형식이 해당 클래스 또는 구조체의 형식인 경우 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="c600f-119">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c600f-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c600f-120">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c600f-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c600f-121">예제</span><span class="sxs-lookup"><span data-stu-id="c600f-121">Example</span></span>  
 <span data-ttu-id="c600f-122">다음 코드 예제에서는 및 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다 `IsFalse` `IsTrue` .</span><span class="sxs-lookup"><span data-stu-id="c600f-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="c600f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c600f-123">See also</span></span>

- [<span data-ttu-id="c600f-124">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="c600f-124">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="c600f-125">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="c600f-125">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="c600f-126">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="c600f-126">OrElse Operator</span></span>](orelse-operator.md)
