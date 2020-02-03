---
title: 디자이너를 사용 하 여 DataGrid 컨트롤에 테이블 및 열 추가
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: fed7465fbe665b1945161653616e3a21640e0b2a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746257"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.

<xref:System.Windows.Forms.DataGridTableStyle> 개체를 만들고 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성을 통해 액세스 되는 <xref:System.Windows.Forms.GridTableStylesCollection> 개체에 추가 하 여 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤의 데이터를 테이블 및 열에 표시할 수 있습니다. 각 테이블 스타일은 <xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성에 지정 된 모든 데이터 테이블의 내용을 표시 합니다. 기본적으로 열 스타일이 지정 되지 않은 테이블 스타일은 해당 데이터 테이블 내의 모든 열을 표시 합니다. 각 <xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성을 통해 액세스 되는 <xref:System.Windows.Forms.GridColumnStylesCollection>에 <xref:System.Windows.Forms.DataGridColumnStyle> 개체를 추가 하 여 표시 되는 테이블의 열을 제한할 수 있습니다.

다음 절차를 수행 하려면 <xref:System.Windows.Forms.DataGrid> 컨트롤을 포함 하는 폼이 포함 된 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요. 기본적으로 Visual Studio 2005에서는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 **도구 상자**에 없습니다. 추가 하는 방법에 대 한 자세한 내용은 [방법: 도구 상자에 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))를 참조 하세요.

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>디자이너에서 DataGrid 컨트롤에 테이블을 추가 하려면

1. 테이블에 데이터를 표시 하려면 먼저 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터 집합에 바인딩해야 합니다. 자세한 내용은 [방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤을 데이터 소스에 바인딩](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)을 참조 하세요.

2. 속성 창에서 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성을 선택 하 고 속성 옆의 줄임표 단추 (...)를 클릭 하 여 **DataGridTableStyle 컬렉션 편집기**를 표시 합니다![(속성 창).](./media/visual-studio-ellipsis-button.png)

3. 컬렉션 편집기에서 **추가** 를 클릭 하 여 테이블 스타일을 삽입 합니다.

4. **확인** 을 클릭 하 여 컬렉션 편집기를 닫은 다음 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성 옆에 있는 줄임표 단추를 클릭 하 여 다시 엽니다.

     컬렉션 편집기를 다시 열면 컨트롤에 바인딩된 모든 데이터 테이블이 테이블 스타일의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성에 대 한 드롭다운 목록에 표시 됩니다.

5. 컬렉션 편집기의 **멤버** 상자에서 테이블 스타일을 클릭 합니다.

6. 컬렉션 편집기의 **속성** 상자에서 표시 하려는 테이블에 대 한 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 값을 선택 합니다.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>디자이너에서 DataGrid 컨트롤에 열을 추가 하려면

1. **DataGridTableStyle 컬렉션 편집기**의 **멤버** 상자에서 적절 한 테이블 스타일을 선택 합니다. 컬렉션 편집기의 **속성** 상자에서 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션을 선택 하 고 줄임표![단추 (](./media/visual-studio-ellipsis-button.png))를 클릭 하 여 속성 옆에 속성 창 있는 줄임표 단추 (...)를 클릭 하 여 **system.windows.forms.datagridcolumnstyle> 컬렉션 편집기**를 표시 합니다.

2. 컬렉션 편집기에서 **추가** 를 클릭 하 여 열 스타일을 삽입 하거나 **추가** 옆에 있는 아래쪽 화살표를 클릭 하 여 열 유형을 지정 합니다.

     드롭다운 상자에서 <xref:System.Windows.Forms.DataGridTextBoxColumn> 또는 <xref:System.Windows.Forms.DataGridBoolColumn> 유형 중 하나를 선택할 수 있습니다.

3. 확인을 클릭 하 여 **System.windows.forms.datagridcolumnstyle> 컬렉션 편집기**를 닫은 다음 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성 옆에 있는 줄임표 단추를 클릭 하 여 다시 엽니다.

     컬렉션 편집기를 다시 열면 바인딩된 데이터 테이블의 모든 데이터 열이 열 스타일의 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 속성에 대 한 드롭다운 목록에 표시 됩니다.

4. 컬렉션 편집기의 **멤버** 상자에서 열 스타일을 클릭 합니다.

5. 컬렉션 편집기의 **속성** 상자에서 표시 하려는 열에 대 한 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 값을 선택 합니다.

## <a name="see-also"></a>참고 항목

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
