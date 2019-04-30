---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: aa81eb7470b818fa2b65200503e5ce65b467c0f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011296"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 열 중 일부만 표시하려는 경우도 있습니다. 직원을 표시 하려는 하는 예를 들어, 다른 사용자 로부터 숨기고 관리 자격 증명이 있는 사용자에 게 급여 열입니다. 또는 다음 중에서 일부만 표시 하려는 많은 열이 포함 된 데이터 원본에 컨트롤을 바인딩하는 것이 좋습니다. 이 경우 숨기기 보다는 표시 하는 데 관심이 없는 열은 일반적으로 제거 합니다. 자세한 내용은 [방법: 추가 및 제거 열에는 Windows Forms DataGridView 컨트롤 디자이너를 사용 하 여](add-and-remove-columns-in-the-datagrid-using-the-designer.md)입니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-hide-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 숨기려면  
  
1. 스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.  
  
2. 열을 선택 합니다 **선택한 열** 목록입니다.  
  
3. 에 **열 속성** 표에서 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`입니다.  
  
    > [!NOTE]
    >  선택을 취소 하 여 추가 하는 경우 열을 숨길 수도 있습니다는 **Visible** 확인란 합니다 **열 추가** 대화 상자.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [방법: 추가 하 고 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 제거 합니다.](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: Windows Forms 애플리케이션 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
