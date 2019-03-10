---
title: HelpProvider 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: f9cf0c165c6c64186eff53676c8b1b06f74361fc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708381"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="4a027-102">HelpProvider 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4a027-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="4a027-103">Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) 구성 요소는 Windows 응용 프로그램을 사용 하 여 HTML 도움말 1.x 도움말 파일 (HTML Help Workshop으로 생성 된.chm 파일 또는.htm 파일)를 연결할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="4a027-104">다양 한 방법에에서 대 한 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-104">You can provide help in a variety of ways:</span></span>  
  
-   <span data-ttu-id="4a027-105">Windows Forms에서 컨트롤에 대 한 상황에 맞는 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
-   <span data-ttu-id="4a027-106">특정 대화 상자 또는 대화 상자에서 특정 컨트롤에서 상황에 맞는 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
-   <span data-ttu-id="4a027-107">도움말 파일을 목차, 색인 또는 검색 기능을의 기본 페이지 등의 특정 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="4a027-108">Help Provider를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4a027-108">Using the Help Provider</span></span>  
 <span data-ttu-id="4a027-109">추가 <xref:System.Windows.Forms.HelpProvider> Windows 폼에 구성 요소에는 다른 컨트롤의 도움말 속성을 노출 하는 폼에 허용 된 <xref:System.Windows.Forms.HelpProvider> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="4a027-110">이 옵션을 사용 하면 Windows 폼의 컨트롤에 대 한 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="4a027-111">사용 하 여 도움말 파일을 연결할 수 있습니다 합니다 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하 여는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="4a027-112">호출 하 여 제공 된 도움말의 형식을 지정할 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 의 값을 제공 하는 <xref:System.Windows.Forms.HelpNavigator> 지정된 된 컨트롤에 대 한 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="4a027-113">호출 하 여 도움말에 대 한 키워드 또는 항목을 제공 합니다 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a027-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="4a027-114">필요에 따라 다른 컨트롤을 사용 하 여 특정 도움말 문자열을 연결 하려면 사용 된 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a027-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="4a027-115">이 메서드를 사용 하는 컨트롤을 사용 하 여 연결 하는 문자열은 컨트롤에 포커스가 있는 동안 사용자가 F1 키를 누를 때 팝업 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="4a027-116">하는 경우 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 를 사용 해야 설정 되지 않은 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 도움말 텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="4a027-117">모두 설정한 경우 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 도움말 문자열에 따라 도움말 및 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 우선 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a027-118">도움말 파일의 경로를 지정 하는 경우에 상대 경로 사용 하 여 문제를 발생할 수 있습니다는 <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드 또는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 의 속성을 <xref:System.Windows.Forms.HelpProvider> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="4a027-119">이와 같이 절대 파일 경로 사용 하 여 도움말 파일을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a027-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a027-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a027-120">See also</span></span>
- [<span data-ttu-id="4a027-121">Windows Forms 응용 프로그램의 도움말 시스템</span><span class="sxs-lookup"><span data-stu-id="4a027-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)
