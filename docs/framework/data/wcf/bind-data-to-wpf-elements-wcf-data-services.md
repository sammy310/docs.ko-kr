---
description: '자세한 정보: 방법: Windows Presentation Foundation 요소에 데이터 바인딩 (WCF Data Services)'
title: '방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: 57ad03770681fbedf9b0d5afae82a0a2590f0bc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766532"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>방법: Windows Presentation Foundation 요소에 데이터 바인딩(WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

WCF Data Services를 사용 하면 또는와 같은 WPF (Windows Presentation Foundation) 요소를 컨트롤 <xref:System.Windows.Controls.ListBox> 의 <xref:System.Windows.Controls.ComboBox> <xref:System.Data.Services.Client.DataServiceCollection%601> 데이터 변경 내용과 동기화 된 상태로 유지 하기 위해 컨트롤에 의해 발생 된 이벤트를 처리 하는 인스턴스에 바인딩할 수 있습니다 <xref:System.Data.Services.Client.DataServiceContext> . 자세한 내용은 [컨트롤에 데이터 바인딩](binding-data-to-controls-wcf-data-services.md)을 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  

 다음 예제는 WPF에서 창을 정의 하는 Extensible Application Markup Language (XAML) 페이지에 대 한 코드 숨김이 페이지에서 가져온 것입니다 `SalesOrders` . 창이 로드 되 면 <xref:System.Data.Services.Client.DataServiceCollection%601> 고객을 반환 하는 쿼리 결과를 기준으로이 생성 되며, 해당 국가/지역으로 필터링 됩니다. 이 페이징된 결과의 모든 페이지는 관련 주문과 함께 로드 되며 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Controls.StackPanel> WPF 창에 대 한 루트 레이아웃 컨트롤인의 속성에 바인딩됩니다. 자세한 내용은 [지연 된 콘텐츠 로드](loading-deferred-content-wcf-data-services.md)를 참조 하세요.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>예제  

 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>예제  

 다음 예제는 WPF에서 창을 정의 하는 Extensible Application Markup Language (XAML) 페이지에 대 한 코드 숨김이 페이지에서 가져온 것입니다 `SalesOrders` . 창이 로드 될 때는 <xref:System.Data.Services.Client.DataServiceCollection%601> 관련 개체와 함께 고객을 반환 하는 쿼리 결과를 기준으로 하 여 국가/지역으로 필터링 됩니다. 이 결과는 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Controls.StackPanel> WPF 창의 루트 레이아웃 컨트롤인의 속성에 바인딩됩니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>예제  

 다음 XAML에서는 위 예제의 `SalesOrders` 창을 WPF에서 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
