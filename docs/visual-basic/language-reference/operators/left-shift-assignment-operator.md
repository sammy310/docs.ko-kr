---
title: < < = 연산자 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: aae71069bdcb88efa5842526dd7eb47806f248d0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701101"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="70fae-102">\< @ no__t = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70fae-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="70fae-103">변수 또는 속성 값에서 산술 왼쪽 시프트를 수행 하 고 결과를 다시 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70fae-104">구문</span><span class="sxs-lookup"><span data-stu-id="70fae-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="70fae-105">요소</span><span class="sxs-lookup"><span data-stu-id="70fae-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="70fae-106">필수.</span><span class="sxs-lookup"><span data-stu-id="70fae-106">Required.</span></span> <span data-ttu-id="70fae-107">정수 계열 형식의 변수 또는 속성 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `ULong`).</span><span class="sxs-lookup"><span data-stu-id="70fae-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="70fae-108">필수.</span><span class="sxs-lookup"><span data-stu-id="70fae-108">Required.</span></span> <span data-ttu-id="70fae-109">@No__t-0으로 확대 되는 데이터 형식의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70fae-110">설명</span><span class="sxs-lookup"><span data-stu-id="70fae-110">Remarks</span></span>  
 <span data-ttu-id="70fae-111">@No__t-0 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="70fae-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="70fae-113">@No__t-0 연산자는 먼저 변수나 속성의 값에 산술 왼쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="70fae-114">그런 다음 연산자는 해당 작업의 결과를 해당 변수 또는 속성에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="70fae-115">산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="70fae-116">산술 왼쪽 시프트에서 결과 데이터 형식의 범위를 벗어나 이동 하는 비트는 무시 되 고 오른쪽에서 비워진 비트 위치는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="70fae-117">오버로딩</span><span class="sxs-lookup"><span data-stu-id="70fae-117">Overloading</span></span>  
 <span data-ttu-id="70fae-118">[< < 연산자](../../../visual-basic/language-reference/operators/left-shift-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식이 면 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="70fae-119">@No__t-0 연산자를 오버 로드 하면 `<<=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="70fae-120">코드에서-1 @no__t 오버 로드 하는 클래스 또는 구조체에 `<<=`을 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="70fae-121">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fae-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70fae-122">예제</span><span class="sxs-lookup"><span data-stu-id="70fae-122">Example</span></span>  
 <span data-ttu-id="70fae-123">다음 예에서는 `<<=` 연산자를 사용 하 여 @no__t 1 변수의 비트 패턴을 지정한 양만큼 왼쪽으로 이동 하 고 결과를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fae-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="70fae-124">참조</span><span class="sxs-lookup"><span data-stu-id="70fae-124">See also</span></span>

- [<span data-ttu-id="70fae-125"><< 연산자</span><span class="sxs-lookup"><span data-stu-id="70fae-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="70fae-126">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="70fae-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="70fae-127">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="70fae-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="70fae-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="70fae-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="70fae-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="70fae-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="70fae-130">문(C++)</span><span class="sxs-lookup"><span data-stu-id="70fae-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
