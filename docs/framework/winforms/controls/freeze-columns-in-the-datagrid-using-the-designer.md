---
title: '방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 고정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: e3581390a56e2dfd19ed0d760a618993ec124bfb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716846"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 고정
사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 단일 열이나 열 집합을 자주 참조해야 하는 경우가 있습니다. 예를 들어 많은 열이 포함 된 고객 정보 테이블을 표시할 때 유용 항상 표시 되는 영역 바깥으로 스크롤할에 다른 열을 사용 하도록 설정 하는 동안 고객 이름을 표시할 수 있습니다.  
  
 이 동작을 얻기 위해 컨트롤에서 열을 고정할 수 있습니다. 열을 고정하는 경우 왼쪽(또는 오른쪽에서 왼쪽 언어 스크립트의 경우 오른쪽)에 있는 모든 열도 고정됩니다. 다른 모든 열을 스크롤할 수 있는 동안 고정된 열은 그대로 유지됩니다. 열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 별개인 그룹으로 처리됩니다. 사용자는 각 그룹에서 열의 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-freeze-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 고정 하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.  
  
2.  열을 선택 합니다 **선택한 열** 목록입니다.  
  
3.  에 **열 속성** 표에서 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 속성을 `true`입니다.  
  
    > [!NOTE]
    >  선택 하 여 추가 하는 경우에 열을 고정할 수 있습니다는 **Frozen** 상자에 **열 추가** 대화 상자.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [방법: 추가 하 고 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 제거 합니다.](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [방법: 세계화를 위한 Windows Forms에서 오른쪽에서 왼쪽 텍스트 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))
- [방법: Windows Forms 애플리케이션 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
