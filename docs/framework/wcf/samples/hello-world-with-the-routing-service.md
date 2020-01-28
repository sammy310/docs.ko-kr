---
title: Hello World 라우팅 서비스
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: ae0615c8cf2fa33f3bb363f77c0d06440b6afc13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743715"
---
# <a name="hello-world-with-the-routing-service"></a>Hello World 라우팅 서비스
이 샘플에서는 WCF (Windows Communication Foundation) 라우팅 서비스를 보여 줍니다. 라우팅 서비스는 응용 프로그램에 콘텐츠 기반 라우터를 쉽게 포함할 수 있도록 하는 WCF 구성 요소입니다. 이 샘플에서는 라우팅 서비스를 사용 하 여 통신 하도록 표준 WCF 계산기 샘플을 조정 합니다. 이 샘플에서 계산기 클라이언트는 라우터에 의해 노출된 엔드포인트로 메시지를 보내도록 구성되어 있습니다. 라우팅 서비스는 전송된 모든 메시지를 승인하고 이를 계산기 서비스에 해당하는 엔드포인트에 전달하도록 구성되어 있습니다. 따라서 클라이언트에서 보내는 메시지는 라우터가 받아 실제 계산기 서비스로 다시 라우트합니다. 계산기 서비스에서 보내는 메시지는 다시 라우터로 전송되고 라우터는 이를 다시 계산기 클라이언트에 전달합니다.

### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Visual Studio 2012을 사용 하 여 HelloRoutingService를 엽니다.

2. F5 또는 Ctrl+Shift+B를 누릅니다.

    > [!NOTE]
    > F5 키를 누르면 계산기 클라이언트가 자동으로 시작됩니다. Ctrl+Shift+B(빌드)를 누를 경우에는 다음 애플리케이션을 직접 시작해야 합니다.
    >
    > 1. 계산기 클라이언트(./CalculatorClient/bin/client.exe)
    > 2. 계산기 서비스(./CalculatorService/bin/service.exe)
    > 3. 라우팅 서비스(./RoutingService/bin/RoutingService.exe)

3. Enter 키를 눌러 클라이언트를 시작합니다.

     다음과 같은 내용이 출력됩니다.

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a>코드 또는 App.Config를 통해 구성 가능
 이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다. App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 ConfigureRouterViaCode() 메서드 호출의 주석 처리를 제거할 수도 있습니다. 어떤 방법을 사용하든 라우터 동작은 동일합니다.

### <a name="scenario"></a>시나리오
 이 샘플에서는 기본 메시지 펌프 역할을 하는 라우터를 보여 줍니다. 라우팅 서비스는 미리 구성된 대상 엔드포인트 집합에 직접 메시지를 전달하도록 구성된 투명 프록시 노드 역할을 합니다.

### <a name="real-world-scenario"></a>실제 시나리오
 Contoso에서는 서비스의 명명, 주소 지정, 구성 및 보안과 관련하여 유연성을 향상시키려고 합니다. 이를 위해 Contoso에서는 공개 엔드포인트 역할을 할 서비스 앞에 기본 메시지 펌프를 배치합니다. 이렇게 하면 실제 서비스 앞에 추가 보안 기능을 배치할 수 있으며 나중에 확장된 솔루션이나 서비스 버전 관리를 보다 쉽게 구현할 수 있습니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> 이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>참조

- [AppFabric 호스팅 및 지 속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
