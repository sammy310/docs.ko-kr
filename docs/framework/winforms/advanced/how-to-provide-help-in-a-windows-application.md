---
title: '방법: Windows 애플리케이션에서 도움말 제공'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 2f9c0a9791db28cebd055ca446fdff16b9e276a4
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959614"
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="190c3-102">방법: Windows 애플리케이션에서 도움말 제공</span><span class="sxs-lookup"><span data-stu-id="190c3-102">How to: Provide Help in a Windows Application</span></span>

<span data-ttu-id="190c3-103">할 수 있습니다 사용 된 <xref:System.Windows.Forms.HelpProvider> Windows Forms에서 특정 컨트롤에 도움말 파일 내의 도움말 항목을 연결할 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-103">You can make use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="190c3-104">도움말 파일은 HTML 또는 HTMLHelp 1.x 이상의 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>

## <a name="provide-help"></a><span data-ttu-id="190c3-105">도움말 제공</span><span class="sxs-lookup"><span data-stu-id="190c3-105">Provide Help</span></span>

1. <span data-ttu-id="190c3-106">Visual Studio에서에서 **도구 상자**를 끌어는 <xref:System.Windows.Forms.HelpProvider> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-106">In Visual Studio, from the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>

     <span data-ttu-id="190c3-107">구성 요소가 Windows Forms 디자이너 아래쪽의 트레이너에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-107">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="190c3-108">에 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성을.chm,.col 또는.htm 도움말 파일로.</span><span class="sxs-lookup"><span data-stu-id="190c3-108">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>

3. <span data-ttu-id="190c3-109">폼에 있고에 다른 컨트롤을 선택 합니다 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-109">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>

     <span data-ttu-id="190c3-110">통과 하는 문자열을 <xref:System.Windows.Forms.HelpProvider> 해당 도움말 항목을 호출 하 여 도움말 파일에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-110">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>

4. <span data-ttu-id="190c3-111">에 **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 속성의 값을는 <xref:System.Windows.Forms.HelpNavigator> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>

     <span data-ttu-id="190c3-112">이 값은 **HelpKeyword** 속성이 도움말 시스템에 전달되는 방식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-112">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="190c3-113">다음 표에서는 가능한 설정과 해당 설명을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-113">The following table shows the possible settings and their descriptions.</span></span>

    |<span data-ttu-id="190c3-114">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="190c3-114">Member Name</span></span>|<span data-ttu-id="190c3-115">설명</span><span class="sxs-lookup"><span data-stu-id="190c3-115">Description</span></span>|
    |-----------------|-----------------|
    |<span data-ttu-id="190c3-116">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="190c3-116">AssociateIndex</span></span>|<span data-ttu-id="190c3-117">지정한 항목에 대한 인덱스가 지정한 URL에서 수행되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-117">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|
    |<span data-ttu-id="190c3-118">Find</span><span class="sxs-lookup"><span data-stu-id="190c3-118">Find</span></span>|<span data-ttu-id="190c3-119">지정한 URL의 검색 페이지가 표시되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-119">Specifies that the search page of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="190c3-120">인덱스</span><span class="sxs-lookup"><span data-stu-id="190c3-120">Index</span></span>|<span data-ttu-id="190c3-121">지정한 URL의 인덱스가 표시되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-121">Specifies that the index of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="190c3-122">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="190c3-122">KeywordIndex</span></span>|<span data-ttu-id="190c3-123">검색할 키워드와 지정한 URL에서 수행할 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-123">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|
    |<span data-ttu-id="190c3-124">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="190c3-124">TableOfContents</span></span>|<span data-ttu-id="190c3-125">HTML 1.0 도움말 파일의 목차가 표시되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-125">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|
    |<span data-ttu-id="190c3-126">항목</span><span class="sxs-lookup"><span data-stu-id="190c3-126">Topic</span></span>|<span data-ttu-id="190c3-127">지정한 URL에서 참조하는 항목이 표시되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-127">Specifies that the topic referenced by the specified URL is displayed.</span></span>|

 <span data-ttu-id="190c3-128">런타임에 F1 키를 누르면 때 컨트롤-설정한에 대 한 합니다 **HelpKeyword** 및 **HelpNavigator** 속성-에 포커스와 연결 된 도움말 파일이 열립니다 <xref:System.Windows.Forms.HelpProvider> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-128">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>

 <span data-ttu-id="190c3-129">현재는 **HelpNamespace** 속성은 다음 세 가지 형식 도움말 파일을 지원 합니다. HTMLHelp 1.x, HTMLHelp 2.0 및 HTML입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-129">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="190c3-130">따라서 **HelpNamespace** 속성을 웹 페이지와 같은 http:// 주소로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-130">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="190c3-131">이렇게 설정하면 앵커로 사용된 **HelpKeyword** 속성에 지정된 문자열이 있는 웹 페이지가 기본 브라우저에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-131">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="190c3-132">앵커는 HTML 페이지의 특정 부분으로 이동하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-132">The anchor is used to jump to a specific part of an HTML page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="190c3-133">클라이언트에서 보낸 정보는 애플리케이션에서 사용하기 전에 반드시 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-133">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="190c3-134">악의적인 사용자가 실행 스크립트, SQL 문 또는 다른 코드를 보내거나 삽입하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-134">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="190c3-135">사용자의 입력을 표시하거나 데이터베이스에 저장하거나 사용하기 전에 잠재적으로 안전하지 않은 정보가 포함되어 있지 않은지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-135">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="190c3-136">일반적인 검사 방법은 사용자가 입력을 받을 때 정규식을 사용하여 "SCRIPT"와 같은 키워드를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-136">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>

<span data-ttu-id="190c3-137">사용할 수도 있습니다는 <xref:System.Windows.Forms.HelpProvider> 에 Windows Forms에서 컨트롤에 대 한 도움말 파일을 표시 하도록 구성 된 경우에 팝업 도움말을 표시할 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-137">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="190c3-138">자세한 내용은 [방법: 팝업 도움말 표시](how-to-display-pop-up-help.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="190c3-138">For more information, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="190c3-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="190c3-139">See also</span></span>

- [<span data-ttu-id="190c3-140">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="190c3-140">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)
- [<span data-ttu-id="190c3-141">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="190c3-141">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="190c3-142">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="190c3-142">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="190c3-143">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="190c3-143">Windows Forms</span></span>](../index.md)
