---
title: '방법: 비동기 Windows Presentation Framework 응용 프로그램 (WCF Data Services) 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: c5dc4e34711cdb128eb012633bad104d0060be71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765866"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>방법: 비동기 Windows Presentation Framework 응용 프로그램 (WCF Data Services) 만들기
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 데이터 서비스에서 가져온 데이터를 WPF(Windows Presentation Framework) 응용 프로그램의 UI 요소에 바인딩할 수 있습니다. 자세한 내용은 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)합니다. 또한 응용 프로그램을 데이터 서비스 요청에 응답을 기다리는 동안 계속 응답할 수 있도록 하는 비동기 방식으로 데이터 서비스에 대 한 작업을 실행할 수 있습니다. 데이터 서비스에 비동기적으로 액세스하려면 Silverlight용 응용 프로그램이 필요합니다. 자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)합니다.  
  
 이 항목에서는 데이터 서비스에 비동기적으로 액세스하고 그 결과를 WPF 응용 프로그램의 요소에 바인딩하는 방법을 보여 줍니다. 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 XAML에서는 WPF 응용 프로그램의 창을 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>예제  
 XAML 파일의 다음 코드 숨김 페이지에서는 데이터 서비스를 사용하여 비동기 쿼리를 실행하고 그 결과를 WPF 창의 요소에 바인딩합니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
