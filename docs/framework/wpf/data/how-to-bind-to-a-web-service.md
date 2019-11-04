---
title: '방법: 웹 서비스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 76fa13d4a12362d04c832fd59ee69db5a6811029
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454455"
---
# <a name="how-to-bind-to-a-web-service"></a>방법: 웹 서비스 바인딩
이 예제에서는 웹 서비스 메서드 호출에서 반환 되는 개체에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 [MSDN/TechNet Publishing 시스템 (MTPS) 콘텐츠 서비스](https://go.microsoft.com/fwlink/?LinkId=95677) 를 사용 하 여 지정 된 문서에서 지원 되는 언어 목록을 검색 합니다.  
  
 웹 서비스를 호출 하기 전에 해당 웹 서비스에 대 한 참조를 만들어야 합니다. Visual Studio를 사용 하 여 MTPS 서비스에 대 한 웹 참조를 만들려면 다음 단계를 수행 합니다.  
  
1. Visual Studio에서 프로젝트를 엽니다.  
  
2. **프로젝트** 메뉴에서 **웹 참조 추가**를 클릭 합니다.  
  
3. 대화 상자에서 **URL** 을 [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)설정 합니다.  
  
4. **Go** 를 누르고 **참조를 추가**합니다.  
  
 그런 다음 웹 서비스 메서드를 호출 하 고 적절 한 컨트롤 또는 창의 <xref:System.Windows.FrameworkElement.DataContext%2A>을 반환 된 개체로 설정 합니다. MTPS 서비스의 `GetContent` 메서드는 `getContentRequest` 개체에 대 한 참조를 사용 합니다. 따라서 다음 예제에서는 먼저 요청 개체를 설정 합니다.  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <xref:System.Windows.FrameworkElement.DataContext%2A> 설정 된 후에는 <xref:System.Windows.FrameworkElement.DataContext%2A>가 설정 된 개체의 속성에 대 한 바인딩을 만들 수 있습니다. 이 예제에서 <xref:System.Windows.FrameworkElement.DataContext%2A>는 `GetContent` 메서드에서 반환 되는 `getContentResponse` 개체로 설정 됩니다. 다음 예제에서 <xref:System.Windows.Controls.ItemsControl>는에 바인딩되고 `getContentResponse``availableVersionsAndLocales`의 `locale` 값을 표시 합니다.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 `getContentResponse`구조에 대 한 자세한 내용은 [콘텐츠 서비스 설명서](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [바인딩 소스 개요](binding-sources-overview.md)
- [XAML의 바인딩에 사용할 수 있는 데이터 만들기](how-to-make-data-available-for-binding-in-xaml.md)
