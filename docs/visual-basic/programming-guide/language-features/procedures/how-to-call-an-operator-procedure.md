---
title: '방법: 연산자 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: 0e88ff7b36535a709671a1f9b838f2b4488d1d37
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075189"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="191db-102">방법: 연산자 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="191db-102">How to: Call an Operator Procedure (Visual Basic)</span></span>

<span data-ttu-id="191db-103">식에서 연산자 기호를 사용 하 여 연산자 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="191db-104">변환 연산자의 경우 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 호출 하 여 값을 한 데이터 형식에서 다른 데이터 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-104">In the case of a conversion operator, you call the [CType Function](../../../language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="191db-105">연산자 프로시저를 명시적으로 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="191db-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="191db-106">`CType`일반적으로 연산자를 사용 하는 것과 같은 방법으로 연산자 또는 함수를 대입문 또는 식에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="191db-107">Visual Basic 연산자 프로시저에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="191db-108">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="191db-109">연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="191db-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="191db-110">일반적인 방법으로 식에 연산자 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="191db-111">피연산자의 데이터 형식이 연산자에 적합 하 고 올바른 순서로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="191db-112">연산자는 예상 대로 식의 값에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="191db-113">변환 연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="191db-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="191db-114">`CType`식 내에서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="191db-115">피연산자의 데이터 형식이 변환에 적합 하 고 올바른 순서 대로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="191db-116">`CType` 변환 연산자 프로시저를 호출 하 고 변환 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="191db-117">예제</span><span class="sxs-lookup"><span data-stu-id="191db-117">Example</span></span>  

 <span data-ttu-id="191db-118">다음 예에서는 두 개의 <xref:System.TimeSpan> 구조체를 만들고 함께 추가 하 고 그 결과를 세 번째 구조에 저장 합니다 <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="191db-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="191db-119"><xref:System.TimeSpan>구조는 여러 표준 연산자를 오버 로드 하는 연산자 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="191db-120">는 <xref:System.TimeSpan> 표준 연산자를 오버 로드 하기 때문에 `+` 이전 예에서는의 값을 계산할 때 연산자 프로시저를 호출 합니다 `combinedSpan` .</span><span class="sxs-lookup"><span data-stu-id="191db-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="191db-121">대화 연산자 프로시저를 호출 하는 예제는 [방법: 연산자를 정의 하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="191db-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="191db-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="191db-122">Compile the code</span></span>  

 <span data-ttu-id="191db-123">사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="191db-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191db-124">참조</span><span class="sxs-lookup"><span data-stu-id="191db-124">See also</span></span>

- [<span data-ttu-id="191db-125">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="191db-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="191db-126">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="191db-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="191db-127">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="191db-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="191db-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="191db-128">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="191db-129">Widening</span><span class="sxs-lookup"><span data-stu-id="191db-129">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="191db-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="191db-130">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="191db-131">Structure 문</span><span class="sxs-lookup"><span data-stu-id="191db-131">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="191db-132">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="191db-132">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="191db-133">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="191db-133">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="191db-134">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="191db-134">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
