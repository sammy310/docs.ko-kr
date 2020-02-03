---
title: DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기
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
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730987"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤을 사용하여 마스터/세부 목록 만들기
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Data.DataSet>에 일련의 관련 테이블이 포함 되어 있는 경우 두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용 하 여 데이터를 마스터/세부 형식으로 표시할 수 있습니다. 한 <xref:System.Windows.Forms.DataGrid> 마스터 그리드로 지정 되 고 두 번째는 세부 정보 표로 지정 됩니다. 마스터 목록에서 항목을 선택 하면 관련 된 모든 자식 항목이 세부 정보 목록에 표시 됩니다. 예를 들어 <xref:System.Data.DataSet>에 Customers 테이블과 관련 Orders 테이블이 포함 되어 있는 경우에는 Customers 테이블을 마스터 그리드로 지정 하 고 Orders 테이블을 세부 정보 표로 지정 합니다. 마스터 표에서 고객이 선택 된 경우 Orders 테이블에서 해당 고객과 연결 된 모든 주문이 세부 정보 표에 표시 됩니다.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>마스터/세부 관계를 프로그래밍 방식으로 설정 하려면  
  
1. 두 개의 새 <xref:System.Windows.Forms.DataGrid> 컨트롤을 만들고 해당 속성을 설정 합니다.  
  
2. 데이터 집합에 테이블을 추가 합니다.  
  
3. <xref:System.Data.DataRelation> 형식의 변수를 선언 하 여 만들려는 관계를 나타냅니다.  
  
4. 관계의 이름을 지정 하 고 두 테이블을 연결 하는 테이블, 열 및 항목을 지정 하 여 관계를 인스턴스화합니다.  
  
5. <xref:System.Data.DataSet> 개체의 <xref:System.Data.DataSet.Relations%2A> 컬렉션에 관계를 추가 합니다.  
  
6. <xref:System.Windows.Forms.DataGrid>의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용 하 여 각 표를 <xref:System.Data.DataSet>에 바인딩합니다.  
  
     다음 예에서는 이전에 생성 된 <xref:System.Data.DataSet> (`ds`)에서 Customers 테이블과 Orders 테이블 간에 마스터/세부 관계를 설정 하는 방법을 보여 줍니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
