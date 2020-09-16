---
title: '방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 696e6a08f3f040fcc6f27d101cd6b7c8cc89a0d6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556644"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성

ASP.NET 웹 서비스 클라이언트와 상호 운용할 수 있도록 WCF (Windows Communication Foundation) 서비스 끝점을 구성 하려면 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 형식을 서비스 끝점의 바인딩 형식으로 사용 합니다.  
  
 바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다. ASP.NET 웹 서비스 클라이언트는 MTOM 메시지 인코딩을 지원 하지 않으므로 속성은 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 기본값인로 유지 해야 합니다 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> . ASP.NET 웹 서비스 클라이언트는 WS-SECURITY를 지원 하지 않으므로 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 를로 설정 해야 합니다 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> .  
  
 ASP.NET 웹 서비스 프록시 생성 도구 ( [Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [웹 서비스 검색 도구 (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100)), Visual Studio의 **웹 참조 추가** 기능 등 WCF 서비스에 대 한 메타 데이터를 사용할 수 있도록 하려면 HTTP/GET 메타 데이터 끝점을 노출 해야 합니다.  
  
## <a name="add-an-endpoint-in-code"></a>코드에서 끝점 추가  
  
1. 새 <xref:System.ServiceModel.BasicHttpBinding> 인스턴스를 만듭니다.  
  
2. 바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 엔드포인트 바인딩에 대한 전송 보안을 선택적으로 사용할 수 있습니다. 자세한 내용은 [전송 보안](transport-security.md)을 참조 하세요.  
  
3. 방금 만든 바인딩 인스턴스를 사용하여 새 애플리케이션 엔드포인트를 서비스 호스트에 추가합니다. 코드에서 서비스 끝점을 추가 하는 방법에 대 한 자세한 내용은 [방법: 코드에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-code.md)를 참조 하세요.  
  
4. 서비스에 대해 HTTP/GET 메타데이터 엔드포인트를 사용합니다. 자세한 내용은 [방법: 코드를 사용 하 여 서비스에 대 한 메타 데이터 게시](how-to-publish-metadata-for-a-service-using-code.md)를 참조 하세요.  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>구성 파일에 끝점 추가  
  
1. 새 <xref:System.ServiceModel.BasicHttpBinding> 바인딩 구성을 만듭니다. 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](../how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요.  
  
2. 바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 엔드포인트 바인딩 구성에 대한 전송 보안을 선택적으로 사용할 수 있습니다. 자세한 내용은 [전송 보안](transport-security.md)을 참조 하세요.  
  
3. 방금 만든 바인딩 구성을 사용하여 서비스에 대한 새 애플리케이션 엔드포인트를 구성합니다. 구성 파일에서 서비스 끝점을 추가 하는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-configuration.md)를 참조 하세요.  
  
4. 서비스에 대해 HTTP/GET 메타데이터 엔드포인트를 사용합니다. 자세한 내용은 [방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)를 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제 코드에서는 ASP.NET 웹 서비스 클라이언트와 호환 되는 WCF 끝점을 코드 또는 구성 파일에 추가 하는 방법을 보여 줍니다.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>참조

- [방법: 코드에서 서비스 엔드포인트 만들기](how-to-create-a-service-endpoint-in-code.md)
- [방법: 코드를 사용하여 서비스에 대한 메타데이터 게시](how-to-publish-metadata-for-a-service-using-code.md)
- [방법: 구성에서 서비스 바인딩 지정](../how-to-specify-a-service-binding-in-configuration.md)
- [방법: 구성에서 서비스 엔드포인트 만들기](how-to-create-a-service-endpoint-in-configuration.md)
- [방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [전송 보안](transport-security.md)
- [메타데이터 사용](using-metadata.md)
