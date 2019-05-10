---
title: '방법: 프로젝트 데이터 원본 (WCF Data Services)를 사용 하 여 데이터 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
ms.openlocfilehash: 69a0ec657f0a8cec34048776a4767cec23d091d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645641"
---
# <a name="how-to-bind-data-using-a-project-data-source-wcf-data-services"></a>방법: 프로젝트 데이터 원본 (WCF Data Services)를 사용 하 여 데이터 바인딩

WCF Data Services 클라이언트 응용 프로그램에서 생성 된 데이터 개체를 기반으로 하는 데이터 원본을 만들 수 있습니다. 사용 하 여 데이터 서비스에 대 한 참조를 추가 하는 **서비스 참조 추가** 대화 상자에서 프로젝트 데이터 소스를 생성 된 클라이언트 데이터 클래스와 함께 만들어집니다. 데이터 서비스에서 노출하는 각 엔터티 집합에 대해 데이터 소스 하나가 만들어집니다. 이러한 데이터 원본 항목을 끌어 서비스에서 데이터를 표시 하는 폼을 만들 수 있습니다 합니다 **데이터 원본** 디자이너 창입니다. 이러한 항목은 데이터 소스에 바인딩된 컨트롤이 됩니다. 실행 하는 동안이 데이터 원본 인스턴스에 바인딩되는 <xref:System.Data.Services.Client.DataServiceCollection%601> 클래스를 데이터 서비스 쿼리에서 반환 되는 개체를 사용 하 여 채워집니다. 자세한 내용은 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)합니다.

 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.

## <a name="use-a-project-data-source-in-a-wpf-window"></a>WPF 창에서 프로젝트 데이터 소스를 사용 합니다.

1. Visual Studio에서 WPF 프로젝트에서 Northwind 데이터 서비스에 대 한 참조를 추가 합니다. 자세한 내용은 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)합니다.

2. 에 **데이터 원본** 창 확장를 `Customers` 에서 노드를 **NorthwindEntities** 프로젝트 데이터 소스입니다.

3. 클릭는 **CustomerID** 항목을 선택 **콤보 상자** 확인 하 고 끌어서 목록에서를 **CustomerID** 에서 항목을 **고객** 노드를는 디자이너입니다.

     창에 대한 XAML 파일에 다음 개체 요소가 만들어집니다.

    - <xref:System.Windows.Data.CollectionViewSource>라는 `customersViewSource` 요소. 최상위 <xref:System.Windows.FrameworkElement.DataContext%2A> 개체 요소의 <xref:System.Windows.Controls.Grid> 속성은 새 <xref:System.Windows.Data.CollectionViewSource>로 설정됩니다.

    - <xref:System.Windows.Controls.ComboBox>라는 데이터 바인딩된 `CustomerID`

    - <xref:System.Windows.Controls.Label>

4. 끌기 합니다 **주문** 디자이너 탐색 속성입니다.

     창에 대한 XAML 파일에 다음 개체 요소가 추가로 만들어집니다.

    - 소스가 <xref:System.Windows.Data.CollectionViewSource>인 `customersOrdersViewSource`라는 두 번째 `customerViewSource` 요소

    - <xref:System.Windows.Controls.DataGrid>라는 데이터 바인딩된 `ordersDataGrid` 컨트롤

5. (선택 사항) 추가 항목을 끌어 놓아 합니다 **고객** 노드에서 디자이너로 합니다.

6. 폼의 코드 페이지를 열고 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]

7. 폼을 정의하는 partial 클래스에서 <xref:System.Data.Objects.ObjectContext> 인스턴스를 만들고 `customerID` 상수를 정의하는 다음 코드를 추가합니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]

8. 디자이너에서 창을 선택합니다.

    > [!NOTE]
    > 창 안에 있는 콘텐츠를 선택하는 대신 창 자체를 선택해야 합니다. 창을 선택 하면 합니다 **이름** 입력란의 위쪽에 **속성** 창 창의 이름이 포함 되어야 합니다.

9. 에 **속성** 창에서 합니다 **이벤트** 단추입니다.

10. 찾을 합니다 **Loaded** 이벤트 및이 이벤트 옆에 있는 드롭다운 목록 두 번 클릭 합니다.

     창에 대한 코드 숨김 파일이 열리고 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기가 생성됩니다.

11. 새로 만들어진 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]

12. 이 코드에서는 Northwind 데이터 서비스의 관련 <xref:System.Data.Services.Client.DataServiceCollection%601> 개체와 함께 `Customers`의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하고 `Customers`에 바인딩하는 LINQ 쿼리의 실행을 기준으로 `Orders` 형식에 대해 `customersViewSource` 인스턴스를 만듭니다.

## <a name="use-a-project-data-source-in-a-windows-form"></a>Windows form에서 프로젝트 데이터 소스 사용

1. 에 **데이터 원본** 창 확장를 **고객** 에서 노드를 **NorthwindEntities** 프로젝트 데이터 소스입니다.

2. 클릭는 **CustomerID** 항목을 선택 **콤보 상자** 확인 하 고 끌어서 목록에서를 **CustomerID** 에서 항목을 **고객** 노드를는 디자이너입니다.

     폼에 다음 컨트롤이 만들어집니다.

    - <xref:System.Windows.Forms.BindingSource>라는 `customersBindingSource` 인스턴스.

    - <xref:System.Windows.Forms.BindingNavigator>라는 `customersBindingNavigator` 인스턴스. 이 컨트롤은 필요 없으므로 삭제할 수 있습니다.

    - <xref:System.Windows.Forms.ComboBox>라는 데이터 바인딩된 `CustomerID`

    - <xref:System.Windows.Forms.Label>

3. 끌기 합니다 **주문** 탐색 속성을 폼입니다.

4. 컨트롤의 `ordersBindingSource` 속성이 <xref:System.Windows.Forms.BindingSource.DataSource%2A>로 설정되고 `customersBindingSource` 속성이 <xref:System.Windows.Forms.BindingSource.DataMember%2A>로 설정된 `Customers` 컨트롤이 만들어집니다. `ordersDataGridView` 데이터 바인딩된 컨트롤도 폼에 만들어지며, 적절한 제목의 레이블 컨트롤이 함께 표시됩니다.

5. (선택 사항) 추가 항목을 끌어 놓아 합니다 **고객** 노드에서 디자이너로 합니다.

6. 폼의 코드 페이지를 열고 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersusing)]

7. 폼을 정의하는 partial 클래스에서 <xref:System.Data.Objects.ObjectContext> 인스턴스를 만들고 `customerID` 상수를 정의하는 다음 코드를 추가합니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdefinition)]

8. 폼 디자이너에서 폼을 두 번 클릭합니다.

     폼에 대한 코드 페이지가 열리고 폼의 `Load` 이벤트를 처리하는 메서드가 만들어집니다.

9. `Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabinding)]

10. 이 코드에서는 Northwind 데이터 서비스에서 <xref:System.Data.Services.Client.DataServiceCollection%601>의 `Customers`을 반환하고 <xref:System.Data.Services.Client.DataServiceQuery%601>에 바인딩하는 <xref:System.Collections.Generic.IEnumerable%601>의 실행을 기준으로 `Customers` 형식에 대해 `customersBindingSource` 인스턴스를 만듭니다.

## <a name="see-also"></a>참고자료

- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [방법: Windows Presentation Foundation 요소에 데이터 바인딩](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)
