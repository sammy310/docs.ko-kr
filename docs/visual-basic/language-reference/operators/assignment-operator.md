---
description: '다음에 대 한 자세한 정보: = 연산자 (Visual Basic)'
title: = 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 3cf45fb93bf5138f9e7fa5a43650019ab58674fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774254"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e40c8-103">= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e40c8-103">= Operator (Visual Basic)</span></span>

<span data-ttu-id="e40c8-104">변수 또는 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-104">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40c8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e40c8-105">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="e40c8-106">부분</span><span class="sxs-lookup"><span data-stu-id="e40c8-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="e40c8-107">쓰기 가능한 변수 또는 모든 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-107">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="e40c8-108">모든 리터럴, 상수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-108">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e40c8-109">설명</span><span class="sxs-lookup"><span data-stu-id="e40c8-109">Remarks</span></span>  

 <span data-ttu-id="e40c8-110">등호 ()의 왼쪽에 있는 요소는 `=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-110">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e40c8-111">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-111">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="e40c8-112">`=`연산자는 오른쪽의 값을 왼쪽에 있는 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-112">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e40c8-113">`=`연산자는 비교 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-113">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="e40c8-114">자세한 내용은 [비교 연산자](comparison-operators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e40c8-114">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e40c8-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="e40c8-115">Overloading</span></span>  

 <span data-ttu-id="e40c8-116">`=`연산자는 할당 연산자가 아닌 관계형 비교 연산자로만 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-116">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="e40c8-117">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e40c8-117">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e40c8-118">예제</span><span class="sxs-lookup"><span data-stu-id="e40c8-118">Example</span></span>  

 <span data-ttu-id="e40c8-119">다음 예에서는 대입 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-119">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="e40c8-120">오른쪽의 값이 왼쪽의 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e40c8-120">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="e40c8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e40c8-121">See also</span></span>

- [<span data-ttu-id="e40c8-122">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-122">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="e40c8-123">\* = 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-123">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="e40c8-124">+ = 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-124">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="e40c8-125">-= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e40c8-125">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="e40c8-126">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e40c8-126">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="e40c8-127">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-127">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="e40c8-128">^ = 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-128">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="e40c8-129">문</span><span class="sxs-lookup"><span data-stu-id="e40c8-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="e40c8-130">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="e40c8-130">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="e40c8-131">읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e40c8-131">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="e40c8-132">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="e40c8-132">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
