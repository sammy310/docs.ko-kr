---
description: '다음에 대 한 자세한 정보:  >>= 연산자 (Visual Basic)'
title: '>>= 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 80f614042403ad9179de0025b289bd83c71008b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795315"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b20af-103">>>= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b20af-103">>>= Operator (Visual Basic)</span></span>

<span data-ttu-id="b20af-104">변수 또는 속성 값에서 산술 오른쪽 시프트를 수행 하 고 결과를 다시 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-104">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b20af-105">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="b20af-106">부분</span><span class="sxs-lookup"><span data-stu-id="b20af-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="b20af-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-107">Required.</span></span> <span data-ttu-id="b20af-108">정수 계열 형식 ( `SByte` , `Byte` ,,,,, `Short` `UShort` 또는 `Integer` )의 `UInteger` `Long` 변수 또는 속성 `ULong` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-108">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="b20af-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-109">Required.</span></span> <span data-ttu-id="b20af-110">로 확대 되는 데이터 형식의 숫자 식입니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="b20af-110">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b20af-111">설명</span><span class="sxs-lookup"><span data-stu-id="b20af-111">Remarks</span></span>  

 <span data-ttu-id="b20af-112">연산자의 좌 변에 있는 요소는 `>>=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-112">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b20af-113">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b20af-114">`>>=`연산자는 먼저 변수나 속성의 값에 대 한 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-114">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="b20af-115">그런 다음 연산자는 해당 작업의 결과를 변수 또는 속성에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-115">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="b20af-116">산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-116">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="b20af-117">산술 오른쪽 시프트에서 가장 오른쪽 비트 위치를 넘어 이동 하는 비트는 무시 되 고 맨 왼쪽 비트는 왼쪽의 비워진 비트 위치로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-117">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="b20af-118">즉 `variableorproperty` ,의 값이 음수 이면 비워진 위치가 1로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-118">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="b20af-119">`variableorproperty`가 양수인 경우 또는 해당 데이터 형식이 부호 없는 형식이 면 비워진 위치가 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-119">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b20af-120">오버로딩</span><span class="sxs-lookup"><span data-stu-id="b20af-120">Overloading</span></span>  

 <span data-ttu-id="b20af-121">[>> 연산자](right-shift-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-121">The [>> Operator](right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b20af-122">연산자를 오버 로드 하면 `>>` 연산자의 동작에 영향을 줍니다 `>>=` .</span><span class="sxs-lookup"><span data-stu-id="b20af-122">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="b20af-123">`>>=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `>>` 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-123">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b20af-124">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b20af-124">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20af-125">예제</span><span class="sxs-lookup"><span data-stu-id="b20af-125">Example</span></span>  

 <span data-ttu-id="b20af-126">다음 예에서는 연산자를 사용 `>>=` 하 여 변수의 비트 패턴을 `Integer` 지정 된 크기 만큼 오른쪽으로 이동 하 고 결과를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b20af-126">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="b20af-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b20af-127">See also</span></span>

- [<span data-ttu-id="b20af-128">>> 연산자</span><span class="sxs-lookup"><span data-stu-id="b20af-128">>> Operator</span></span>](right-shift-operator.md)
- [<span data-ttu-id="b20af-129">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="b20af-129">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="b20af-130">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="b20af-130">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="b20af-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="b20af-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b20af-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="b20af-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b20af-133">문</span><span class="sxs-lookup"><span data-stu-id="b20af-133">Statements</span></span>](../../programming-guide/language-features/statements.md)
