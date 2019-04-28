---
title: '&amp;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: a79e779d8fcf549daeabc494e0a55deee30b5d22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608439"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="9f2dc-102">&amp;= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f2dc-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="9f2dc-103">연결을 `String` 식을 `String` 변수 또는 속성 결과 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f2dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f2dc-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9f2dc-105">요소</span><span class="sxs-lookup"><span data-stu-id="9f2dc-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9f2dc-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-106">Required.</span></span> <span data-ttu-id="9f2dc-107">모든 `String` 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="9f2dc-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-108">Required.</span></span> <span data-ttu-id="9f2dc-109">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f2dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="9f2dc-110">Remarks</span></span>  
 <span data-ttu-id="9f2dc-111">왼쪽된에 있는 요소는 `&=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9f2dc-112">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="9f2dc-113">`&=` 연산자는 연결을 `String` 는 오른쪽에 식이 `String` 변수나 속성 왼쪽에 결과 변수 또는 왼쪽의 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9f2dc-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="9f2dc-114">Overloading</span></span>  
 <span data-ttu-id="9f2dc-115">합니다 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9f2dc-116">오버 로드 된 `&` 연산자의 동작에 영향을 줍니다는 `&=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="9f2dc-117">코드를 사용 하는 경우 `&=` 클래스나 구조체에 오버 로드에서 `&`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9f2dc-118">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f2dc-119">예제</span><span class="sxs-lookup"><span data-stu-id="9f2dc-119">Example</span></span>  
 <span data-ttu-id="9f2dc-120">다음 예제에서는 합니다 `&=` 두 연결 연산자 `String` 변수 및 결과 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2dc-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9f2dc-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f2dc-121">See also</span></span>

- [<span data-ttu-id="9f2dc-122">& 연산자</span><span class="sxs-lookup"><span data-stu-id="9f2dc-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="9f2dc-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="9f2dc-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="9f2dc-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="9f2dc-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="9f2dc-125">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="9f2dc-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="9f2dc-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="9f2dc-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9f2dc-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="9f2dc-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9f2dc-128">문(C++)</span><span class="sxs-lookup"><span data-stu-id="9f2dc-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
