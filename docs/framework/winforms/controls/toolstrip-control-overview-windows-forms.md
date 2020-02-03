---
title: ToolStrip 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741069"
---
# <a name="toolstrip-control-overview-windows-forms"></a>ToolStrip 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 관련 클래스는 사용자 인터페이스 요소를 도구 모음, 상태 표시줄 및 메뉴에 결합 하기 위한 공통 프레임 워크를 제공 합니다. <xref:System.Windows.Forms.ToolStrip> 컨트롤은 가로 또는 세로 공간을 공유 하는 도구 모음의 기능인 내부 활성화 및 편집, 사용자 지정 레이아웃 및 래프팅 (rafting)을 포함 하는 다양 한 디자인 타임 환경을 제공 합니다.  
  
 <xref:System.Windows.Forms.ToolStrip>를 대체 하 고 이전 버전의 컨트롤에 기능을 추가 하는 경우에도 <xref:System.Windows.Forms.ToolBar> 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다.  
  
## <a name="features-of-the-toolstrip-controls"></a>ToolStrip 컨트롤의 기능  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용 하 여 다음을 수행 합니다.  
  
- 컨테이너 간에 공용 사용자 인터페이스를 제공 합니다.  
  
- 도킹, 래프팅 (rafting), 텍스트 및 이미지가 있는 단추, 드롭다운 단추 및 컨트롤, 오버플로 단추, <xref:System.Windows.Forms.ToolStrip> 항목의 런타임 다시 정렬 등 고급 사용자 인터페이스 및 레이아웃 기능을 지 원하는 일반적으로 사용 되는 도구 모음을 쉽게 사용자 지정 하 여 만들 수 있습니다.  
  
- 오버플로 및 런타임 항목 다시 정렬을 지원 합니다. 오버플로 기능은 <xref:System.Windows.Forms.ToolStrip>에 표시 하기에 충분 한 공간이 없는 경우 항목을 드롭다운 메뉴로 이동 합니다.  
  
- 일반적인 렌더링 모델을 통해 운영 체제의 일반적인 모양과 동작을 지원 합니다.  
  
- 다른 컨트롤에 대 한 이벤트를 처리 하는 것과 동일한 방식으로 모든 컨테이너 및 포함 된 항목에 대해 이벤트를 일관 되 게 처리 합니다.  
  
- 항목을 한 <xref:System.Windows.Forms.ToolStrip>에서 다른 위치로 또는 <xref:System.Windows.Forms.ToolStrip>내에서 끌어 놓습니다.  
  
- <xref:System.Windows.Forms.ToolStripDropDown>에서 고급 레이아웃을 사용 하 여 드롭다운 컨트롤과 사용자 인터페이스 형식 편집기를 만듭니다.  
  
 <xref:System.Windows.Forms.ToolStripControlHost> 클래스를 사용 하 여 <xref:System.Windows.Forms.ToolStrip>의 다른 컨트롤을 사용 하 고 해당 컨트롤에 대 한 <xref:System.Windows.Forms.ToolStrip> 기능을 얻을 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStripRenderMode> 및 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 열거형과 함께 <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>및 <xref:System.Windows.Forms.ToolStripManager>를 사용 하 여 기능을 확장 하 고 모양 및 동작을 수정할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 매우 구성 가능 하 고 확장 가능 하며 여러 속성, 메서드 및 이벤트를 제공 하 여 모양과 동작을 사용자 지정 합니다. 다음은 몇 가지 주목할 만한 멤버입니다.  
  
### <a name="important-toolstrip-members"></a>중요 한 ToolStrip 멤버  
  
|속성|Description|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<xref:System.Windows.Forms.ToolStrip> 도킹 된 부모 컨테이너의 가장자리를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<xref:System.Windows.Forms.ToolStrip> 클래스를 통해 끌어서 놓기와 항목 다시 정렬을 프라이빗하게 처리할지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<xref:System.Windows.Forms.ToolStrip> 항목을 레이아웃 하는 방법을 나타내는 값을 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStrip> 또는 <xref:System.Windows.Forms.ToolStripOverflowButton>에 연결 되어 있는지 또는 둘 사이에서 부동 상태로 있을 수 있는지를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<xref:System.Windows.Forms.ToolStripItem> 클릭 될 때 <xref:System.Windows.Forms.ToolStripItem> 드롭다운 목록에 다른 항목을 표시할지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|오버플로가 활성화된 <xref:System.Windows.Forms.ToolStripItem>에 대한 오버플로 단추인 <xref:System.Windows.Forms.ToolStrip>을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<xref:System.Windows.Forms.ToolStrip>의 모양 및 동작 (모양 및 느낌)을 사용자 지정 하는 데 사용 되는 <xref:System.Windows.Forms.ToolStripRenderer>를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<xref:System.Windows.Forms.ToolStrip>에 적용될 그리기 스타일을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성이 변경되면 발생합니다.|  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 유연성은 다양 한 도우미 클래스를 사용 하 여 구현 됩니다. 다음은 가장 주목할 만한 몇 가지 사항입니다.  
  
### <a name="important-toolstrip-companion-classes"></a>중요 한 ToolStrip 도우미 클래스  
  
|속성|Description|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|를 대체 하 고 <xref:System.Windows.Forms.MainMenu> 클래스에 기능을 추가 합니다.|  
|<xref:System.Windows.Forms.StatusStrip>|를 대체 하 고 <xref:System.Windows.Forms.StatusBar> 클래스에 기능을 추가 합니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|를 대체 하 고 <xref:System.Windows.Forms.ContextMenu> 클래스에 기능을 추가 합니다.|  
|<xref:System.Windows.Forms.ToolStripItem>|<xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>또는 <xref:System.Windows.Forms.ToolStripDropDown>에 포함 될 수 있는 모든 요소의 이벤트와 레이아웃을 관리 하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Forms.ToolStripContainer>|다양 한 방법으로 컨트롤을 정렬할 수 있는 폼의 양쪽에 있는 패널을 컨테이너에 제공 합니다.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<xref:System.Windows.Forms.ToolStrip> 개체에 대한 그리기 기능을 처리합니다.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Microsoft Office 스타일의 모양을 제공 합니다.|  
|<xref:System.Windows.Forms.ToolStripManager>|<xref:System.Windows.Forms.ToolStrip> 렌더링 및 래프팅(rafting)과 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ToolStripMenuItem> 개체의 병합을 제어합니다.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|폼에 포함 된 여러 <xref:System.Windows.Forms.ToolStrip> 개체에 적용 되는 그리기 스타일 (사용자 지정, Windows XP 또는 Microsoft Office Professional)을 지정 합니다.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|폼에 포함 된 하나의 <xref:System.Windows.Forms.ToolStrip> 개체에 적용 되는 그리기 스타일 (사용자 지정, Windows XP 또는 Microsoft Office Professional)을 지정 합니다.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|는 특정 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 하지 않지만 <xref:System.Windows.Forms.ToolStrip> 기능을 원하는 다른 컨트롤을 호스팅합니다.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<xref:System.Windows.Forms.ToolStripItem>를 기본 <xref:System.Windows.Forms.ToolStrip>에 배치할지, 오버플로 <xref:System.Windows.Forms.ToolStrip>에 배치할지 아니면 둘 다에 배치할지를 지정 합니다.|  
  
 자세한 내용은 [Toolstrip 기술 요약](toolstrip-technology-summary.md) 및 [toolstrip 컨트롤 아키텍처](toolstrip-control-architecture.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
