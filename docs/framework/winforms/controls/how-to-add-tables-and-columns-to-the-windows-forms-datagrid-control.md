---
title: '방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가'
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
ms.openlocfilehash: e222227d6283555fa4ec25fe1e5d8e661296034f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709161"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms에서 데이터를 표시할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 컨트롤에 테이블과 열을 만들어 **DataGridTableStyle** 개체에 추가 하는 **GridTableStylesCollection** 개체 이며, 통해 액세스 합니다 <xref:System.Windows.Forms.DataGrid> 컨트롤의 **TableStyles** 속성입니다. 각 테이블 스타일에 지정 된 모든 데이터 테이블의 내용을 표시 합니다 **DataGridTableStyle** 개체의 **MappingName** 속성입니다. 기본적으로 테이블 스타일을 지정 된 열 스타일이 없는 사용 하 여 해당 데이터 테이블 안의 모든 열 표시 됩니다. 테이블에서 열 추가 하 여 표시를 제한할 수 있습니다 **DataGridColumnStyle** 개체를 **GridColumnStylesCollection** 개체를 통해 액세스할 수 있는  **GridColumnStyles** 속성을 각각 **DataGridTableStyle** 개체입니다.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>테이블 및 열을 DataGrid에 프로그래밍 방식으로 추가 하려면  
  
1.  테이블의 데이터를 표시 하려면 먼저 바인딩해야 합니다 <xref:System.Windows.Forms.DataGrid> 데이터 집합에는 컨트롤입니다. 자세한 내용은 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.  
  
    > [!CAUTION]
    >  열 스타일을 프로그래밍 방식으로 지정할 때 항상 만들기 **DataGridColumnStyle** 개체에 추가 하는 **GridColumnStylesCollection** 개체를 추가 하기 전에  **DataGridTableStyle** 개체를 **GridTableStylesCollection** 개체입니다. 빈을 추가 하는 경우 **DataGridTableStyle** 개체를 컬렉션에 **DataGridColumnStyle** 개체를 자동으로 생성 됩니다. 새로 추가 하려고 하면 예외가 throw 될 따라서 **DataGridColumnStyle** 중복을 사용 하 여 개체 **MappingName** 값을 **GridColumnStylesCollection**개체입니다.  
  
2.  새 테이블 스타일을 선언 하 고 해당 매핑을 이름을 설정 합니다.  
  
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
  
3.  새 열 스타일을 선언 하 고 해당 매핑 이름 및 기타 속성을 설정 합니다.  
  
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
  
4.  호출을 **추가** 메서드는 **GridColumnStylesCollection** 열 테이블 스타일을 추가 하는 개체  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  호출을 **추가** 메서드는 **GridTableStylesCollection** 데이터 표에 테이블 스타일을 추가 하는 개체입니다.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>참고자료
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
