---
description: '자세히 알아보기: 방법: 연산자를 정의 하는 클래스 사용 (Visual Basic)'
title: '방법: 연산자를 정의하는 클래스 사용'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 4bf5321fbf1868ad0214d0f4781df30dc8f92ac9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455745"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="2b2b1-103">방법: 연산자를 정의하는 클래스 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b2b1-103">How to: Use a Class that Defines Operators (Visual Basic)</span></span>

<span data-ttu-id="2b2b1-104">자체 연산자를 정의 하는 클래스 또는 구조체를 사용 하는 경우 Visual Basic에서 해당 연산자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-104">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="2b2b1-105">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-105">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b2b1-106">예</span><span class="sxs-lookup"><span data-stu-id="2b2b1-106">Example</span></span>  

 <span data-ttu-id="2b2b1-107">다음 예에서는 sql <xref:System.Data.SqlTypes.SqlString> 문자열과 Visual Basic 문자열 사이에서 양방향으로 변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))를 정의 하는 sql 구조에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-107">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="2b2b1-108">Sql 문자열 식을 사용 하 여 `CType(`  `String)` sql 문자열을 Visual Basic 문자열로 변환 하 고 `CType(` *문자열 식을 Visual Basic* 하 여 <xref:System.Data.SqlTypes.SqlString> `)` 다른 방향으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-108">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2b2b1-109"><xref:System.Data.SqlTypes.SqlString>구조는에서로 변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))를 정의 하 `String` <xref:System.Data.SqlTypes.SqlString> 고 다른에서 <xref:System.Data.SqlTypes.SqlString> 로 변환 `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-109">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="2b2b1-110">에를 할당 하는 문은 `title` `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출은 두 번째 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-110">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="2b2b1-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2b2b1-111">Compile the code</span></span>  

 <span data-ttu-id="2b2b1-112">사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-112">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="2b2b1-113">클래스 또는 구조체에서 오버 로드에 사용할 수 있는 모든 연산자를 정의 했다고 가정해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-113">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="2b2b1-114">사용 가능한 연산자 목록은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-114">For a list of available operators, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="2b2b1-115">`Imports`소스 파일의 시작 부분에 SQL 문자열에 대 한 적절 한 문을 포함 합니다 (이 경우 <xref:System.Data.SqlTypes> ).</span><span class="sxs-lookup"><span data-stu-id="2b2b1-115">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="2b2b1-116">프로젝트에는 System.object와 System.XML에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-116">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2b1-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2b2b1-117">See also</span></span>

- [<span data-ttu-id="2b2b1-118">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="2b2b1-118">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="2b2b1-119">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="2b2b1-119">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="2b2b1-120">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="2b2b1-120">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="2b2b1-121">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="2b2b1-121">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="2b2b1-122">Widening</span><span class="sxs-lookup"><span data-stu-id="2b2b1-122">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="2b2b1-123">Narrowing</span><span class="sxs-lookup"><span data-stu-id="2b2b1-123">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="2b2b1-124">Structure 문</span><span class="sxs-lookup"><span data-stu-id="2b2b1-124">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="2b2b1-125">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="2b2b1-125">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="2b2b1-126">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="2b2b1-126">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="2b2b1-127">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="2b2b1-127">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
