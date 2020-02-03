---
title: DataGrid 컨트롤을 사용 하 여 입력 유효성 검사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728289"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.

Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤에 사용할 수 있는 입력 유효성 검사에는 두 가지 유형이 있습니다. 사용자가 셀에 대해 허용 되지 않는 데이터 형식의 값 (예: 문자열)을 입력 하려고 하면 새 잘못 된 값이 이전 값으로 바뀝니다. 이러한 종류의 입력 유효성 검사는 자동으로 수행 되며 사용자 지정할 수 없습니다.

다른 형식의 입력 유효성 검사를 사용 하 여 허용 되지 않는 데이터 (예: 1 보다 크거나 같은 필드의 0 값 또는 부적절 한 문자열)를 거부할 수 있습니다. 이 작업은 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에 대 한 이벤트 처리기를 작성 하 여 데이터 집합에서 수행 됩니다. 다음 예에서는 특히 "Product" 열에 대해 허용 되지 않는 값이 허용 되지 않기 때문에 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 사용 합니다. <xref:System.Data.DataTable.RowChanging> 이벤트를 사용 하 여 "종료 날짜" 열 값이 같은 행의 "시작 날짜" 열 보다 최신 인지 확인할 수 있습니다.

## <a name="to-validate-user-input"></a>사용자 입력의 유효성을 검사 하려면

1. 적절 한 테이블에 대 한 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 처리 하는 코드를 작성 합니다. 부적절 한 입력이 감지 되 면 <xref:System.Data.DataRow> 개체의 <xref:System.Data.DataRow.SetColumnError%2A> 메서드를 호출 합니다.

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. 이벤트 처리기를 이벤트에 연결 합니다.

    폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 나 해당 생성자에 다음 코드를 추가 합니다.

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
