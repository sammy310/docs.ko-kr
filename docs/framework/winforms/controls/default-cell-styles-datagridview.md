---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 대한 기본 셀 스타일 및 데이터 형식 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 8939a182032cfac1beac6c1e5cb3c9de9792114c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333615"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 대한 기본 셀 스타일 및 데이터 형식 설정
<xref:System.Windows.Forms.DataGridView> 제어를 사용 하면 기본 셀 스타일을 지정 하 고 셀 및에 대 한 전체 컨트롤, 특정 열, 행 및 열 머리글에 대 한 원장 효과 만드는 행을 교대로 반복 되는 데이터 형식입니다. 전체 컨트롤에 대해 설정 하는 기본 스타일은 기본적으로 스타일 교대로 반복 되는 행과 열에 대 한 설정 재정의 됩니다. 또한 개별 행 및 셀에 대 한 코드에서 설정 하는 스타일에는 기본 스타일을 재정의 합니다.  
  
 셀 스타일에 대 한 자세한 내용은 참조 하세요. [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)합니다. 행을 교대로 반복 되는 스타일을 설정 하려면 참조 [방법: Windows Forms 디자이너를 사용 하 여 DataGridView 컨트롤에 대 한 행 스타일 교대로 반복 되는 설정](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)합니다.  
  
 사용 하 여 스타일을 설정할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성을 컨트롤에 추가 될 모든 행에 영향을 줍니다. 행 템플릿에 대 한 자세한 내용은 참조 하세요. [방법: 행 템플릿을 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정](use-the-row-template-to-customize-rows-in-the-datagrid.md)합니다.  
  
 다음 절차는 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>컨트롤의 모든 셀에 대 한 기본 스타일을 설정 하려면  
  
1. 선택 된 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 합니다.  
  
2. 에 **속성** 창에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>를 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성입니다. 합니다 **CellStyle 작성기** 대화 상자가 나타납니다.  
  
3. 사용 하 여 속성을 설정 하 여 스타일을 정의 합니다 **미리 보기** 선택 사항을 확인 하는 창입니다.  
  
> [!NOTE]
>  비주얼 스타일을 사용 하는 경우 행 및 열 머리글 (제외 하 고는 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>)는 현재 테마에 따라 자동으로 스타일이 지정 재정의 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 값입니다.  
>   
>  선택한 여러 셀 스타일을 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 수정할 셀 스타일 속성에 동일한 값이 있는 경우만 디자이너를 사용 하 여 제어 합니다. 해당 속성에 대 한 서로 다른 셀 스타일을 **속성** 의 windows를 **CellStyle 작성기** 대화 상자는 비어 있게 됩니다.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>개별 열에 셀에 대 한 기본 스타일을 설정 하려면  
  
1. 마우스 오른쪽 단추로 클릭 합니다 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 하 고 선택 **열 편집**합니다.  
  
2. 열을 선택 합니다 **선택한 열** 목록입니다.  
  
3. 에 **열 속성** 표에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성입니다. 합니다 **CellStyle 작성기** 대화 상자가 나타납니다.  
  
4. 사용 하 여 속성을 설정 하 여 스타일을 정의 합니다 **미리 보기** 선택 사항을 확인 하는 창입니다.  
  
### <a name="to-format-data-in-cells"></a>셀의 데이터 형식을 지정 하려면  
  
1. 앞의 절차 중 하나를 사용 하 여 표시할를 **CellStyle 작성기** 대화 상자에 기본 셀 스타일 속성이 관련이 있습니다.  
  
2. 에 **CellStyle 작성기** 대화 상자에서 줄임표 단추 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성입니다. 합니다 **서식 문자열** 대화 상자가 나타납니다.  
  
3. 형식 유형을 선택한 다음 형식 (예: 개수 표시할 소수 자릿수)의 세부 정보를 수정를 사용 하는 **샘플** 선택 사항을 확인 하는 상자입니다.  
  
4. 바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> null 값을 포함 하 여 입력을 가능성이 있는 데이터 소스에 컨트롤을 **Null 값** 입력란입니다. 셀 값이 null 참조 같음이 값이 표시 됩니다 (`Nothing` Visual basic에서) 또는 <xref:System.DBNull.Value?displayProperty=nameWithType>합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 대한 대체 행 스타일 설정](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
