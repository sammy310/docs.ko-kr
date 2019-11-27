---
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
ms.openlocfilehash: 9ec4b4c07910100dd02cc86e882b44aa7dbd2ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346046"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="7fce4-102">방법: 연산자를 정의하는 클래스 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fce4-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="7fce4-103">자체 연산자를 정의 하는 클래스 또는 구조체를 사용 하는 경우 Visual Basic에서 해당 연산자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="7fce4-104">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fce4-105">예제</span><span class="sxs-lookup"><span data-stu-id="7fce4-105">Example</span></span>  
 <span data-ttu-id="7fce4-106">다음 예에서는 sql 문자열과 Visual Basic 문자열 사이에서 양방향으로 변환 연산자 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 정의 하는 sql 구조 <xref:System.Data.SqlTypes.SqlString>에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="7fce4-107">Sql 문자열 *식*`CType(`를 사용 하 여 sql 문자열을 Visual Basic 문자열로 변환 하 고 Visual Basic *문자열 식*`CType(`<xref:System.Data.SqlTypes.SqlString>를 사용 하 여 다른 방향으로 변환할 `String)` 있습니다.`)`</span><span class="sxs-lookup"><span data-stu-id="7fce4-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="7fce4-108"><xref:System.Data.SqlTypes.SqlString> 구조는 `String`에서 <xref:System.Data.SqlTypes.SqlString> 사이에 변환 연산자 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 정의 하 고 다른 <xref:System.Data.SqlTypes.SqlString>에서 `String`로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="7fce4-109">`jobTitle`에 `title`를 할당 하는 문은 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출은 두 번째 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fce4-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7fce4-110">Compiling the Code</span></span>  
 <span data-ttu-id="7fce4-111">사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="7fce4-112">클래스 또는 구조체에서 오버 로드에 사용할 수 있는 모든 연산자를 정의 했다고 가정해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="7fce4-113">사용 가능한 연산자 목록은 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fce4-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="7fce4-114">소스 파일의 시작 부분에 SQL 문자열에 대 한 적절 한 `Imports` 문을 포함 합니다 (이 경우 <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="7fce4-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="7fce4-115">프로젝트에는 System.object 및 SYSTEM.XML에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fce4-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fce4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fce4-116">See also</span></span>

- [<span data-ttu-id="7fce4-117">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="7fce4-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="7fce4-118">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="7fce4-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="7fce4-119">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="7fce4-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="7fce4-120">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="7fce4-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="7fce4-121">확장</span><span class="sxs-lookup"><span data-stu-id="7fce4-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="7fce4-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="7fce4-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="7fce4-123">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7fce4-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7fce4-124">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="7fce4-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7fce4-125">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="7fce4-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="7fce4-126">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="7fce4-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
