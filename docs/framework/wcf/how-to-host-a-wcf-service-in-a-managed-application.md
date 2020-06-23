---
title: '방법: 관리형 애플리케이션에서 WCF 서비스 호스트'
description: 자체 호스팅 서비스를 만들고 테스트 하 여 관리 되는 응용 프로그램 내에서 WCF 서비스를 호스트 하는 방법에 대해 알아봅니다.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246170"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅

관리되는 애플리케이션 내에서 서비스를 호스팅하려면 관리되는 애플리케이션 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 엔드포인트를 사용해 서비스에 대한 엔드포인트를 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.

메시지 받기를 시작하려면 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost>을 호출합니다. 이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다. 관리되는 애플리케이션이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 &quot;자체 호스팅&quot;이라고 합니다. 서비스를 닫으려면 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost>를 호출합니다.

서비스는 관리되는 Windows 서비스, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 호스팅될 수도 있습니다. 서비스의 호스팅 옵션에 대 한 자세한 내용은 [호스팅 서비스](hosting-services.md)를 참조 하세요.

관리되는 애플리케이션에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다. 관리 되는 응용 프로그램에서 서비스를 호스팅하는 방법에 대 한 자세한 내용은 [관리 되는 응용 프로그램에서 호스팅](./feature-details/hosting-in-a-managed-application.md)을 참조 하세요.

다음 절차에서는 콘솔 애플리케이션에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.

## <a name="create-a-self-hosted-service"></a>자체 호스팅 서비스 만들기

1. 새 콘솔 응용 프로그램을 만듭니다.

   1. Visual Studio를 열고 **New**  >  **파일** 메뉴에서 새**프로젝트** 를 선택 합니다.

   2. **설치 된 템플릿** 목록에서 **Visual c #** 또는 **Visual Basic**을 선택한 다음 **Windows 데스크톱**을 선택 합니다.

   3. **콘솔 앱** 템플릿을 선택 합니다. `SelfHost` **이름** 상자에를 입력 한 다음 **확인을**선택 합니다.

2. **솔루션 탐색기** 에서 **SelfHost** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다. **.Net** 탭에서 **system.servicemodel** 을 선택 하 고 **확인**을 선택 합니다.

    > [!TIP]
    > **솔루션 탐색기** 창이 표시 되지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택 합니다.

3. **솔루션 탐색기** 에서 **Program.cs** 또는 module1.vb를 두 번 클릭 하 여 코드 창에서 엽니다 (아직 열려 있지 않은 경우 **).** 파일의 맨 위에 다음 문을 추가 합니다.

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. 서비스 계약을 정의 및 구현합니다. 이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > 서비스 인터페이스를 정의 하 고 구현 하는 방법에 대 한 자세한 내용은 [방법: 서비스 계약 정의](how-to-define-a-wcf-service-contract.md) 및 [방법: 서비스 계약 구현](how-to-implement-a-wcf-contract.md)을 참조 하세요.

5. 서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI(Uniform Resource Identifier)를 나타내는 <xref:System.Type>을 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다. 메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > 이 예제에서는 기본 엔드포인트를 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다. 엔드포인트를 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 엔드포인트를 하나씩 만듭니다. 기본 끝점에 대 한 자세한 내용은 [WCF 서비스에 대 한](./samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.

7. **Ctrl** + **Shift** + **B** 를 눌러 솔루션을 빌드합니다.

## <a name="test-the-service"></a>서비스 테스트

1. **Ctrl** + **F5** 를 눌러 서비스를 실행 합니다.

2. **WCF 테스트 클라이언트**를 엽니다.

    > [!TIP]
    > **WCF 테스트 클라이언트**를 열려면 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 **WcfTestClient.exe**를 실행 합니다.

3. **파일** 메뉴에서 **서비스 추가** 를 선택 합니다.

4. `http://localhost:8080/hello`주소 상자에를 입력 하 고 **확인을**클릭 합니다.

    > [!TIP]
    > 서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다. 코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.

5. **내 서비스 프로젝트** 노드 아래에서 **SayHello** 를 두 번 클릭 합니다. **요청** 목록에서 **값** 열에 이름을 입력 하 고 **호출**을 클릭 합니다.

   **응답** 목록에 회신 메시지가 표시 됩니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출합니다. 기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 엔드포인트가 사용됩니다.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>참고 항목

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [방법: IIS에서 WCF 서비스 호스팅](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [자체 호스팅](./samples/self-host.md)
- [서비스 호스팅](hosting-services.md)
- [방법: 서비스 계약 정의](how-to-define-a-wcf-service-contract.md)
- [방법: 서비스 계약 구현](how-to-implement-a-wcf-contract.md)
- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](using-bindings-to-configure-services-and-clients.md)
- [시스템 제공 바인딩](system-provided-bindings.md)
