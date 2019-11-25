---
title: '방법: 신뢰할 수 있는 세션 내에서 메시지 교환'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 58a392fc6295e82f41e08c80a3343b4059afad7e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141682"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>방법: 신뢰할 수 있는 세션 내에서 메시지 교환

이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다. 구성 파일에서 선언적으로 또는 코드를 사용 하 여 신뢰할 수 있는 세션을 사용 하도록 설정 합니다. 이 절차에서는 클라이언트 및 서비스 구성 파일을 사용 하 여 신뢰할 수 있는 세션을 사용 하도록 설정 하 고 메시지가 전송 된 순서 대로 도착 규정 합니다.

이 절차의 핵심 부분은 끝점 구성 요소에 `Binding1`이라는 바인딩 구성을 참조 하는 `bindingConfiguration` 특성이 포함 되어 있다는 것입니다. [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) 요소의 `enabled` 특성을 `true`로 설정 하 여 신뢰할 수 있는 세션을 사용 하도록 구성 요소 [ **\<바인딩 >** ](../../configure-apps/file-schema/wcf/bindings.md) 구성 요소에서이 이름을 참조 합니다. `ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션에 대해 순서가 지정된 배달 보증을 지정합니다.

이 예제의 소스 복사에 대해서는 [WS 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/ws-reliable-session.md)을 참조 하세요.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 서비스 구성

1. 서비스 유형에 대한 서비스 계약을 정의합니다.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. 서비스 클래스에 서비스 계약을 구현합니다. 주소 또는 바인딩 정보는 서비스 구현 내에 지정 되지 않습니다. 구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성할 필요가 없습니다.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. 신뢰할 수 있는 세션을 사용할 수 있는 <xref:System.ServiceModel.WSHttpBinding>를 사용 하 고 필요한 메시지를 순차적으로 전달 하는 `CalculatorService`에 대 한 끝점을 구성 *하는 web.config 파일을* 만듭니다.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. 줄이 포함 된 *서비스 .svc* 파일을 만듭니다.

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. 인터넷 정보 서비스 (IIS) 가상 디렉터리에 *서비스 .svc* 파일을 저장 합니다.

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>신뢰할 수 있는 세션을 사용 하도록 WSHttpBinding으로 클라이언트 구성

1. 명령줄에서 [ServiceModel Metadata 유틸리티 도구 (*svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스 메타 데이터에서 코드를 생성 합니다.

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. 생성 된 클라이언트는 클라이언트 구현에서 충족 해야 하는 서비스 계약을 정의 하는 `ICalculator` 인터페이스를 포함 합니다.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. 또한 생성된 클라이언트 애플리케이션에는 `ClientCalculator`의 구현이 포함되어 있습니다. 주소 및 바인딩 정보는 서비스 구현 내에서 지정 되지 않습니다. 구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성할 필요가 없습니다.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. 또한 *svcutil.exe* 는 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용 하는 클라이언트에 대 한 구성을 생성 합니다. Visual Studio를 사용 하는 경우 구성 파일의 이름을 *app.config* 로 설정 합니다.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. 응용 프로그램에서 `ClientCalculator`의 인스턴스를 만들고 서비스 작업을 호출 합니다.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. 클라이언트를 컴파일하고 실행합니다.

## <a name="example"></a>예제

기본적으로 여러 시스템 제공 바인딩은 신뢰할 수 있는 세션을 지원합니다. 여기에는 다음이 포함됩니다.

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

신뢰할 수 있는 세션을 지 원하는 사용자 지정 바인딩을 만드는 방법에 대 한 예제는 [방법: HTTPS를 사용 하 여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)를 참조 하세요.

## <a name="see-also"></a>참조

- [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
