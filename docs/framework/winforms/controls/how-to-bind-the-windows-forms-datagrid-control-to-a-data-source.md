---
title: 데이터 그리드 제어를 데이터 원본에 바인딩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182252"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.  
  
 Windows 양식 <xref:System.Windows.Forms.DataGrid> 컨트롤은 데이터 원본의 정보를 표시하도록 특별히 설계되었습니다. 메서드를 호출 하여 런타임에 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 컨트롤을 바인딩합니다. 다양한 데이터 원본의 데이터를 표시할 수 있지만 가장 일반적인 원본은 데이터 집합 및 데이터 보기입니다.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>데이터 바인딩을 프로그래밍 방식으로 데이터 바인딩하려면  
  
1. 데이터 집합을 채우는 코드를 작성합니다.  
  
     데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 하는 데이터 보기인 경우 양식에 코드를 추가하여 데이터 집합을 채웁니다.  
  
     사용하는 정확한 코드는 데이터 집합이 데이터를 가져오는 위치에 따라 다릅니다. 데이터 집합이 데이터베이스에서 직접 채우는 경우 일반적으로 다음 `Fill` 예제와 같이 데이터 어댑터의 메서드를 호출합니다. `DsCategories1`  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     XML 웹 서비스에서 데이터 집합이 채워지는 경우 일반적으로 코드에서 서비스 인스턴스를 만든 다음 해당 메서드 중 하나를 호출하여 데이터 집합을 반환합니다. 그런 다음 XML 웹 서비스의 데이터 집합을 로컬 데이터 집합에 병합합니다. 다음 예제에서는 `CategoriesService`"의 `GetCategories` 메서드를 호출하고 결과 데이터 집합을 다음이라는 `DsCategories1`로컬 데이터 집합으로 병합하는 XML 웹 서비스의 인스턴스를 만드는 방법을 보여 주며 있습니다.  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. 컨트롤의 <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출하여 데이터 원본과 데이터 멤버를 전달합니다. 데이터 멤버를 명시적으로 전달할 필요가 없는 경우 빈 문자열을 전달합니다.  
  
    > [!NOTE]
    > 그리드를 처음으로 바인딩하는 경우 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 컨트롤및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 설정할 수 있습니다. 그러나 이러한 속성이 설정된 후에는 이러한 속성을 재설정할 수 없습니다. 따라서 항상 메서드를 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 사용하는 것이 좋습니다.  
  
     다음 예제에서는 다음이라는 `DsCustomers1`데이터 집합에서 Customers 테이블에 프로그래밍 방식으로 바인딩하는 방법을 보여 주며 있습니다.  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Customers 테이블이 데이터 집합의 유일한 테이블인 경우 다음과 같은 방식으로 그리드를 바인딩할 수 있습니다.  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (선택 사항) 그리드에 적절한 테이블 스타일과 열 스타일을 추가합니다. 테이블 스타일이 없는 경우 테이블이 표시되지만 최소한의 서식이 있고 모든 열이 표시됩니다.  
  
## <a name="see-also"></a>참고 항목

- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [Windows 양식 데이터 바인딩](../windows-forms-data-binding.md)
