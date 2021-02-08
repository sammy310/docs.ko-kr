---
description: '다음에 대 한 자세한 정보: ^ = 연산자 (Visual Basic)'
title: ^= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 5894fdbedb411c6324a9355bd2d335bb6c6c5867
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773890"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="53775-103">^= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53775-103">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="53775-104">변수나 속성의 값을 식의 거듭제곱으로 올리고 결과를 다시 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="53775-104">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53775-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="53775-105">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="53775-106">부분</span><span class="sxs-lookup"><span data-stu-id="53775-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="53775-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="53775-107">Required.</span></span> <span data-ttu-id="53775-108">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="53775-108">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="53775-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="53775-109">Required.</span></span> <span data-ttu-id="53775-110">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="53775-110">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53775-111">설명</span><span class="sxs-lookup"><span data-stu-id="53775-111">Remarks</span></span>  

 <span data-ttu-id="53775-112">연산자의 좌 변에 있는 요소는 `^=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53775-112">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="53775-113">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53775-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="53775-114">연산자는 `^=` 먼저 연산자의 왼쪽에 있는 변수나 속성의 값을 식의 값 (연산자의 오른쪽에 있는)의 거듭제곱으로 올립니다.</span><span class="sxs-lookup"><span data-stu-id="53775-114">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="53775-115">그런 다음 연산자는 해당 작업의 결과를 변수 또는 속성에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="53775-115">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="53775-116">Visual Basic는 [Double 데이터 형식](../data-types/double-data-type.md)에서 항상 지 각 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53775-116">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="53775-117">다른 형식의 피연산자는로 변환 되 `Double` 고 결과는 항상 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="53775-117">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="53775-118">의 값은 `expression` 소수 자릿수, 음수 또는 둘 다 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53775-118">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="53775-119">오버로딩</span><span class="sxs-lookup"><span data-stu-id="53775-119">Overloading</span></span>  

 <span data-ttu-id="53775-120">[^ 연산자](exponentiation-operator.md) 는 *오버 로드* 될 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53775-120">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="53775-121">연산자를 오버 로드 하면 `^` 연산자의 동작에 영향을 줍니다 `^=` .</span><span class="sxs-lookup"><span data-stu-id="53775-121">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="53775-122">`^=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `^` 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53775-122">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="53775-123">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53775-123">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53775-124">예제</span><span class="sxs-lookup"><span data-stu-id="53775-124">Example</span></span>  

 <span data-ttu-id="53775-125">다음 예에서는 연산자를 사용 하 여 `^=` 한 변수의 값을 `Integer` 두 번째 변수의 거듭제곱으로 올리고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="53775-125">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="53775-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53775-126">See also</span></span>

- [<span data-ttu-id="53775-127">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="53775-127">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="53775-128">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="53775-128">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="53775-129">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="53775-129">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="53775-130">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="53775-130">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="53775-131">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="53775-131">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="53775-132">문</span><span class="sxs-lookup"><span data-stu-id="53775-132">Statements</span></span>](../../programming-guide/language-features/statements.md)
