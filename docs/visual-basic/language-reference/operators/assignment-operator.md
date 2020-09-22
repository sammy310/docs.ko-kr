---
title: = 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874819"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d6e90-102">= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6e90-102">= Operator (Visual Basic)</span></span>

<span data-ttu-id="d6e90-103">변수 또는 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e90-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6e90-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="d6e90-105">부분</span><span class="sxs-lookup"><span data-stu-id="d6e90-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="d6e90-106">쓰기 가능한 변수 또는 모든 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="d6e90-107">모든 리터럴, 상수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e90-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6e90-108">Remarks</span></span>  

 <span data-ttu-id="d6e90-109">등호 ()의 왼쪽에 있는 요소는 `=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d6e90-110">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="d6e90-111">`=`연산자는 오른쪽의 값을 왼쪽에 있는 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6e90-112">`=`연산자는 비교 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="d6e90-113">자세한 내용은 [비교 연산자](comparison-operators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e90-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d6e90-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6e90-114">Overloading</span></span>  

 <span data-ttu-id="d6e90-115">`=`연산자는 할당 연산자가 아닌 관계형 비교 연산자로만 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="d6e90-116">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e90-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6e90-117">예제</span><span class="sxs-lookup"><span data-stu-id="d6e90-117">Example</span></span>  

 <span data-ttu-id="d6e90-118">다음 예에서는 대입 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="d6e90-119">오른쪽의 값이 왼쪽의 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e90-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d6e90-120">참조</span><span class="sxs-lookup"><span data-stu-id="d6e90-120">See also</span></span>

- [<span data-ttu-id="d6e90-121">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="d6e90-122">\* = 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="d6e90-123">+ = 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="d6e90-124">-= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6e90-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="d6e90-125">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6e90-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="d6e90-126">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="d6e90-127">^ = 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="d6e90-128">문</span><span class="sxs-lookup"><span data-stu-id="d6e90-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="d6e90-129">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e90-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="d6e90-130">읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d6e90-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="d6e90-131">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="d6e90-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
