---
title: '\= 연산자'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330953"
---
# <a name="-operator"></a><span data-ttu-id="d70ab-102">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="d70ab-102">\\= Operator</span></span>
<span data-ttu-id="d70ab-103">변수 또는 속성의 값을 식의 값으로 나누고 정수 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="d70ab-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d70ab-105">요소</span><span class="sxs-lookup"><span data-stu-id="d70ab-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="d70ab-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d70ab-106">Required.</span></span> <span data-ttu-id="d70ab-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="d70ab-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d70ab-108">Required.</span></span> <span data-ttu-id="d70ab-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d70ab-110">설명</span><span class="sxs-lookup"><span data-stu-id="d70ab-110">Remarks</span></span>  
 <span data-ttu-id="d70ab-111">`\=` 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d70ab-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="d70ab-113">`\=` 연산자는 왼쪽에 있는 변수나 속성의 값을 오른쪽의 값으로 나누고 정수 결과를 왼쪽의 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="d70ab-114">정수 나누기에 대 한 자세한 내용은 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d70ab-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d70ab-115">오버로드</span><span class="sxs-lookup"><span data-stu-id="d70ab-115">Overloading</span></span>  
 <span data-ttu-id="d70ab-116">`\` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d70ab-117">`\` 연산자를 오버 로드 하면 `\=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="d70ab-118">코드에서 `\`오버 로드 하는 클래스 또는 구조체에 `\=`를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d70ab-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d70ab-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d70ab-120">예제</span><span class="sxs-lookup"><span data-stu-id="d70ab-120">Example</span></span>  
 <span data-ttu-id="d70ab-121">다음 예에서는 `\=` 연산자를 사용 하 여 하나의 `Integer` 변수를 초당 나누고 정수 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="d70ab-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="d70ab-122">See also</span></span>

- [<span data-ttu-id="d70ab-123">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d70ab-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="d70ab-124">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d70ab-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="d70ab-125">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="d70ab-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="d70ab-126">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="d70ab-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="d70ab-127">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="d70ab-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d70ab-128">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="d70ab-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d70ab-129">문</span><span class="sxs-lookup"><span data-stu-id="d70ab-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
