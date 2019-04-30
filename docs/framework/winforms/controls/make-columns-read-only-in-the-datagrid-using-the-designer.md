---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: a735b9bef9f9e3488941e05b2aa9444e6ecdc4b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012882"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정
기본적으로 텍스트 및 숫자 데이터를 Windows Forms에 표시 된 사용자가 수정할 수 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 수정에 대 한 고려 하지 않은 데이터를 표시 하려는 경우 읽기 전용 데이터를 포함 하는 열을 확인 해야 합니다. 완전히 읽기 전용 컨트롤을 확인 하는 방법에 대 한 정보를 참조 하세요. [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤 디자이너를 사용 하 여](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)입니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>디자이너를 사용 하 여 읽기 전용으로 열을 설정 하려면  
  
1. 스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.  
  
2. 열을 선택 합니다 **선택한 열** 목록입니다.  
  
3. 에 **열 속성** 표에서 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성을 `true`입니다.  
  
    > [!NOTE]
    >  작업도 가능 열 읽기 전용으로 선택 하 여 추가할 때 합니다 **읽기 전용** 확인란 합니다 **열 추가** 대화 상자.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [방법: 추가 하 고 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 제거 합니다.](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [방법: Windows Forms 애플리케이션 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
