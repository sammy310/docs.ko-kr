---
title: Windows Forms 응용 프로그램의 도움말 시스템
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 1a02271d59a59f0a6e06a652a34922ba5dcdf1f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087276"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="fa8aa-102">Windows Forms 응용 프로그램의 도움말 시스템</span><span class="sxs-lookup"><span data-stu-id="fa8aa-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="fa8aa-103">하나의 가장 중요 한 행위를 응용 프로그램의 개발자는 사용자를 위해 수는 유용한 도움말 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="fa8aa-104">이것이 혼동 하거나 응용 될 때 설정 됩니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="fa8aa-105">사용 하 여 쉽게 이루어집니다 Windows 기반 응용 프로그램의 도움말 시스템을 제공 하는 [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="fa8aa-106">다양 한 유형의 도움이</span><span class="sxs-lookup"><span data-stu-id="fa8aa-106">Different Types of Help</span></span>  
 <span data-ttu-id="fa8aa-107">Windows Forms <xref:System.Windows.Forms.HelpProvider> 구성 요소는 HTML 도움말 1.x 도움말 파일(HTML Help Workshop으로 생성된 .chm 파일 또는 .htm 파일)을 Windows 기반 응용 프로그램에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="fa8aa-108"><xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여 Windows Forms에서 컨트롤 또는 특정 컨트롤에 대 한 상황에 맞는 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="fa8aa-109">또한는 <xref:System.Windows.Forms.HelpProvider> 구성 요소는 도움말 파일의 콘텐츠, 인덱스 또는 검색 기능을 테이블의 기본 페이지 등의 특정 영역을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="fa8aa-110">에 대 한 일반 정보에 대 한 합니다 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 참조 하세요 [HelpProvider 구성 요소 개요](../controls/helpprovider-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="fa8aa-111">사용 하는 방법에 대 한 정보에 대 한 합니다 <xref:System.Windows.Forms.HelpProvider> Windows Forms에서 팝업 도움말을 표시할 구성 요소 참조 [방법: 팝업 도움말 표시](how-to-display-pop-up-help.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="fa8aa-112">사용 방법은 합니다 <xref:System.Windows.Forms.ToolTip> 컨트롤별 도움말을 표시할 구성 요소를 참조 하세요 [제어 하는 데 도움이 사용 하 여 도구 설명](control-help-using-tooltips.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="fa8aa-113">HTML Help Workshop을 사용 하 여 HTML 도움말 1.x 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="fa8aa-114">HTML 도움말에 대 한 자세한 내용은 "HTML Help Workshop" 또는 MSDN의 다른 "HTML Help" 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa8aa-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8aa-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa8aa-115">See also</span></span>

- [<span data-ttu-id="fa8aa-116">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="fa8aa-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="fa8aa-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fa8aa-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="fa8aa-118">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fa8aa-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="fa8aa-119">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="fa8aa-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="fa8aa-120">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa8aa-120">Windows Forms</span></span>](../index.md)
