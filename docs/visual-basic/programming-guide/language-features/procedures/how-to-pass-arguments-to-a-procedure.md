---
title: '방법: 프로시저에 인수 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344840"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="b49e5-102">방법: 프로시저에 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e5-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="b49e5-103">프로시저를 호출할 때 인수 목록이 있는 프로시저 이름을 괄호 안에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="b49e5-104">프로시저에서 정의 하는 모든 필수 매개 변수에 해당 하는 인수를 제공 하 고 선택적으로 `Optional` 매개 변수에 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="b49e5-105">호출에 `Optional` 매개 변수를 제공 하지 않는 경우 후속 인수를 제공 하는 경우 인수 목록에 쉼표를 포함 하 여 해당 자리를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="b49e5-106">`String``Byte`와 같이 해당 매개 변수와 다른 데이터 형식의 인수를 전달 하려는 경우 형식 확인 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))를 `Off`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="b49e5-107">`Option Strict` `On`경우 확대 변환 또는 명시적 변환 키워드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="b49e5-108">자세한 내용은 [확대 및 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b49e5-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="b49e5-109">자세한 내용은 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b49e5-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="b49e5-110">프로시저에 하나 이상의 인수를 전달 하려면</span><span class="sxs-lookup"><span data-stu-id="b49e5-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="b49e5-111">호출 문에서 괄호를 사용 하 여 프로시저 이름을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="b49e5-112">괄호 안에 인수 목록을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="b49e5-113">프로시저에서 정의 하는 각 필수 매개 변수에 대 한 인수를 포함 하 고 인수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="b49e5-114">각 인수가 해당 매개 변수에 대해 프로시저에서 정의 하는 형식으로 변환할 수 있는 데이터 형식으로 계산 되는 유효한 식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="b49e5-115">매개 변수가 [선택적](../../../../visual-basic/language-reference/modifiers/optional.md)으로 정의 된 경우 인수 목록에 포함 하거나 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="b49e5-116">생략 하면 프로시저는 해당 매개 변수에 대해 정의 된 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="b49e5-117">`Optional` 매개 변수에 대 한 인수를 생략 하 고 매개 변수 목록에 다른 매개 변수가 있는 경우 인수 목록에서 생략 된 인수의 자리를 추가 쉼표로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="b49e5-118">다음 예에서는 Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="b49e5-119">앞의 예제에서는 표시 되는 메시지 문자열인 필수 첫 번째 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="b49e5-120">메시지 상자에 표시할 단추를 지정 하는 선택적 두 번째 매개 변수에 대 한 인수를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="b49e5-121">호출에서 값을 제공 하지 않기 때문에 `MsgBox`는 기본값 `MsgBoxStyle.OKOnly`를 사용 합니다 .이 값은 **확인** 단추만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="b49e5-122">인수 목록에서 두 번째 쉼표는 생략 된 두 번째 인수의 자리를 표시 하 고, 마지막 문자열은 제목 표시줄에 표시 될 텍스트인 `MsgBox`의 선택적 세 번째 매개 변수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49e5-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49e5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b49e5-123">See also</span></span>

- [<span data-ttu-id="b49e5-124">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="b49e5-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b49e5-125">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="b49e5-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="b49e5-126">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="b49e5-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b49e5-127">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="b49e5-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b49e5-128">방법: 프로시저의 매개 변수 정의</span><span class="sxs-lookup"><span data-stu-id="b49e5-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="b49e5-129">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b49e5-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b49e5-130">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="b49e5-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="b49e5-131">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="b49e5-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="b49e5-132">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="b49e5-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="b49e5-133">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49e5-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
