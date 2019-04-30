---
title: '방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 60ba1e9304320346d505f3f73e1ba93ff6edab63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961657"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms를 만든 후 <xref:System.Windows.Forms.DataGrid> 디자인 타임 기능을 사용 하려고 할 수 있습니다도의 요소를 동적으로 변경 합니다 <xref:System.Data.DataSet> 런타임에 그리드의 개체입니다. 변경 테이블의 개별 값을 포함할 수 있습니다 또는 바인딩되는 데이터 원본을 변경 된 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 개별 값의 변경 내용을 통해 수행 됩니다 합니다 <xref:System.Data.DataSet> 개체가 아니라는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.  
  
### <a name="to-change-data-programmatically"></a>프로그래밍 방식으로 데이터를 변경 하려면  
  
1. 원하는 테이블을 지정 합니다 <xref:System.Data.DataSet> 개체 및 원하는 행 및 테이블에서 필드를 셀 새 값으로 설정 합니다.  
  
    > [!NOTE]
    >  첫 번째 테이블을 지정 하는 <xref:System.Data.DataSet> 하거나 0을 사용 하 여 테이블의 첫 번째 행.  
  
     다음 예제에서는 클릭 하 여 데이터 집합의 첫 번째 테이블의 첫 번째 행의 두 번째 항목을 변경 하는 방법을 보여 줍니다 `Button1`합니다. <xref:System.Data.DataSet> (`ds`) 및 테이블 (`0` 고 `1`)은 이전에 만든 합니다.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     런타임에 사용할 수는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 바인딩할 메서드는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다른 데이터 소스입니다. 예를 들어, 여러 개 있을 수 있습니다 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 다른 데이터베이스에 연결 된 각 데이터 컨트롤입니다.  
  
### <a name="to-change-the-datasource-programmatically"></a>데이터 소스를 프로그래밍 방식으로 변경 하려면  
  
1. 설정 된 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 데이터 원본 및 바인딩할 하려는 테이블의 이름입니다.  
  
     다음 예제에서는 사용 하 여 날짜 소스를 변경 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드는 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Pubs 데이터베이스에 있는 Authors 테이블에 연결 된 데이터 컨트롤 (adoPubsAuthors).  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 데이터 세트](../../data/adonet/ado-net-datasets.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
