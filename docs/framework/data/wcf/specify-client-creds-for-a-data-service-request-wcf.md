---
title: '방법: 데이터 서비스에 대 한 클라이언트 자격 증명 요청 (WCF Data Services)를 지정 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: ca2ed1fcf113e06535c8900e5836eb64f9b23958
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59518138"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>방법: 데이터 서비스에 대 한 클라이언트 자격 증명 요청 (WCF Data Services)를 지정 합니다.
기본적으로 클라이언트 라이브러리는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스에 요청을 보낼 때 자격 증명을 제공하지 않습니다. 하지만 <xref:System.Net.NetworkCredential>의 <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> 속성에 대해 <xref:System.Data.Services.Client.DataServiceContext>을 제공하여 데이터 서비스에 요청을 인증하기 위해 자격 증명이 보내지도록 지정할 수 있습니다.  자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요. 이 항목의 예제는 데이터 서비스의 데이터를 요청할 때 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트에 사용되는 자격 증명을 명시적으로 제공하는 방법을 나타냅니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다. 사용할 수도 있습니다는 [Northwind 샘플 데이터 서비스](https://go.microsoft.com/fwlink/?LinkId=187426) 에 게시 된는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ; 웹 사이트를이 샘플 데이터 서비스는 읽기 전용 이며 변경 내용을 저장 하려고 하면 오류가 발생 합니다. 샘플 데이터 서비스는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 웹 사이트는 익명 인증을 허용 합니다.  
  
## <a name="example"></a>예제  
 Extensible Application Markup Language (XAML) 되는 파일을 Windows Presentation Framework 응용 프로그램의 기본 페이지에 대 한 코드 숨김 페이지에서 다음 예제가입니다. 이 예제는 사용자의 인증 자격 증명을 수집한 다음 데이터 서비스에 요청을 할 때 해당 자격 증명을 사용하는 `LoginWindow` 인스턴스를 나타냅니다.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>예제  
 다음 XAML에서는 WPF 응용 프로그램의 기본 페이지를 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>예제  
 다음 예제는 데이터 서비스에 요청을 하기 전에 인증 자격 증명을 수집하는 데 사용되는 창의 코드 숨김 페이지에서 가져온 것입니다.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>예제  
 다음 XAML에서는 WPF 응용 프로그램의 로그인을 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 이 항목의 예제에는 다음과 같은 보안 고려 사항이 적용됩니다.  
  
-   이 예제에 제공된 자격 증명이 작동하는지 확인하려면 Northwind 데이터 서비스에서 익명 액세스 외의 다른 인증 체계를 사용해야 합니다. 그렇지 않으면 데이터 서비스를 호스트하는 웹 사이트에서 자격 증명을 요청하지 않습니다.  
  
-   사용자 자격 증명은 실행 중에만 요청되어야 하며 캐시되어서는 안 됩니다. 자격 증명은 항상 안전하게 보관해야 합니다.  
  
-   기본 및 다이제스트 인증과 함께 전송된 데이터는 암호화되지 않으므로 악의적 사용자가 데이터를 볼 수 있습니다. 또한 기본 인증 자격 증명(사용자 이름 및 암호)은 일반 텍스트로 보내지므로 누군가 이를 가로챌 수 있습니다.  
  
 자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services 보안](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
