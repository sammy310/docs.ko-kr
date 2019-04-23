---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 48fd223c8e770e64513d79ef9d24f93321c98332
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322097"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 각 목록에 대 한 여러 열을 표시할 수 있습니다 때 항목을 **세부 정보** 보기. 여러 유형의 각 목록 항목에 대 한 정보를 표시할 열을 사용할 수 있습니다. 예를 들어, 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜 파일의 목록을 표시할 수 있습니다. 만든 후 열을 채우는 방법에 대 한 내용은 참조 [방법: Windows 사용 하 여 열에 하위 항목 표시 Forms ListView 컨트롤](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)합니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ListView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-columns-in-the-designer"></a>디자이너에서 열을 추가 하려면  
  
1. 에 **속성** 창에서 컨트롤의 설정 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>입니다.  
  
2. 에 **속성** 창에서 클릭 합니다 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.ListView.Columns%2A> 속성입니다.  
  
     합니다 **ColumnHeader 컬렉션 편집기** 나타납니다.  
  
3. 사용 된 **추가** 새 열을 추가 하는 단추입니다. 다음 열 머리글을 선택 하 고 해당 텍스트 (열 캡션), 텍스트 맞춤 및 두께 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 열에 하위 항목 표시](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 대 한 아이콘을 표시 합니다.](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가](add-custom-information-to-a-treeview-or-listview-control-wf.md)
