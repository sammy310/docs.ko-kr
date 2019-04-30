---
title: '방법: Windows Forms DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 92b4a7d9513ce0ec9b7c02f57c23fa4267fb26ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052172"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤을 사용하여 마스터/세부 목록 만들기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 경우에 <xref:System.Data.DataSet> 계열이 관련된 테이블의 두 사용할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 마스터/세부 정보 형식으로 데이터를 표시 하는 컨트롤입니다. 하나의 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터에 지정 된 두 번째 지정 된 세부 정보 표 및 합니다. 목록에 항목을 선택 하면 관련된 자식 항목의 모든 세부 정보 목록에 표시 됩니다. 예를 들어, 경우에 <xref:System.Data.DataSet> 고객 테이블 및 관련된 Orders 테이블에 포함 되어는 마스터 데이터를 Customers 테이블과 Orders 테이블 세부 정보 표에서을 지정 합니다. 마스터 그리드에서 고객을 선택 하면 모든 주문을 Orders 테이블의 해당 고객과 관련 된 세부 정보 창에 표시 됩니다.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>마스터/세부 관계를 프로그래밍 방식으로 설정 하려면  
  
1. 두 개의 새 만들려면 <xref:System.Windows.Forms.DataGrid> 컨트롤과 해당 속성을 설정 합니다.  
  
2. 데이터 집합에 테이블을 추가 합니다.  
  
3. 형식의 변수 선언 <xref:System.Data.DataRelation> 만들려는 관계를 나타내는입니다.  
  
4. 테이블, 열 및 두 테이블을 연결 해 주는 항목 및 관계의 이름을 지정 하 여 관계를 인스턴스화하십시오.  
  
5. 에 대 한 관계를 추가 합니다 <xref:System.Data.DataSet> 개체의 <xref:System.Data.DataSet.Relations%2A> 컬렉션입니다.  
  
6. 사용 하 여는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 <xref:System.Windows.Forms.DataGrid> 각 표를 바인딩하는 <xref:System.Data.DataSet>합니다.  
  
     다음 예제에서는 이전에 생성 된의 Customers 및 Orders 테이블 간 마스터/세부 관계를 설정 하는 방법을 보여 줍니다 <xref:System.Data.DataSet> (`ds`).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>참고자료

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
