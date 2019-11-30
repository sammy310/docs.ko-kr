---
title: '방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: b623dc10bfe1b723c62b2861b4142a138904e64a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569334"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)
WCF Data Services를 사용 하 여 <xref:System.Windows.Controls.ListBox> 또는 <xref:System.Windows.Controls.ComboBox>와 같은 WPF (Windows Presentation Foundation) 요소를 <xref:System.Data.Services.Client.DataServiceCollection%601>인스턴스에 바인딩할 수 있습니다. 그러면 컨트롤에서 발생 한 이벤트를 처리 하 여 컨트롤의 데이터 변경 내용과 <xref:System.Data.Services.Client.DataServiceContext> 동기화 된 상태로 유지 합니다. 자세한 내용은 [컨트롤에 데이터 바인딩](binding-data-to-controls-wcf-data-services.md)을 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의 하는 Extensible Application Markup Language (XAML) 페이지에 대 한 코드 숨김이 페이지에서 가져온 것입니다. 창이 로드 되 면 고객을 반환 하는 쿼리 결과를 기준으로 국가/지역으로 필터링 된 <xref:System.Data.Services.Client.DataServiceCollection%601> 만들어집니다. 이 페이징된 결과의 모든 페이지는 관련 주문과 함께 로드 되며 WPF 창에 대 한 루트 레이아웃 컨트롤인 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 바인딩됩니다. 자세한 내용은 [지연 된 콘텐츠 로드](loading-deferred-content-wcf-data-services.md)를 참조 하세요.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>예제  
 다음 예제는 WPF에서 `SalesOrders` 창을 정의 하는 Extensible Application Markup Language (XAML) 페이지에 대 한 코드 숨김이 페이지에서 가져온 것입니다. 창이 로드 되 면 관련 개체를 사용 하 여 고객을 반환 하는 쿼리 결과를 기준으로 국가/지역으로 필터링 된 <xref:System.Data.Services.Client.DataServiceCollection%601> 만들어집니다. 이 결과는 WPF 창의 루트 레이아웃 컨트롤인 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에 바인딩됩니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>예제  
 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
