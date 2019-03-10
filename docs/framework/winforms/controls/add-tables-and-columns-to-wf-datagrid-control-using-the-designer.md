---
title: '방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤에 테이블과 열 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 741da635ec187d8605a9f67aa010ff49a83ba86b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725352"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤에 테이블과 열 추가

> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms에서 데이터를 표시할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 컨트롤에 테이블과 열을 만들어 <xref:System.Windows.Forms.DataGridTableStyle> 개체에 추가 하는 <xref:System.Windows.Forms.GridTableStylesCollection> 개체를 통해 액세스할 수 있는 합니다 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다. 에 지정 된 모든 데이터 테이블의 내용을 표시 하는 각 테이블 스타일을 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 의 속성을 <xref:System.Windows.Forms.DataGridTableStyle>입니다. 기본적으로 테이블 스타일을 열 스타일을 지정 하지 않으면 해당 데이터 테이블 안의 모든 열 표시 됩니다. 추가 하 여 표시할 테이블에서 열을 제한할 수 있습니다 <xref:System.Windows.Forms.DataGridColumnStyle> 개체를 합니다 <xref:System.Windows.Forms.GridColumnStylesCollection>를 통해 액세스를 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 의 각 속성 <xref:System.Windows.Forms.DataGridTableStyle>합니다.  
  
 다음 절차를 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGrid> 컨트롤입니다. 이러한 프로젝트를 설정 하는 방법에 대 한 정보를 참조 하세요. [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다. Visual Studio 2005에서는 기본적으로는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 합니다 **도구 상자**합니다. 추가 하는 방법에 대 한 내용은 [방법: 도구 상자 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>테이블을 DataGrid 컨트롤 디자이너에 추가 하려면  
  
1.  테이블의 데이터를 표시 하려면 먼저 바인딩해야 합니다 <xref:System.Windows.Forms.DataGrid> 데이터 집합에는 컨트롤입니다. 자세한 내용은 [방법: 데이터 원본 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤을 바인딩할](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)합니다.  
  
2.  선택 된 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성이 속성 창에서 줄임표 단추를 클릭 하 고 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 속성을 표시 합니다 **DataGridTableStyle 컬렉션 편집기**합니다.  
  
3.  컬렉션 편집기에서 클릭 **추가** 테이블 스타일을 삽입 합니다.  
  
4.  클릭 **확인** 컬렉션 편집기를 닫고 옆 줄임표 단추를 클릭 하 여 닫은 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다.  
  
     컨트롤에 바인딩된 데이터 테이블에 대 한 드롭다운 목록에 표시 됩니다 컬렉션 편집기를 열면는 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 테이블 스타일의 속성입니다.  
  
5.  에 **멤버** 상자 컬렉션 편집기의 테이블 스타일을 클릭 합니다.  
  
6.  에 **속성** 컬렉션 편집기 선택 상자는 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 표시 하려는 테이블에 대 한 값입니다.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>디자이너에서 DataGrid 컨트롤에 열을 추가 하려면  
  
1.  에 **멤버** 상자를 **DataGridTableStyle 컬렉션 편집기**, 해당 테이블 스타일을 선택 합니다. 에 **속성** 컬렉션 편집기 선택 상자는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션, 줄임표 단추를 클릭 하 고 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png " vbEllipsesButton")) 표시할 속성 옆에 **DataGridColumnStyle 컬렉션 편집기**합니다.  
  
2.  컬렉션 편집기에서 클릭 **추가** 열 스타일을 삽입 하거나 옆에서 아래쪽 화살표를 클릭 **추가** 열 형식을 지정할 수 있습니다.  
  
     드롭다운 목록 상자에서 선택할 수 있습니다 합니다 <xref:System.Windows.Forms.DataGridTextBoxColumn> 또는 <xref:System.Windows.Forms.DataGridBoolColumn> 형식입니다.  
  
3.  닫으려면 확인을 클릭 합니다 **DataGridColumnStyle 컬렉션 편집기**를 닫은 다음 옆에 있는 줄임표 단추를 클릭 하 여는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성.  
  
     드롭다운 목록에 바인딩된 데이터 테이블의 모든 데이터 열 컬렉션 편집기를 열면 나타납니다는 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 열 스타일의 속성입니다.  
  
4.  에 **멤버** 상자 컬렉션 편집기를 열 스타일을 클릭 합니다.  
  
5.  에 **속성** 컬렉션 편집기 선택 상자는 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 표시 하려는 열에 대 한 값입니다.  
  
## <a name="see-also"></a>참고자료
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
