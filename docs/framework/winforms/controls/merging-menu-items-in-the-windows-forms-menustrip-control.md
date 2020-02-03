---
title: MenuStrip 컨트롤의 메뉴 항목 병합
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739046"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Windows Forms MenuStrip 컨트롤의 메뉴 항목 병합
MDI (다중 문서 인터페이스) 응용 프로그램이 있는 경우 자식 폼의 메뉴 항목 또는 전체 메뉴를 부모 폼의 메뉴에 병합할 수 있습니다.  
  
 이 항목에서는 MDI 응용 프로그램에서 메뉴 항목을 병합 하는 것과 관련 된 기본 개념을 설명 합니다.  
  
## <a name="general-concepts"></a>일반 개념  
 프로시저 병합에는 대상과 소스 컨트롤이 모두 포함 됩니다.  
  
- 대상은 메뉴 항목을 병합 하는 주 또는 MDI 부모 폼에 대 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤입니다.  
  
- 소스는 대상 메뉴에 병합 하려는 메뉴 항목이 포함 된 MDI 자식 폼의 <xref:System.Windows.Forms.MenuStrip> 컨트롤입니다.  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성은 드롭다운 목록을 현재 MDI 부모 폼의 MDI 자식의 제목으로 채울 메뉴 항목을 식별 합니다. 예를 들어 일반적으로 **창** 메뉴에 현재 열려 있는 MDI 자식을 나열 합니다.  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> 속성은 MDI 자식 폼의 <xref:System.Windows.Forms.MenuStrip>에서 제공 되는 메뉴 항목을 식별 합니다.  
  
 수동으로 또는 자동으로 메뉴 항목을 병합할 수 있습니다. 메뉴 항목은 두 방법에 대해 동일한 방식으로 병합 되지만 병합은이 항목의 뒷부분에 나오는 "수동 병합" 및 "자동 병합" 단원에서 설명한 대로 다르게 활성화 됩니다. 수동 병합 및 자동 병합 모두에서 각 병합 작업은 다음 병합 작업에 영향을 줍니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 병합 하면 <xref:System.Windows.Forms.MainMenu>의 경우와 마찬가지로 메뉴 항목을 복제 하는 대신 <xref:System.Windows.Forms.ToolStrip> 간에 이동 합니다.  
  
## <a name="mergeaction-values"></a>MergeAction 값  
 <xref:System.Windows.Forms.MergeAction> 속성을 사용 하 여 원본 <xref:System.Windows.Forms.MenuStrip>의 메뉴 항목에 대 한 병합 동작을 설정 합니다.  
  
 다음 표에서는 사용 가능한 병합 동작의 의미와 일반적인 사용법을 설명 합니다.  
  
|MergeAction 값|Description|일반적인 용도|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|기본 소스 항목을 대상 항목 컬렉션의 끝에 추가 합니다.|프로그램의 일부가 활성화 된 경우 메뉴의 끝에 메뉴 항목을 추가 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|소스 항목에 설정 된 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성으로 지정 된 위치에 있는 대상 항목의 컬렉션에 소스 항목을 추가 합니다.|프로그램의 일부가 활성화 될 때 메뉴 항목을 가운데에 추가 하거나 메뉴의 시작 부분에 추가 합니다.<br /><br /> <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>의 값이 두 메뉴 항목의 값과 같으면 역순으로 추가 됩니다. 원래 순서를 유지 하기 위해 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>를 적절 하 게 설정 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|텍스트 일치를 찾거나 일치 하는 텍스트를 찾을 수 없는 경우 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용 하 고 일치 하는 대상 메뉴 항목을 원본 메뉴 항목과 바꿉니다.|대상 메뉴 항목을 다른 이름을 사용 하는 동일한 이름의 소스 메뉴 항목으로 바꿉니다.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|텍스트 일치를 찾거나, 일치 하는 텍스트 항목이 없으면 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용 하 고, 원본의 모든 드롭다운 항목을 대상에 추가 합니다.|메뉴 항목을 하위 메뉴에 삽입 하거나 추가 하거나 하위 메뉴에서 메뉴 항목을 제거 하는 메뉴 구조를 작성 합니다. 예를 들어 MDI 자식의 메뉴 항목을 기본 <xref:System.Windows.Forms.MenuStrip>**저장** 메뉴에 추가할 수 있습니다.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly>를 사용 하면 아무 작업도 수행 하지 않고 메뉴 구조를 탐색할 수 있습니다. 다음 항목을 평가 하는 방법을 제공 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|텍스트 일치를 찾거나, 일치 하는 텍스트가 없는 경우 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값을 사용 하 고, 대상에서 항목을 제거 합니다.|대상 <xref:System.Windows.Forms.MenuStrip>에서 메뉴 항목을 제거 하는 중입니다.|  
  
## <a name="manual-merging"></a>수동 병합  
 <xref:System.Windows.Forms.MenuStrip> 컨트롤만 자동 병합에 참여 합니다. <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤과 같은 다른 컨트롤의 항목을 결합 하려면 필요에 따라 코드에서 <xref:System.Windows.Forms.ToolStripManager.Merge%2A> 및 <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> 메서드를 호출 하 여 수동으로 병합 해야 합니다.  
  
## <a name="automatic-merging"></a>자동 병합  
 원본 폼을 활성화 하 여 MDI 응용 프로그램에 대해 자동 병합을 사용할 수 있습니다. MDI 응용 프로그램에서 <xref:System.Windows.Forms.MenuStrip>를 사용 하려면 소스 <xref:System.Windows.Forms.MenuStrip>에서 수행 되는 병합 작업이 대상 <xref:System.Windows.Forms.MenuStrip>에 반영 되도록 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성을 대상 <xref:System.Windows.Forms.MenuStrip>로 설정 합니다.  
  
 MDI 원본에서 <xref:System.Windows.Forms.MenuStrip>를 활성화 하 여 자동 병합을 트리거할 수 있습니다. 활성화 되 면 소스 <xref:System.Windows.Forms.MenuStrip> MDI 대상으로 병합 됩니다. 새 폼이 활성화 되 면 마지막 폼에서 병합이 되돌아가고 새 폼에서 트리거됩니다. 각 <xref:System.Windows.Forms.ToolStripItem>에서 필요에 따라 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 속성을 설정 하 고 각 <xref:System.Windows.Forms.MenuStrip>에 대해 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 설정 하 여이 동작을 제어할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
- [방법: MenuStrip이 포함된 MDI 창 목록 만들기](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [방법: MDI 애플리케이션의 자동 메뉴 병합 설정](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
