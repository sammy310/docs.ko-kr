---
title: 코딩 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: eae283c757ddeb1290c15d82a41c8028a8941e63
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059160"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="13e19-102">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="13e19-102">Visual Basic Coding Conventions</span></span>

<span data-ttu-id="13e19-103">Microsoft는이 항목의 지침을 따르는 샘플과 설명서를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="13e19-104">동일한 코딩 규칙을 따르는 경우 다음과 같은 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="13e19-105">코드는 일관 된 모양을 가지 므로, 독자가 레이아웃을 통해 콘텐츠를 더 잘 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="13e19-106">독자가 이전 환경을 기반으로 가정을 할 수 있으므로 코드를 더 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="13e19-107">코드를 보다 쉽게 복사, 변경 및 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="13e19-108">코드에서 Visual Basic에 대 한 "최선의 구현 방법"을 보여 주는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="13e19-109">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="13e19-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="13e19-110">이름 지정 지침에 대 한 자세한 내용은 [명명 지침](../../../standard/design-guidelines/naming-guidelines.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13e19-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="13e19-111">변수 이름의 일부로 "My" 또는 "my"를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13e19-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="13e19-112">이 연습에서는 개체와 혼동을 만듭니다 `My` .</span><span class="sxs-lookup"><span data-stu-id="13e19-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="13e19-113">자동 생성 된 코드에서 개체의 이름을 변경 하 여 지침에 맞게 만들 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="13e19-114">레이아웃 규칙</span><span class="sxs-lookup"><span data-stu-id="13e19-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="13e19-115">탭을 공백으로 삽입 하 고 4 개의 공백 들여쓰기로 스마트 들여쓰기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="13e19-116">코드를 쉽게 **나열 (다시 포맷)** 하 여 코드 편집기에서 코드를 다시 포맷 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="13e19-117">자세한 내용은 [옵션, 텍스트 편집기, 기본 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13e19-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="13e19-118">줄 마다 문을 하나만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-118">Use only one statement per line.</span></span> <span data-ttu-id="13e19-119">Visual Basic 줄 구분 기호 문자 (:)를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="13e19-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="13e19-120">암시적 줄 연속 문자 "_"를 사용 하 여 언어에서 허용 하는 모든 위치에서 암시적 줄 연속을 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="13e19-121">한 줄에 하나의 선언만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="13e19-122">**코드의 표시 (다시 포맷)** 가 연속 줄을 자동으로 서식 지정 하지 않는 경우 연속 줄을 탭 정지 하나 만큼 수동으로 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="13e19-123">그러나 항상 목록의 항목을 왼쪽에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="13e19-124">메서드와 속성 정의 사이에 하나 이상의 빈 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="13e19-125">주석 규칙</span><span class="sxs-lookup"><span data-stu-id="13e19-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="13e19-126">코드 줄의 끝이 아닌 별도의 줄에 주석을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="13e19-127">주석 텍스트는 대문자로 시작 하 고 주석 텍스트는 마침표를 사용 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="13e19-128">주석 구분 기호 (')와 주석 텍스트 사이에 공백을 하나 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="13e19-129">서식이 지정 된 별표 블록으로 주석을 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="13e19-130">프로그램 구조</span><span class="sxs-lookup"><span data-stu-id="13e19-130">Program Structure</span></span>  
  
- <span data-ttu-id="13e19-131">메서드를 사용 하는 경우 `Main` 새 콘솔 응용 프로그램에 대 한 기본 구문을 사용 하 고 `My` 명령줄 인수에를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="13e19-132">언어 지침</span><span class="sxs-lookup"><span data-stu-id="13e19-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="13e19-133">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13e19-133">String Data Type</span></span>  
  
- <span data-ttu-id="13e19-134">다음 코드에 나와 있는 것처럼 [문자열 보간](../language-features/strings/interpolated-strings.md)을 사용하여 짧은 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-134">Use [string interpolation](../language-features/strings/interpolated-strings.md) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="13e19-135">루프에서 문자열을 추가 하려면 개체를 사용 <xref:System.Text.StringBuilder> 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="13e19-136">이벤트 처리기의 완화 대리자</span><span class="sxs-lookup"><span data-stu-id="13e19-136">Relaxed Delegates in Event Handlers</span></span>  

 <span data-ttu-id="13e19-137">인수 (개체 및 EventArgs)를 이벤트 처리기로 명시적으로 한정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13e19-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="13e19-138">이벤트에 전달 되는 이벤트 인수를 사용 하지 않는 경우 (예: sender as Object, e를 EventArgs로), 완화 된 대리자를 사용 하 고 이벤트 인수를 코드에 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="13e19-139">부호 없는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13e19-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="13e19-140">`Integer`필요한 경우를 제외 하 고는 부호 없는 형식 대신을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="13e19-141">배열</span><span class="sxs-lookup"><span data-stu-id="13e19-141">Arrays</span></span>  
  
- <span data-ttu-id="13e19-142">선언 줄에서 배열을 초기화할 때는 간단한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="13e19-143">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="13e19-144">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13e19-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="13e19-145">변수가 아니라 형식에 배열 지정자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="13e19-146">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="13e19-147">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13e19-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="13e19-148">기본 데이터 형식의 배열을 선언 하 고 초기화할 때 {} 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="13e19-149">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="13e19-150">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13e19-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="13e19-151">With 키워드 사용</span><span class="sxs-lookup"><span data-stu-id="13e19-151">Use the With Keyword</span></span>  

 <span data-ttu-id="13e19-152">하나의 개체에 대 한 일련의 호출을 수행 하는 경우 키워드를 사용 하는 것이 좋습니다 `With` .</span><span class="sxs-lookup"><span data-stu-id="13e19-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="13e19-153">Try ...를 사용 합니다. 예외 처리를 사용 하는 경우 문 Catch 및 사용</span><span class="sxs-lookup"><span data-stu-id="13e19-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  

 <span data-ttu-id="13e19-154">`On Error Goto`는 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="13e19-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="13e19-155">IsNot 키워드 사용</span><span class="sxs-lookup"><span data-stu-id="13e19-155">Use the IsNot Keyword</span></span>  

 <span data-ttu-id="13e19-156">`IsNot`대신 키워드를 사용 `Not...Is Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="13e19-157">New 키워드</span><span class="sxs-lookup"><span data-stu-id="13e19-157">New Keyword</span></span>  
  
- <span data-ttu-id="13e19-158">약식 인스턴스화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-158">Use short instantiation.</span></span> <span data-ttu-id="13e19-159">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="13e19-160">위의 줄은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="13e19-161">매개 변수가 없는 생성자 대신 새 개체에 대 한 개체 이니셜라이저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="13e19-162">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="13e19-162">Event Handling</span></span>  
  
- <span data-ttu-id="13e19-163">대신 `Handles` 를 사용 합니다 `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="13e19-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="13e19-164">`AddressOf`를 사용 하 고 대리자를 명시적으로 인스턴스화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="13e19-165">이벤트를 정의할 때는 간단한 구문을 사용 하 고 컴파일러가 대리자를 정의 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="13e19-166">`Nothing`메서드를 호출 하기 전에 이벤트가 (null) 인지 여부를 확인 하지 않습니다 `RaiseEvent` .</span><span class="sxs-lookup"><span data-stu-id="13e19-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="13e19-167">`RaiseEvent``Nothing`이벤트를 발생 시키기 전에를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="13e19-168">공유 멤버 사용</span><span class="sxs-lookup"><span data-stu-id="13e19-168">Using Shared Members</span></span>  

 <span data-ttu-id="13e19-169">`Shared`인스턴스 변수가 아니라 클래스 이름을 사용 하 여 멤버를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="13e19-170">XML 리터럴 사용</span><span class="sxs-lookup"><span data-stu-id="13e19-170">Use XML Literals</span></span>  

 <span data-ttu-id="13e19-171">XML 리터럴은 XML로 작업할 때 가장 자주 발생 하는 작업 (예: 로드, 쿼리 및 변환)을 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="13e19-172">XML을 사용 하 여 개발 하는 경우 다음 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="13e19-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="13e19-173">Xml Api를 직접 호출 하는 대신 xml 리터럴을 사용 하 여 XML 문서 및 조각을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="13e19-174">XML 리터럴에 대 한 성능 최적화를 활용 하려면 파일 또는 프로젝트 수준에서 XML 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="13e19-175">Xml 축 속성을 사용 하 여 XML 문서의 요소 및 특성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="13e19-176">메서드와 같은 API 호출을 사용 하는 대신 포함 식을 사용 하 여 값을 포함 하 고 기존 값에서 XML을 만듭니다 `Add` .</span><span class="sxs-lookup"><span data-stu-id="13e19-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="13e19-177">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="13e19-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="13e19-178">쿼리 변수에 의미 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="13e19-179">쿼리의 요소 이름을 지정 하 여 익명 형식의 속성 이름이 파스칼식 대/소문자를 사용 하 여 올바르게 대문자로 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="13e19-180">결과의 속성 이름이 모호하면 속성 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="13e19-181">예를 들어 쿼리에서 고객 이름과 주문 ID를 반환 하는 경우 `Name` 결과에서 및로 유지 하는 대신 이름을 바꿉니다 `ID` .</span><span class="sxs-lookup"><span data-stu-id="13e19-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="13e19-182">쿼리 변수 및 범위 변수의 선언에서 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="13e19-183">문 아래의 쿼리 절을 정렬 합니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="13e19-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="13e19-184">`Where`이후 쿼리 절이 필터링 된 데이터 집합에 대해 작동 하도록 다른 쿼리 절 앞에 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e19-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="13e19-185">절을 사용 하 여 조인 작업을 암시적으로 정의 하는 대신 절을 사용 하 여 `Join` 조인 작업을 명시적으로 정의 합니다 `Where` .</span><span class="sxs-lookup"><span data-stu-id="13e19-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="13e19-186">참조</span><span class="sxs-lookup"><span data-stu-id="13e19-186">See also</span></span>

- [<span data-ttu-id="13e19-187">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="13e19-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
