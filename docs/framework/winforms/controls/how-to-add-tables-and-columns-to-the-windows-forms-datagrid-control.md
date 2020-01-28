---
title: DataGrid 컨트롤에 테이블 및 열 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747211"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.

**DataGridTableStyle** 개체를 만들고이 개체를 <xref:System.Windows.Forms.DataGrid> 컨트롤의 **system.windows.forms.datagrid.tablestyles** 속성을 통해 액세스 되는 **GridTableStylesCollection** 개체에 추가 하 여 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤의 데이터를 테이블 및 열에 표시할 수 있습니다. 각 테이블 스타일은 **DataGridTableStyle** 개체의 **MappingName** 속성에 지정 된 모든 데이터 테이블의 내용을 표시 합니다. 기본적으로 열 스타일이 지정 되지 않은 테이블 스타일은 해당 데이터 테이블 내의 모든 열을 표시 합니다. 각 **DataGridTableStyle** 개체의 **gridcolumnstyles** 속성을 통해 액세스 되는 **GridColumnStylesCollection** 개체에 **system.windows.forms.datagridcolumnstyle>** 개체를 추가 하 여 나타나는 테이블의 열을 제한할 수 있습니다.

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>프로그래밍 방식으로 DataGrid에 테이블과 열을 추가 하려면

1. 테이블에 데이터를 표시 하려면 먼저 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터 집합에 바인딩해야 합니다. 자세한 내용은 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)을 참조 하세요.

    > [!CAUTION]
    > 프로그래밍 방식으로 열 스타일을 지정 하는 경우 **system.windows.forms.datagridcolumnstyle>** 개체를 **GridTableStylesCollection** 개체 **에 추가 하기** 전에 항상 **GridColumnStylesCollection** 개체에 추가 합니다. 컬렉션에 빈 **DataGridTableStyle** 개체를 추가 하면 **system.windows.forms.datagridcolumnstyle>** 개체가 자동으로 생성 됩니다. 따라서 **MappingName** 값이 중복 되는 새 **System.windows.forms.datagridcolumnstyle>** 개체를 **GridColumnStylesCollection** 개체에 추가 하려고 하면 예외가 throw 됩니다.

2. 새 테이블 스타일을 선언 하 고 매핑 이름을 설정 합니다.

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. 새 열 스타일을 선언 하 고 해당 매핑 이름 및 기타 속성을 설정 합니다.

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. **GridColumnStylesCollection** 개체의 **add** 메서드를 호출 하 여 테이블 스타일에 열을 추가 합니다.

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. **GridTableStylesCollection** 개체의 **Add** 메서드를 호출 하 여 테이블 스타일을 데이터 표에 추가 합니다.

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>참조

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
