---
title: 도움말 시스템
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742240"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="b00c9-102">Windows Forms 애플리케이션의 도움말 시스템</span><span class="sxs-lookup"><span data-stu-id="b00c9-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="b00c9-103">응용 프로그램 개발자로 서 가장 중요 한 courtesies 중 하나는 사용자에 게 특정 조항이 불법 도움말 시스템을 제공할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="b00c9-104">이것이 혼동 되거나 disoriented 될 때 설정 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="b00c9-105">Windows 기반 응용 프로그램에 도움말 시스템을 제공 하는 것은 [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)를 사용 하 여 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="b00c9-106">다양 한 형식의 도움말</span><span class="sxs-lookup"><span data-stu-id="b00c9-106">Different Types of Help</span></span>  
 <span data-ttu-id="b00c9-107">Windows Forms <xref:System.Windows.Forms.HelpProvider> 구성 요소는 HTML 도움말 1.x 도움말 파일(HTML Help Workshop으로 생성된 .chm 파일 또는 .htm 파일)을 Windows 기반 애플리케이션에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="b00c9-108"><xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여 Windows Forms 또는 특정 컨트롤의 컨트롤에 대 한 상황에 맞는 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="b00c9-109">또한 <xref:System.Windows.Forms.HelpProvider> 구성 요소는 목차, 인덱스 또는 검색 함수의 기본 페이지와 같은 특정 영역에 대 한 도움말 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="b00c9-110"><xref:System.Windows.Forms.HelpProvider> 구성 요소에 대 한 일반 정보는 [HelpProvider 구성 요소 개요](../controls/helpprovider-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b00c9-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="b00c9-111"><xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여 Windows Forms에 대 한 팝업 도움말을 표시 하는 방법에 대 한 자세한 내용은 [방법: 팝업 도움말 표시](how-to-display-pop-up-help.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b00c9-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="b00c9-112"><xref:System.Windows.Forms.ToolTip> 구성 요소를 사용 하 여 컨트롤별 도움말을 표시 하는 방법에 대 한 자세한 내용은 [도구 설명을 사용 하 여 컨트롤 도움말](control-help-using-tooltips.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b00c9-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="b00c9-113">Html 도움말 워크샵을 사용 하 여 HTML 도움말 1.x 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b00c9-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="b00c9-114">HTML 도움말에 대 한 자세한 내용은 MSDN의 "HTML 도움말 워크숍" 또는 기타 "HTML 도움말" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b00c9-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00c9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b00c9-115">See also</span></span>

- [<span data-ttu-id="b00c9-116">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="b00c9-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="b00c9-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b00c9-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="b00c9-118">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b00c9-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="b00c9-119">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="b00c9-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="b00c9-120">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b00c9-120">Windows Forms</span></span>](../index.md)
