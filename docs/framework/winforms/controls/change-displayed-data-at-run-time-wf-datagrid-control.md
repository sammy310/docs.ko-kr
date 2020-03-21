---
title: 데이터 그리드 컨트롤에서 런타임에 표시된 데이터 변경
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142383"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.  
  
 디자인 타임 기능을 사용하여 <xref:System.Windows.Forms.DataGrid> Windows Forms를 만든 후에는 런타임에 그리드 <xref:System.Data.DataSet> 개체의 요소를 동적으로 변경할 수도 있습니다. 여기에는 테이블의 개별 값에 대한 변경 또는 <xref:System.Windows.Forms.DataGrid> 컨트롤에 바인딩된 데이터 원본 변경이 포함될 수 있습니다. 개별 값에 대한 변경 <xref:System.Data.DataSet> 은 컨트롤이 아닌 개체를 <xref:System.Windows.Forms.DataGrid> 통해 수행됩니다.  
  
### <a name="to-change-data-programmatically"></a>프로그래밍 방식으로 데이터를 변경하려면  
  
1. <xref:System.Data.DataSet> 개체에서 원하는 테이블을 지정하고 테이블에서 원하는 행과 필드를 지정하고 셀을 새 값과 동일하게 설정합니다.  
  
    > [!NOTE]
    > 테이블의 첫 번째 <xref:System.Data.DataSet> 테이블 또는 첫 번째 행을 지정하려면 0을 사용합니다.  
  
     다음 예제에서는 를 클릭하여 `Button1`데이터 집합의 첫 번째 테이블의 첫 번째 행의 두 번째 항목을 변경하는 방법을 보여 주며 있습니다. <xref:System.Data.DataSet> ()`ds`및 테이블 (및)`0` `1`이전에 만들어졌습니다.  
  
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
  
     (비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     런타임에 메서드를 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 사용하여 컨트롤을 <xref:System.Windows.Forms.DataGrid> 다른 데이터 원본에 바인딩할 수 있습니다. 예를 들어, 여러 ADO.NET 데이터 컨트롤이 있을 수 있습니다., 각각 다른 데이터베이스에 연결.  
  
### <a name="to-change-the-datasource-programmatically"></a>데이터 원본을 프로그래밍 방식으로 변경하려면  
  
1. 바인딩할 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 데이터 원본 및 테이블의 이름으로 메서드를 설정합니다.  
  
     다음 예제에서는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하여 날짜 원본을 Pubs 데이터베이스의 Authors 테이블에 연결된 ADO.NET 데이터 컨트롤(adoPubsAuthors)으로 변경하는 방법을 보여 주었습니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [ADO.NET 데이터 집합](../../data/adonet/ado-net-datasets.md)
- [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
