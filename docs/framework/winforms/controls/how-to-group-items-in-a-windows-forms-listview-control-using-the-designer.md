---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 7c25c012798adcf90c652beb91a7550406e5f8ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013389"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화
그룹화 기능을 <xref:System.Windows.Forms.ListView> 컨트롤을 사용 하면 그룹의 관련된 항목 집합을 표시할 수 있습니다. 이러한 그룹은 화면에서 그룹 제목을 포함 하는 행 그룹 머리글에 의해 구분 됩니다. 사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 날짜 또는 기타 논리 그룹으로 항목을 사전순으로 그룹화 하 여 보다 쉽게 긴 목록 이동 되도록 합니다. 다음 이미지에서는 일부 그룹화 된 항목을 보여 줍니다.  
  
 ![ListView 그룹](./media/listviewgroups.gif "ListViewGroups")  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ListView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
 그룹화를 사용 하려면 먼저 만들어야 이상의 <xref:System.Windows.Forms.ListViewGroup> 디자이너에서 또는 프로그래밍 방식으로 개체입니다. 그룹을 정의한 후에 항목을 할당할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> 그룹에만 사용할 수 있습니다 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드. 이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다. 자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>추가 하거나 디자이너에서 그룹을 제거 하려면  
  
1. 에 **속성** 창에서 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.ListView.Groups%2A> 속성입니다.  
  
     합니다 **ListViewGroup 컬렉션 편집기** 나타납니다.  
  
2. 그룹을 추가 하려면 클릭 합니다 **추가** 단추입니다. 새 그룹의 속성을 같은 설정한 수는 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 고 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성입니다. 그룹을 제거 하려면 선택 하 고 클릭 합니다 **제거** 단추입니다.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>디자이너에서 그룹에 항목을 할당 하려면  
  
1. 에 **속성** 창에서 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.ListView.Items%2A> 속성입니다.  
  
     합니다 **ListViewItem 컬렉션 편집기** 나타납니다.  
  
2. 새 항목을 추가 하려면 클릭 합니다 **추가** 단추입니다. 새 항목의 속성을 같은 설정한 수는 <xref:System.Windows.Forms.ListViewItem.Text%2A> 고 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성입니다.  
  
3. 선택 된 <xref:System.Windows.Forms.ListViewItem.Group%2A> 속성 드롭다운 목록에서 그룹을 선택 하 고 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 컨트롤](listview-control-windows-forms.md)
- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
