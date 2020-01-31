---
title: StatusBar 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742870"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="3219c-102">StatusBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3219c-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3219c-103"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 기능을 대체 하 고 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 추가 합니다. 그러나 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다 (선택 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="3219c-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="3219c-104">Windows Forms [StatusBar 컨트롤](statusbar-control-windows-forms.md) 은 폼에서 주로 창의 맨 아래에 표시 되는 영역으로 사용 됩니다 .이 영역에서 응용 프로그램은 다양 한 종류의 상태 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3219c-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="3219c-105"><xref:System.Windows.Forms.StatusBar> 컨트롤에는 상태를 나타내는 텍스트 또는 아이콘을 표시 하는 상태 표시줄 패널 또는 프로세스가 작동 하는 애니메이션의 일련의 아이콘이 있을 수 있습니다. 예를 들어 Microsoft Word에서 문서를 저장 하 고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3219c-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="3219c-106">StatusBar 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="3219c-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="3219c-107">Internet Explorer는 마우스를 하이퍼링크 위로 가져갈 때 상태 표시줄을 사용 하 여 페이지의 URL을 표시 합니다. Microsoft Word는 페이지 위치, 섹션 위치 및 겹쳐쓰기 및 수정 내용 추적과 같은 편집 모드에 대 한 정보를 제공 합니다. 및 Visual Studio는 상태 표시줄을 사용 하 여 도킹 된 창을 도킹 또는 부동으로 조작 하는 방법을 설명 하는 등 상황에 맞는 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3219c-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="3219c-108"><xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `false` (기본값)로 설정 하 고 상태 표시줄의 <xref:System.Windows.Forms.StatusBar.Text%2A> 속성을 상태 표시줄에 표시할 텍스트로 설정 하 여 상태 표시줄에 단일 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3219c-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="3219c-109"><xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true`로 설정 하 고 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>의 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 메서드를 사용 하 여 여러 유형의 정보를 표시 하도록 상태 표시줄을 패널로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3219c-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3219c-110">참조</span><span class="sxs-lookup"><span data-stu-id="3219c-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="3219c-111">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="3219c-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
