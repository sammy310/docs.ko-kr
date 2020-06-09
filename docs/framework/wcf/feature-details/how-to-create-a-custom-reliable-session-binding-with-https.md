---
title: '방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 70f8f4f33626ab0d1705e03750bfd9baa324e60a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598998"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기

이 항목에서는 신뢰할 수 있는 세션에 SSL(Secure Sockets Layer) 전송 보안을 사용하는 방법을 보여 줍니다. HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 사용자 지정 바인딩을 만들어야 합니다. 코드를 사용 하 여 명령적으로 또는 구성 파일에서 선언적으로 신뢰할 수 있는 세션을 사용 하도록 설정 합니다. 이 절차에서는 클라이언트 및 서비스 구성 파일을 사용 하 여 신뢰할 수 있는 세션과 요소를 사용 하도록 설정 합니다 [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) .

이 절차의 핵심 부분은 **\<endpoint>** 구성 요소에 `bindingConfiguration` 이라는 사용자 지정 바인딩 구성을 참조 하는 특성이 포함 되어 있다는 것입니다 `reliableSessionOverHttps` . [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)구성 요소는 및 요소를 포함 하 여 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하도록 지정 하기 위해이 이름을 참조 합니다 **\<reliableSession>** **\<httpsTransport>** .

이 예제의 소스 복사에 대해서는 HTTPS를 [통한 사용자 지정 바인딩 신뢰할 수 있는 세션](../samples/custom-binding-reliable-session-over-https.md)을 참조 하세요.

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하도록 서비스를 CustomBinding으로 구성

1. 서비스 유형에 대한 서비스 계약을 정의합니다.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. 서비스 클래스에 서비스 계약을 구현합니다. 주소 또는 바인딩 정보는 서비스 구현 내에 지정 되지 않습니다. 구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성할 필요가 없습니다.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. 신뢰할 수 *Web.config* 있는 `CalculatorService` `reliableSessionOverHttps` 세션 및 HTTPS 전송을 사용 하는 라는 사용자 지정 바인딩을 사용 하 여에 대 한 끝점을 구성 하는 web.config 파일을 만듭니다.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. 줄이 포함 된 *서비스 .svc* 파일을 만듭니다.

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. 인터넷 정보 서비스 (IIS) 가상 디렉터리에 *서비스 .svc* 파일을 저장 합니다.

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>HTTPS로 신뢰할 수 있는 세션을 사용 하도록 CustomBinding을 사용 하 여 클라이언트 구성

1. 명령줄에서 [ServiceModel Metadata 유틸리티 도구 (*svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스 메타 데이터에서 코드를 생성 합니다.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. 생성 된 클라이언트에는 `ICalculator` 클라이언트 구현에서 충족 해야 하는 서비스 계약을 정의 하는 인터페이스가 포함 되어 있습니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. 또한 생성된 클라이언트 애플리케이션에는 `ClientCalculator`의 구현이 포함되어 있습니다. 주소 및 바인딩 정보는 서비스 구현 내에 지정 되지 않습니다. 구성 파일에서 주소 및 바인딩 정보를 검색 하는 코드를 작성할 필요는 없습니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. `reliableSessionOverHttps`HTTPS 전송 및 신뢰할 수 있는 세션을 사용 하도록 라는 사용자 지정 바인딩을 구성 합니다.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. 애플리케이션에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. 클라이언트를 컴파일하고 실행합니다.  

## <a name="net-framework-security"></a>.NET Framework 보안

이 샘플에 사용 된 인증서는 Makecert.exe를 사용 하 여 만든 테스트 인증서 이므로 브라우저에서와 같은 HTTPS 주소에 액세스 하려고 하면 보안 경고가 나타납니다 *.* `https://localhost/servicemodelsamples/service.svc`

## <a name="see-also"></a>참고 항목

- [신뢰할 수 있는 세션](reliable-sessions.md)
