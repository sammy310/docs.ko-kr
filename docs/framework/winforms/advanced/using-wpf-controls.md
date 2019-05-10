---
title: WPF 컨트롤 사용
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211309"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="151fb-102">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="151fb-102">Use WPF controls</span></span>

<span data-ttu-id="151fb-103">Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation (WPF) 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="151fb-104">이러한 옵션은 두 가지 서로 다른 뷰 기술, 상호 운용 될 원활 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="151fb-105">Visual Studio에서 Windows Forms 디자이너에는 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="151fb-106">WPF 컨트롤 이라고 하는 특수 한 Windows Forms 컨트롤에서 호스팅하는 <xref:System.Windows.Forms.Integration.ElementHost>합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="151fb-107">이 컨트롤을 WPF 컨트롤을 폼의 레이아웃에 관여 하는 데 키보드 및 마우스 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="151fb-108">디자인 타임에 정렬할 수 있습니다는 <xref:System.Windows.Forms.Integration.ElementHost> 방법과 마찬가지로 모든 Windows Forms 컨트롤을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="151fb-109">또한 WPF 기반 응용 프로그램에서 Windows Forms 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="151fb-110">자세한 내용은 [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="151fb-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="151fb-111">In This Section</span></span>

<span data-ttu-id="151fb-112">[방법: 복사 하 고 디자인 타임에 ElementHost 컨트롤을 붙여 넣습니다.](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="151fb-113">Windows Form에 Windows Presentation Foundation 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="151fb-114">[연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="151fb-115">Windows Presentation Foundation 컨트롤을 정렬 하려면 고정 및 맞춤선 등의 Windows Forms 레이아웃 기능을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="151fb-116">[연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="151fb-117">Windows Forms 기반 응용 프로그램에서 사용 하기 위해 Windows Presentation Foundation 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="151fb-118">[연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="151fb-119">폼에 표시 하려는 Windows Presentation Foundation 컨트롤 유형을 선택 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="151fb-120">[연습: WPF 콘텐츠 스타일 지정](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="151fb-121">Windows Forms 디자이너 간의 워크플로 보여 줍니다. 및 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] Windows Presentation Foundation 컨트롤에 스타일을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="151fb-122">참조</span><span class="sxs-lookup"><span data-stu-id="151fb-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="151fb-123">Windows Forms 기반 응용 프로그램에서 호스트 Windows Presentation Foundation 컨트롤에 사용할 수 있는 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="151fb-124">Windows Presentation Foundation 기반 응용 프로그램에서 호스트 Windows Forms 컨트롤에 사용할 수 있는 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="151fb-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="151fb-125">Related sections</span></span>

<span data-ttu-id="151fb-126">[마이그레이션 및 상호 운용성](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="151fb-127">Windows Presentation Foundation 및 Windows Forms 기술 간의 상호 운용성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="151fb-128">[Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="151fb-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="151fb-129">Visual Studio에서 Windows Presentation Foundation 컨트롤을 디자인 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="151fb-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
