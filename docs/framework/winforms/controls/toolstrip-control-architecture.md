---
title: ToolStrip 컨트롤 아키텍처
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: 6e0c5a426f05590523c178f4b56d07ee98b39d7e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719389"
---
# <a name="toolstrip-control-architecture"></a>ToolStrip 컨트롤 아키텍처
합니다 <xref:System.Windows.Forms.ToolStrip> 고 <xref:System.Windows.Forms.ToolStripItem> 클래스 도구 모음, 상태 및 메뉴 항목을 표시 하기 위한 유연 하 고 확장 가능한 시스템을 제공 합니다. 이러한 클래스에 포함 된 모든 합니다 <xref:System.Windows.Forms> 네임 스페이스 및 이러한 모든 이름은 일반적으로 "ToolStrip" 접두사를 사용 하 여 (같은 <xref:System.Windows.Forms.ToolStripOverflow>) 또는 "제거" 접미사를 사용 하 여 (같은 <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStrip> 와 그 로부터 파생 된 컨트롤입니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 에 대 한 추상 기본 클래스인 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, 및 <xref:System.Windows.Forms.ContextMenuStrip>합니다. 다음 개체 모델에서는 <xref:System.Windows.Forms.ToolStrip> 상속 계층 구조입니다.  
  
 ![ToolStrip 개체 모델](./media/toolstripobjectmodel.gif "ToolStripObjectModel")  
ToolStrip 개체 모델  
  
 모든 항목에 액세스할 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 를 통해를 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션입니다. 모든 항목에 액세스할 수 있습니다는 <xref:System.Windows.Forms.ToolStripDropDownItem> 를 통해를 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 컬렉션입니다. 파생 된 클래스에서 <xref:System.Windows.Forms.ToolStrip>를 사용할 수도 있습니다는 <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> 현재 표시 된 항목만 액세스할 속성입니다. 다음은 현재 오버플로 메뉴에 없는 항목입니다.  
  
 다음 항목을 모두 사용 하 여 원활 하 게 작동 하도록 특별히 설계 된 <xref:System.Windows.Forms.ToolStripSystemRenderer> 고 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수는 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> 대체 하는 최상위 컨테이너인 <xref:System.Windows.Forms.MainMenu>합니다. 또한 키 처리 및 여러 문서 MDI (인터페이스) 기능도 제공 합니다. 기능적으로 <xref:System.Windows.Forms.ToolStripDropDownItem> 하 고 <xref:System.Windows.Forms.ToolStripMenuItem> 과 함께 작동 <xref:System.Windows.Forms.MenuStrip>이지만에서 파생 되므로 <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
 다음 항목을 모두 사용 하 여 원활 하 게 작동 하도록 특별히 설계 된 <xref:System.Windows.Forms.ToolStripSystemRenderer> 고 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수는 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> 대체는 <xref:System.Windows.Forms.StatusBar> 제어 합니다. 특수 기능 <xref:System.Windows.Forms.StatusStrip> 폼의 크기 조정 및 이동 그립에 대 한 지원, 사용자 지정 표 레이아웃을 포함 하며 `Spring` 허용 하는 속성을는 <xref:System.Windows.Forms.ToolStripStatusLabel> 사용 가능한 공간을 자동으로 채울 수.  
  
 다음 항목을 모두 사용 하 여 원활 하 게 작동 하도록 특별히 설계 된 <xref:System.Windows.Forms.ToolStripSystemRenderer> 고 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip>가 <xref:System.Windows.Forms.ContextMenu>를 대체합니다. 연결할 수는 <xref:System.Windows.Forms.ContextMenuStrip> 모든 컨트롤을 마우스 오른쪽 클릭 자동으로 표시 된 상황에 맞는 메뉴 (또는 바로 가기 메뉴). 표시할 수 있습니다는 <xref:System.Windows.Forms.ContextMenuStrip> 를 사용 하 여 프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> 메서드. <xref:System.Windows.Forms.ContextMenuStrip> 취소할 수 있는 지원 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 고 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 동적 채우기 및 여러 원클릭 시나리오를 처리 하는 이벤트입니다. <xref:System.Windows.Forms.ContextMenuStrip> 이미지, 상태를 확인 하는 메뉴 항목, 텍스트, 액세스 키, 바로 가기 및 계단식 메뉴를 지원합니다.  
  
 다음 항목을 모두 사용 하 여 원활 하 게 작동 하도록 특별히 설계 된 <xref:System.Windows.Forms.ToolStripSystemRenderer> 고 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 모든 방향에서. 에 대 한 디자인 타임에 기본적으로 사용할 수는 <xref:System.Windows.Forms.ContextMenuStrip> 제어 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>ToolStrip 일반 기능  
 기능 및 동작에 일반적으로 다음 항목에 설명 합니다 <xref:System.Windows.Forms.ToolStrip> 및 파생 된 컨트롤입니다.  
  
#### <a name="painting"></a>그리기  
 사용자 지정 그리기를 수행할 수 있는 <xref:System.Windows.Forms.ToolStrip> 여러 가지 방법으로 제어 합니다. 다른 Windows Forms 컨트롤과 마찬가지로 합니다 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem> overridable 둘 `OnPaint` 메서드 및 `Paint` 이벤트입니다. 컨트롤의 클라이언트 영역을 기준으로 좌표 시스템은 일반적인 그리기 즉, 컨트롤의 왼쪽 위 모서리는 0, 0입니다. 합니다 `Paint` 이벤트 및 `OnPaint` 에 대 한 메서드는 <xref:System.Windows.Forms.ToolStripItem> 다른 컨트롤 그리기 이벤트 처럼 동작 합니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 항목 및 컨테이너를 통해 렌더링에 대 한 세부적인 액세스 제공는 <xref:System.Windows.Forms.ToolStripRenderer> 배경, 항목 배경, 항목 이미지, 항목 화살표, 항목 텍스트를 그리기 위한 재정의 가능한 메서드가 있는 클래스와의 테두리를 <xref:System.Windows.Forms.ToolStrip>. 이러한 메서드에 대 한 이벤트 인수를 사각형, 색 및 원하는 대로 조정할 수 있는 텍스트 형식 등의 여러 속성을 노출 합니다.  
  
 항목을 그리는 방법을의 몇 가지 측면을 조정 하려면 일반적으로 재정의 된 <xref:System.Windows.Forms.ToolStripRenderer>합니다.  
  
 새 항목을 작성 하는 그리기의 모든 측면을 제어 하려는 경우 재정의 `OnPaint` 메서드. 내에서 `OnPaint`에서 메서드를 사용할 수는 <xref:System.Windows.Forms.ToolStripRenderer>합니다.  
  
 기본적으로 <xref:System.Windows.Forms.ToolStrip> 이중 버퍼링을 활용 하 고 되는지는 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 설정 합니다.  
  
#### <a name="parenting"></a>부모/자식 관리  
 컨테이너 소유권 및 부모/자식 관리의 개념은 보다 복잡 한 <xref:System.Windows.Forms.ToolStrip> 보다 다른 Windows Forms 컨테이너 컨트롤에서 제어 합니다. 오버플로 드롭다운 항목 여러 공유와 같은 동적 시나리오를 지 원하는 데 필요한 <xref:System.Windows.Forms.ToolStrip> 항목의 생성을 지원 하 고는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에서.  
  
 다음은 부모/자식 관리와 관련 된 멤버 및 용도 설명 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> 드롭다운 목록 항목의 원인이 되는 항목에 액세스 합니다. 비슷합니다 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>를 반환 하는 컨트롤을 반환 하는 대신는 <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> 컨트롤 원본인 결정의 합니다 <xref:System.Windows.Forms.ContextMenuStrip> 여러 컨트롤이 동일한을 공유할 때 <xref:System.Windows.Forms.ContextMenuStrip>합니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> 에 대 한 읽기 전용 접근자는 <xref:System.Windows.Forms.ToolStripItem.Parent%2A> 속성입니다. 부모와 달리 소유자에서 부모 나타냅니다는 반환 된 현재 <xref:System.Windows.Forms.ToolStrip> 항목이 표시 되는는 오버플로 영역에 있을 수 있습니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> 반환 된 <xref:System.Windows.Forms.ToolStrip> 해당 항목 컬렉션에 현재 포함 되어 <xref:System.Windows.Forms.ToolStripItem>. 이 참조 하는 가장 좋은 방법은 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 또는 기타 속성 최상위 <xref:System.Windows.Forms.ToolStrip> 오버플로 처리 하는 특수 코드를 작성 하지 않고도 합니다.  
  
#### <a name="behavior-of-inherited-controls"></a>상속 된 컨트롤의 동작  
 다음 컨트롤은 상속에 사용 될 때마다 잠깁니다.  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 패널을 포함 하는 <xref:System.Windows.Forms.ToolStripContainer> 개별 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.  
  
 예를 들어, 이전 목록의 컨트롤 중 하나 이상을 사용 하 여 새 Windows Forms 응용 프로그램을 만듭니다. 하나 이상의 컨트롤의 액세스 한정자를 설정 `public` 또는 `protected`, 한 다음 프로젝트를 빌드합니다. 첫 번째 양식에서 상속 하는 폼을 추가 하 고 상속된 된 컨트롤을 선택 합니다. 컨트롤이 표시 잠긴 액세스 수정 된 것 처럼 동작 `private`합니다.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer 상속 지원  
 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤은 다음 예제와 비슷하게 제한 된 상속된 시나리오를 지원 합니다.  
  
1.  새 Windows Forms 애플리케이션을 만듭니다.  
  
2.  폼에 <xref:System.Windows.Forms.ToolStripContainer>를 추가합니다.  
  
3.  액세스 한정자를 설정 합니다 <xref:System.Windows.Forms.ToolStripContainer> 하 `public` 또는 `protected`합니다.  
  
4.  조합을 추가 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, 및 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel> 영역의 <xref:System.Windows.Forms.ToolStripContainer>합니다.  
  
5.  프로젝트를 빌드합니다.  
  
6.  첫 번째 형태에서 상속 하는 폼을 추가 합니다.  
  
7.  상속 된 선택 <xref:System.Windows.Forms.ToolStripContainer> 양식의 합니다.  
  
#### <a name="inherited-behavior-of-child-controls"></a>자식 컨트롤의 상속 된 동작  
 이전 단계를 완료 하면 상속 된 다음 동작이 발생 합니다.  
  
-   디자이너에서 컨트롤이 상속된 아이콘으로 나타납니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 잠겨;를 선택 하거나 해당 콘텐츠를 다시 정렬할 수 없습니다.  
  
-   컨트롤을 추가할 수 있습니다는 <xref:System.Windows.Forms.ToolStripContentPanel>컨트롤을 이동 하 고 있도록의 자식 컨트롤을 <xref:System.Windows.Forms.ToolStripContentPanel>합니다.  
  
-   폼을 빌드한 후 변경 내용을 유지 합니다.  
  
    > [!NOTE]
    >  모든 액세스 한정자를 제거 <xref:System.Windows.Forms.ToolStripPanel> 포함 된 컨트롤을 <xref:System.Windows.Forms.ToolStripContainer>입니다. 액세스 한정자는 <xref:System.Windows.Forms.ToolStripContainer> 전체 컨트롤을 제어 합니다.  
  
#### <a name="partial-trust"></a>부분 신뢰  
 제한 사항 `ToolStrip`s 부분 신뢰 환경에서 권한 없는 사람이 또는 서비스에서 사용할 수 있는 개인 정보가 의도 하지 않은 항목을 방지 하기 위해 설계 됩니다. 보호 조치는 다음과 같습니다.  
  
-   `ToolStripDropDown` 컨트롤 필요 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 에서 항목을 표시 하는 <xref:System.Windows.Forms.ToolStripControlHost>합니다. 와 같은 내장 컨트롤 모두에 적용이 <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, 및 <xref:System.Windows.Forms.ToolStripProgressBar> 사용자가 만든 계정으로 제어 합니다. 이 요구 사항이 충족 되지 않으면 이러한 항목이 표시 되지 않습니다. 예외가 throw되지 않습니다.  
  
-   설정 된 <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> 속성을 `false` 에 허용 되지 않습니다 및 취소할 수 있는 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 이벤트 매개 변수가 무시 됩니다. 그러면 드롭다운 항목을 해제 하지 않고 둘 이상의 키를 입력 합니다. 이 요구 사항이 충족 되지 않으면 이러한 항목이 표시 되지 않습니다. 예외가 throw되지 않습니다.  
  
-   이벤트를 처리 하는 많은 키 이외의 부분 신뢰 상황에서 발생 하는 경우 발생 하지 것입니다 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>합니다.  
  
-   액세스 키가 처리 될 때 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 부여 되지 않습니다.  
  
#### <a name="usage"></a>사용법  
 다음 사용 패턴 관계가 <xref:System.Windows.Forms.ToolStrip> 레이아웃, 키보드 상호 작용 및 최종 사용자 동작:  
  
-   에 <xref:System.Windows.Forms.ToolStripPanel>  
  
     <xref:System.Windows.Forms.ToolStrip> 내의 위치를 변경할 수는 <xref:System.Windows.Forms.ToolStripPanel> 걸쳐 및 <xref:System.Windows.Forms.ToolStripPanel>s입니다. `Dock` 속성이 무시 됩니다 경우에 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성은 `false`, 크기를 <xref:System.Windows.Forms.ToolStrip> 에 항목을 추가 함에 따라는 <xref:System.Windows.Forms.ToolStripPanel>합니다. 일반적으로 <xref:System.Windows.Forms.ToolStrip> 탭 순서에 참여 하지 않습니다.  
  
-   도킹됨  
  
     <xref:System.Windows.Forms.ToolStrip> 고정된 된 위치에 컨테이너의 한 쪽에 배치 됩니다 하 고 도킹 되어 전체 가장자리를 포인터로 크기로 확장 합니다. 일반적으로 <xref:System.Windows.Forms.ToolStrip> 탭 순서에 참여 하지 않습니다.  
  
-   절대적으로 배치  
  
     <xref:System.Windows.Forms.ToolStrip> 는 다른 컨트롤과 마찬가지로 따라 배치 되는 <xref:System.Windows.Forms.Control.Location%2A> 크기가 고정된 되어 속성과 탭 순서에서 일반적으로 참여 합니다.  
  
#### <a name="keyboard-interaction"></a>키보드 상호 작용  
  
##### <a name="access-keys"></a>액세스 키  
 또는 다음 ALT 키를 결합, 액세스 키는 키보드를 사용 하 여 컨트롤을 활성화 하는 한 가지 방법은입니다. <xref:System.Windows.Forms.ToolStrip> 둘 다 명시적 및 암시적 액세스 키를 지원합니다. 명시적 정의 앰퍼샌드 (&) 문자 앞에 문자를 사용 합니다. 문자 순서에 따라 일치 하는 항목을 찾으려고 시도 하는 알고리즘을 사용 하 여 암시적 정의 지정 된 `Text` 속성입니다.  
  
##### <a name="shortcut-keys"></a>바로 가기 키  
 사용 되는 바로 가기 키를 <xref:System.Windows.Forms.MenuStrip> 조합을 사용 하 여는 <xref:System.Windows.Forms.Keys> 열거형 (순서 관련 되지 않음) 바로 가기 키를 정의 하 합니다. 사용할 수도 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 "삭제 합니다." 대신 "Del"를 표시 하는 등만 텍스트를 사용 하 여 바로 가기 키 표시  
  
##### <a name="navigation"></a>탐색  
 ALT 키를 활성화 합니다 <xref:System.Windows.Forms.MenuStrip> 가리키는 <xref:System.Windows.Forms.Form.MainMenuStrip%2A>합니다. 여기에서 CTRL + TAB 간을 이동 <xref:System.Windows.Forms.ToolStrip> 내에서 제어 `ToolStripPanel`s입니다. 에 있는 항목 간에 이동 하는 TAB 키와 숫자 키패드의 화살표 키를 <xref:System.Windows.Forms.ToolStrip>입니다. 특수 알고리즘 오버플로 영역에서 탐색을 처리합니다. 스페이스바를 누르면 선택 된 <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, 또는 <xref:System.Windows.Forms.ToolStripSplitButton>합니다.  
  
##### <a name="focus-and-validation"></a>포커스 및 유효성 검사  
 ALT 키를 활성화 합니다 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ToolStrip> 도 현재 포커스가 있는 컨트롤에서 포커스가 제거 합니다. 내에 호스트 된 컨트롤 인지를 <xref:System.Windows.Forms.MenuStrip> 의 드롭다운 또는 <xref:System.Windows.Forms.MenuStrip>, 컨트롤 사용자가 TAB 키를 누를 때 포커스를 얻습니다. 일반적으로 <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>를 <xref:System.Windows.Forms.Control.Enter>, 및 <xref:System.Windows.Forms.Control.Leave> 의 이벤트 <xref:System.Windows.Forms.MenuStrip> 키보드에서 활성화 될 경우 발생할 수 있습니다. 이러한 경우에 사용 된 <xref:System.Windows.Forms.MenuStrip.MenuActivate> 및 <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> 이벤트 대신 합니다.  
  
 기본적으로 <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> 는 `false`합니다. 호출 <xref:System.Windows.Forms.ContainerControl.Validate%2A> 명시적으로 양식에 유효성 검사를 수행 합니다.  
  
#### <a name="layout"></a>레이아웃  
 제어 <xref:System.Windows.Forms.ToolStrip> 의 멤버 중 하나를 선택 하 여 레이아웃 <xref:System.Windows.Forms.ToolStripLayoutStyle> 사용 하 여는 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성입니다.  
  
##### <a name="stack-layouts"></a>스택 레이아웃  
 양쪽 끝에서 서로 옆에 있는 항목을 정렬 하는 누적 된 <xref:System.Windows.Forms.ToolStrip>합니다. 다음은 스택 레이아웃을 설명합니다.  
  
-   기본값은 <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>입니다. 이 설정을 사용 하면 합니다 <xref:System.Windows.Forms.ToolStrip> 에 따라 자동으로 해당 레이아웃을 변경 하기를 <xref:System.Windows.Forms.ToolStrip.Orientation%2A> 끌어서 도킹 시나리오를 처리 하는 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> 렌더링 된 <xref:System.Windows.Forms.ToolStrip> 세로로 서로 옆에 있는 항목입니다.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> 렌더링 된 <xref:System.Windows.Forms.ToolStrip> 가로로 서로 옆에 있는 항목입니다.  
  
##### <a name="other-features-of-stack-layouts"></a>스택 레이아웃의 다른 기능  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 종료를 결정 합니다 <xref:System.Windows.Forms.ToolStrip> 항목 정렬 됩니다.  
  
 항목 내에서 적합 하지 않은 경우는 <xref:System.Windows.Forms.ToolStrip>, 오버플로 단추를 자동으로 표시 됩니다. <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 설정 하지 않았거나 전혀 필요에 따라 항상 넘침 영역 항목을 표시할지 여부를 결정 합니다.  
  
 에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 검사할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 항목 주에 배치 되었는지 여부를 결정 하는 속성 <xref:System.Windows.Forms.ToolStrip>, 오버플로 <xref:System.Windows.Forms.ToolStrip>, 전혀 표시 되지 않는 경우 또는. 항목이 표시 되지 않습니다 하는 일반적인 이유는 주 항목에는 적합 하지 않은 <xref:System.Windows.Forms.ToolStrip> 및 해당 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성이 <xref:System.Windows.Forms.ToolStripItemOverflow.Never>합니다.  
  
 확인을 <xref:System.Windows.Forms.ToolStrip> 에 배치 하 여 이동할 수는 <xref:System.Windows.Forms.ToolStripPanel> 설정 해당 <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> 에 <xref:System.Windows.Forms.ToolStripGripStyle.Visible>입니다.  
  
##### <a name="other-layout-options"></a>다른 레이아웃 옵션  
 다른 레이아웃 옵션은 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 고 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>입니다.  
  
##### <a name="flow-layout"></a>선형 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃에 대 한 기본값인 <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, 및 <xref:System.Windows.Forms.ToolStripOverflow>합니다. 비슷합니다는 <xref:System.Windows.Forms.FlowLayoutPanel>합니다. 기능의 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃은 다음과 같습니다.  
  
-   기능의 일부만 <xref:System.Windows.Forms.FlowLayoutPanel> 에 의해 노출 되는 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성입니다. 캐스팅 해야 합니다 <xref:System.Windows.Forms.LayoutSettings> 클래스는 <xref:System.Windows.Forms.FlowLayoutSettings> 클래스입니다.  
  
-   사용할 수는 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 고 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 행 내에서 항목을 정렬 하려면 코드에서 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 검사할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 주 항목 배치 되었는지 여부를 결정 하는 속성 <xref:System.Windows.Forms.ToolStrip> 에 적합 하지 않은 또는.  
  
-   그립 렌더링 되지 않습니다 및를 <xref:System.Windows.Forms.ToolStrip> 에 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 에서 레이아웃 스타일을 <xref:System.Windows.Forms.ToolStripPanel> 이동할 수 없습니다.  
  
-   합니다 <xref:System.Windows.Forms.ToolStrip> 오버플로 단추가 렌더링 되지 않습니다 및 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 무시 됩니다.  
  
##### <a name="table-layout"></a>테이블 레이아웃  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 레이아웃에 대 한 기본값은 <xref:System.Windows.Forms.StatusStrip>합니다. 비슷합니다 <xref:System.Windows.Forms.TableLayoutPanel>합니다. 기능의 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 레이아웃은 다음과 같습니다.  
  
-   기능의 일부만 <xref:System.Windows.Forms.TableLayoutPanel> 에 의해 노출 되는 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 속성입니다. 캐스팅 해야 합니다 <xref:System.Windows.Forms.LayoutSettings> 클래스는 <xref:System.Windows.Forms.TableLayoutSettings> 클래스입니다.  
  
-   사용할 수는 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> 고 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 테이블 셀 내 항목을 정렬 하려면 코드에서 속성입니다.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 무시됩니다.  
  
-   에 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 검사할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 주 항목 배치 되었는지 여부를 결정 하는 속성 <xref:System.Windows.Forms.ToolStrip> 에 적합 하지 않은 또는.  
  
-   그립 렌더링 되지 않습니다 및를 <xref:System.Windows.Forms.ToolStrip> 에 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 에서 레이아웃 스타일을 <xref:System.Windows.Forms.ToolStripPanel> 이동할 수 없습니다.  
  
-   합니다 <xref:System.Windows.Forms.ToolStrip> 오버플로 단추가 렌더링 되지 않습니다 및 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 무시 됩니다.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 다음 항목에서는 <xref:System.Windows.Forms.ToolStripItem> 와 그 로부터 파생 된 컨트롤입니다.  
  
 <xref:System.Windows.Forms.ToolStripItem> 에 포함 된 모든 항목에 대 한 추상 기본 클래스를 <xref:System.Windows.Forms.ToolStrip>입니다. 다음 개체 모델에서는 <xref:System.Windows.Forms.ToolStripItem> 상속 계층 구조입니다.  
  
 ![ToolStripItem 개체 모델](./media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
ToolStripItem 개체 모델  
  
 <xref:System.Windows.Forms.ToolStripItem> 클래스에서 직접 상속 되거나 <xref:System.Windows.Forms.ToolStripItem>를 간접적으로 상속 됩니다에서 또는 <xref:System.Windows.Forms.ToolStripItem> 를 통해 <xref:System.Windows.Forms.ToolStripControlHost> 또는 <xref:System.Windows.Forms.ToolStripDropDownItem>합니다.  
  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤에 포함 되어야 합니다는 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>를 <xref:System.Windows.Forms.StatusStrip>, 또는 <xref:System.Windows.Forms.ContextMenuStrip> 폼에 직접 추가할 수 없습니다. 다양 한 컨테이너 클래스의 적절 한 하위 집합을 포함 하도록 만들어진 <xref:System.Windows.Forms.ToolStripItem> 컨트롤입니다.  
  
 다음 표에서 스톡 <xref:System.Windows.Forms.ToolStripItem> 컨트롤과 컨테이너는 최상의 보입니다. 하지만 모든 <xref:System.Windows.Forms.ToolStrip> 항목에서 호스팅될 수 <xref:System.Windows.Forms.ToolStrip>-컨테이너, 파생 이러한 항목은 다음 컨테이너에서 잘 하도록 설계 되었습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> 디자이너 도구 상자에 나타나지 않습니다.  
  
|포함 된 항목|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|예|아니요|아니요|아니요|예|  
|<xref:System.Windows.Forms.ToolStripComboBox>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripLabel>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripSeparator>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|예|아니요|아니요|예|예|  
|<xref:System.Windows.Forms.ToolStripTextBox>|예|예|예|아니요|예|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|아니요|예|예|아니요|아니요|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|아니요|아니요|아니요|예|아니요|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|예|아니요|아니요|예|아니요|  
|<xref:System.Windows.Forms.ToolStripControlHost>|예|예|아니요|예|예|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> 에 대 한 단추 항목이 <xref:System.Windows.Forms.ToolStrip>합니다. 다양 한 테두리 스타일을 사용 하 여 표시 하 고 나타내고 작동 상태를 활성화 하는 데 사용할 수 있습니다. 기본적으로 포커스를 갖도록 정의할 수 있습니다.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 합니다 <xref:System.Windows.Forms.ToolStripLabel> 레이블 기능을 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. 합니다 <xref:System.Windows.Forms.ToolStripLabel> 비슷합니다는 <xref:System.Windows.Forms.ToolStripButton> 기본적으로 포커스를 받지 않고 및 푸시 되거나 강조 표시 된으로 렌더링 하지 않습니다.  
  
 <xref:System.Windows.Forms.ToolStripLabel> 호스트 항목으로 액세스 키를 지원합니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, 및 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성에는 <xref:System.Windows.Forms.ToolStripLabel> 의 링크 제어를 지원 하려면를 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> 버전이 <xref:System.Windows.Forms.ToolStripLabel> 에서 사용 하기 위해 특별히 설계 된 <xref:System.Windows.Forms.StatusStrip>합니다. 특별 한 기능이 포함 됩니다 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, 및 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>합니다.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> 방향에 따라 메뉴 또는 도구 모음에 세로 또는 가로 줄을 추가 합니다. 그룹 또는 메뉴와 같은 항목을 구분을 제공합니다.  
  
 추가할 수는 <xref:System.Windows.Forms.ToolStripSeparator> 드롭 다운 목록에서 선택 하 여 디자인 타임. 그러나 하면 자동으로 만들 수는 <xref:System.Windows.Forms.ToolStripSeparator> 디자이너 템플릿 노드 또는 하이픈 (-)를 입력 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> 에 대 한 추상 기본 클래스인 <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, 및 <xref:System.Windows.Forms.ToolStripProgressBar>합니다. <xref:System.Windows.Forms.ToolStripControlHost> 두 가지 방법으로 사용자 지정 컨트롤을 비롯 하 여 다른 컨트롤을 호스팅할 수 있습니다.  
  
-   생성 된 <xref:System.Windows.Forms.ToolStripControlHost> 에서 파생 된 클래스를 사용 하 여 <xref:System.Windows.Forms.Control>입니다. 호스팅된 컨트롤 및 속성에 완전히 액세스 하려면 캐스팅 해야 합니다 <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> 속성을 실제 클래스로 나타냅니다.  
  
-   확장할 <xref:System.Windows.Forms.ToolStripControlHost>상속된 된 클래스의 기본 생성자에서 파생 된 클래스를 전달 하 여 기본 클래스 생성자 호출 및 <xref:System.Windows.Forms.Control>합니다. 이 옵션을 사용 하면 일반적인 컨트롤의 메서드 및 속성에 쉽게 액세스할 수를 래핑하는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ComboBox> 의 호스팅을 위해 최적화를 <xref:System.Windows.Forms.ToolStrip>입니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에 노출 되는 <xref:System.Windows.Forms.ToolStripComboBox> 수준 이지만 기본 <xref:System.Windows.Forms.ComboBox> 제어를 통해 완벽 하 게 액세스할 수는 <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> 속성입니다.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> <xref:System.Windows.Forms.TextBox> 의 호스팅을 위해 최적화를 <xref:System.Windows.Forms.ToolStrip>입니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에 노출 되는 <xref:System.Windows.Forms.ToolStripTextBox> 수준 이지만 기본 <xref:System.Windows.Forms.TextBox> 제어를 통해 완벽 하 게 액세스할 수는 <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> 속성입니다.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> <xref:System.Windows.Forms.ProgressBar> 의 호스팅을 위해 최적화를 <xref:System.Windows.Forms.ToolStrip>입니다. 호스팅된 컨트롤의 속성 및 이벤트의 하위 집합에 노출 되는 <xref:System.Windows.Forms.ToolStripProgressBar> 수준 이지만 기본 <xref:System.Windows.Forms.ProgressBar> 제어를 통해 완벽 하 게 액세스할 수는 <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> 속성입니다.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> 에 대 한 추상 기본 클래스인 <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, 및 <xref:System.Windows.Forms.ToolStripSplitButton>, 항목을 직접 또는 드롭 다운 컨테이너에 호스트 추가 항목을 호스팅할 수 있습니다. 설정 하 여이 작업을 수행 합니다 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> 속성을를 <xref:System.Windows.Forms.ToolStripDropDown> 설정를 <xref:System.Windows.Forms.ToolStrip.Items%2A> 의 속성은 <xref:System.Windows.Forms.ToolStripDropDown>합니다. 이러한 드롭다운 항목을 통해 직접 액세스는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 속성입니다.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.ToolStripDropDownItem> 작동 하는 <xref:System.Windows.Forms.ToolStripDropDownMenu> 및 <xref:System.Windows.Forms.ContextMenuStrip> 메뉴에 대 한 특별 한 강조 표시, 레이아웃 및 열 정렬을 처리 하기.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> 다음과 같은 <xref:System.Windows.Forms.ToolStripButton>, 하지만 사용자가 클릭 하면 드롭다운 영역을 보여 줍니다. 숨기 거 나 설정 하 여 드롭다운 화살표를 표시 합니다 <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> 속성입니다. <xref:System.Windows.Forms.ToolStripDropDownButton> 호스트는 <xref:System.Windows.Forms.ToolStripOverflowButton> 오버플로 하는 항목을 표시 하는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> 단추 및 드롭다운 단추 기능을 결합합니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> 동기화 하는 속성을 <xref:System.Windows.Forms.Control.Click> 단추에 표시 되는 항목을 사용 하 여 선택한 드롭다운 목록 항목의 이벤트입니다.  
  
### <a name="toolstripitem-generic-features"></a>Toolstripitem을 가리키는 일반 기능  
 <xref:System.Windows.Forms.ToolStripItem> 다음 제네릭 기능 및 컨트롤을 상속 하는 옵션을 제공 합니다.  
  
-   핵심 이벤트  
  
-   이미지 처리  
  
-   맞춤  
  
-   텍스트 및 이미지 관계  
  
-   표시 스타일  
  
#### <a name="core-events"></a>핵심 이벤트  
 <xref:System.Windows.Forms.ToolStripItem> 컨트롤 자체 클릭, 마우스 및 그리기 이벤트를 받고 일부 키보드도 전처리를 수행할 수 있습니다.  
  
#### <a name="image-handling"></a>이미지 처리  
 합니다 <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>를 <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, 및 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 다양 한 이미지 처리와 관련 된 속성입니다. 이미지를 사용 하 여 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 실행 시간 – 전용를 설정 하거나 직접 이러한 속성을 설정 하 여 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 속성입니다.  
  
 둘 다에서 속성의 상호 작용에 의해 결정 됩니다 이미지 크기 조정 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripItem>다음과 같이 합니다.  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> 이미지의 조합으로 결정 된 최종 이미지의 소수 자릿수 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 설정 및 컨테이너의 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 설정 합니다.  
  
    -   경우 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 됩니다 `true` (기본값) 및 <xref:System.Windows.Forms.ToolStripItemImageScaling> 됩니다 <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, 이미지 크기는 조정 되지 않습니다 및 <xref:System.Windows.Forms.ToolStrip> 크기는 가장 큰 항목 또는 지정 된 최소 크기의 합니다.  
  
    -   경우 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 됩니다 `false` 및 <xref:System.Windows.Forms.ToolStripItemImageScaling> 은 <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, 모두 이미지도 <xref:System.Windows.Forms.ToolStrip> 발생 크기 조정 합니다.  
  
#### <a name="alignment"></a>맞춤  
 값을 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성의 끝을 결정는 <xref:System.Windows.Forms.ToolStrip> 항목이 나타나는. 합니다 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성은 경우에만 사용할 수의 레이아웃 스타일을 <xref:System.Windows.Forms.ToolStrip> 스택 오버플로 값 중 하나로 설정 됩니다.  
  
 에 항목을 배치 합니다 <xref:System.Windows.Forms.ToolStrip> 항목 컬렉션에 항목을 표시 된 순서에서입니다. 항목 배치 되는 위치를 프로그래밍 방식으로 변경 하려면 사용 된 <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> 컬렉션에서 항목을 이동 하는 방법입니다. 이 메서드는 항목을 이동 하지만 복제 하지 않습니다.  
  
#### <a name="text-and-image-relationship"></a>텍스트 및 이미지 관계  
 합니다 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 에 텍스트와 관련 하 여 이미지의 상대 위치를 정의 하는 속성을 <xref:System.Windows.Forms.ToolStripItem>입니다. 이미지, 텍스트 또는 둘 다 없는 항목은 특별 한 경우로 처리 됩니다 있도록는 <xref:System.Windows.Forms.ToolStripItem> 누락 된 요소 또는 요소에 대 한 빈 곳을 표시 하지 않습니다.  
  
#### <a name="display-style"></a>표시 스타일  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 원하는 부분만 표시 하는 동안 항목의 텍스트 및 이미지 속성의 값을 설정할 수 있습니다. 이 각기 다른 컨텍스트에서 동일한 항목을 표시할 때만 표시 스타일을 변경 하려면 일반적으로 사용 됩니다.  
  
## <a name="accessory-classes"></a>액세서리 클래스  
 기타 다양 한 기능을 제공 하는 클래스는 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.ToolStripManager> 지원 <xref:System.Windows.Forms.ToolStrip>-관련 병합, 설정 및 렌더러 옵션 등의 전체 응용 프로그램에 대 한 작업입니다.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> 특정 스타일 또는 테마를 적용할 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 쉽게 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 펜과 대체할 수 있는 색 테이블을 기반으로 하는 브러시를 만듭니다 (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> 시스템 색과 평면 비주얼 스타일을 적용 <xref:System.Windows.Forms.ToolStrip> 응용 프로그램입니다.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> 비슷합니다 <xref:System.Windows.Forms.SplitContainer>합니다. 도킹 된 쪽 패널 네 개 사용 하 여 (인스턴스의 <xref:System.Windows.Forms.ToolStripPanel>) 및 중앙 패널이 하나 (인스턴스의 <xref:System.Windows.Forms.ToolStripContentPanel>) 일반적인 배열을 만드는 데 있습니다. 왼쪽 패널에 제거할 수 없지만 숨길 수 있습니다. 제거 아니고 중앙 패널을 숨길 수 있습니다. 하나 이상의 정렬할 수 있습니다 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, 또는 <xref:System.Windows.Forms.StatusStrip> 측면 패널에서 컨트롤 다른 컨트롤에 대 한 중앙 패널을 사용할 수 있습니다. <xref:System.Windows.Forms.ToolStripContentPanel> 또한 일관 된 모양을 위해 폼의 본문으로 렌더러 지원을 받는 방법을 제공 합니다. <xref:System.Windows.Forms.ToolStripContainer> 다중 문서 인터페이스 MDI ()를 지원 하지 않습니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 이동 및 정렬을 위한 공간이 제공 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. 따라서 선택 하는 경우에 하나의 패널을 사용할 수 있습니다 및 <xref:System.Windows.Forms.ToolStripPanel> MDI 시나리오에서 잘 작동 합니다.  
  
## <a name="see-also"></a>참고자료
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
- [ToolStrip 컨트롤](toolstrip-control-windows-forms.md)
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
- [StatusStrip 컨트롤](statusstrip-control.md)
- [ContextMenuStrip 컨트롤](contextmenustrip-control.md)
- [BindingNavigator 컨트롤](bindingnavigator-control-windows-forms.md)
