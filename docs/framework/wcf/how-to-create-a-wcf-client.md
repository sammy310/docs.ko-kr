---
title: '자습서: Windows 통신 파운데이션 클라이언트 만들기'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184107"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>자습서: Windows 통신 파운데이션 클라이언트 만들기

이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 네 번째 에 대해 설명합니다. 자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.

WCF 응용 프로그램을 만드는 다음 작업은 WCF 서비스에서 메타데이터를 검색하여 클라이언트를 만드는 것입니다. Visual Studio를 사용하여 서비스의 MEX 끝점에서 메타데이터를 가져오는 서비스 참조를 추가합니다. 그런 다음 Visual Studio는 선택한 언어로 클라이언트 프록시에 대해 관리되는 소스 코드 파일을 생성합니다. 또한 클라이언트 구성*파일(App.config)을*만듭니다. 이 파일을 사용하면 클라이언트 응용 프로그램이 끝점에서 서비스에 연결할 수 있습니다.

> [!NOTE]
> Visual Studio의 클래스 라이브러리 프로젝트에서 WCF 서비스를 호출하는 경우 **서비스 참조 추가** 기능을 사용하여 프록시 및 관련 구성 파일을 자동으로 생성합니다. 그러나 클래스 라이브러리 프로젝트는 이 구성 파일을 사용하지 않으므로 클래스 라이브러리를 호출하는 실행 파일에 대해 생성된 구성 파일의 설정을 *App.config* 파일에 추가해야 합니다.

> [!NOTE]
> 또는 Visual Studio 대신 [ServiceModel 메타데이터 유틸리티 도구를](#servicemodel-metadata-utility-tool) 사용하여 프록시 클래스 및 구성 파일을 생성합니다.

클라이언트 애플리케이션은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다. 이 절차는 [자습서: 클라이언트 사용에](how-to-use-a-wcf-client.md)설명되어 있습니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WCF 클라이언트에 대한 콘솔 앱 프로젝트를 만들고 구성합니다.
> - WCF 서비스에 서비스 참조를 추가하여 프록시 클래스 및 구성 파일을 생성합니다.

## <a name="create-a-windows-communication-foundation-client"></a>Windows 통신 기반 클라이언트 만들기

1. Visual Studio에서 콘솔 앱 프로젝트 만들기:

    1. **파일** 메뉴에서**프로젝트/솔루션** **열기를** > 선택하고 이전에 만든 **GettingStarted** *솔루션(GettingStarted.sln)을*찾아봅니다. **열기**를 선택합니다.

    2. **보기** 메뉴에서 **솔루션 탐색기를**선택합니다.

    3. 솔루션 **탐색기** 창에서 **GettingStarted** 솔루션(맨 위 노드)을 선택한 다음 바로 가기 메뉴에서**새 프로젝트** **추가를** > 선택합니다.

    4. 새 **프로젝트 추가** 창왼쪽에서 **Visual C#** 또는 **Visual Basic**에서 Windows **데스크톱** 범주를 선택합니다.

    5. 콘솔 **앱(.NET 프레임워크)** 템플릿을 선택하고 **이름에**대해 *GettingStartedClient* 를 입력합니다. **확인**을 선택합니다.

2. 어셈블리에 **GettingStartedClient** 프로젝트에서 <xref:System.ServiceModel> 참조를 추가합니다.

    1. 솔루션 **탐색기** 창에서 **GettingStartedClient** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **참조 추가를** 선택합니다.

    2. 참조 **추가** 창에서 창 왼쪽에 있는 **어셈블리** 아래에서 **프레임워크**를 선택합니다.

    3. **System.ServiceModel을**찾아서 선택한 다음 **확인을**선택합니다.

    4. **파일** > 저장 모두를 선택하여 솔루션을**저장합니다.**

3. 계산기 서비스에 서비스 참조추가:

   1. 솔루션 **탐색기** 창에서 **GettingStartedClient** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **서비스 참조 추가를** 선택합니다.

   2. 서비스 **참조 추가** 창에서 **검색을**선택합니다.

      계산기서비스 서비스가 시작되고 Visual Studio가 **서비스** 상자에 표시됩니다.

   3. **계산기 서비스를** 선택하여 확장하고 서비스에서 구현한 서비스 계약을 표시합니다. 기본 **네임스페이스를** 두고 **확인을**선택합니다.

      Visual Studio는 **GettingStartedClient** 프로젝트의 **연결된 서비스** 폴더 아래에 새 항목을 추가합니다.

### <a name="servicemodel-metadata-utility-tool"></a>서비스 모델 메타데이터 유틸리티 도구

다음 예제에서는 [서비스모델 메타데이터 유틸리티 도구(Svcutil.exe)를](servicemodel-metadata-utility-tool-svcutil-exe.md) 선택적으로 사용하여 프록시 클래스 파일을 생성하는 방법을 보여 준다. 이 도구는 프록시 클래스 파일과 *App.config* 파일을 생성합니다. 다음 예제에서는 각각 C# 및 Visual Basic에서 프록시를 생성하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 준다.

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>클라이언트 구성 파일

클라이언트를 만든 후 Visual Studio는 다음 예제와 유사해야 하는 **GettingStartedClient** 프로젝트에서 **App.config** 구성 파일을 만듭니다.

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

system.serviceModel>섹션에서 [ \<끝점>](../configure-apps/file-schema/wcf/endpoint-element.md) 요소를 확인합니다. [ \<](../configure-apps/file-schema/wcf/system-servicemodel.md) **끝점&gt; 요소는 클라이언트가 서비스에 액세스하는 데 사용하는 끝점을 다음과 같이 정의합니다. &lt;**

- 주소: `http://localhost:8000/GettingStarted/CalculatorService`. 엔드포인트의 주소입니다.
- 서비스 계약: `ServiceReference1.ICalculator`. 서비스 계약은 WCF 클라이언트와 서비스 간의 통신을 처리합니다. Visual Studio는 서비스 참조 **추가** 기능을 사용할 때 이 계약을 생성했습니다. 기본적으로 GettingStartedLib 프로젝트에서 정의한 계약의 복사본입니다.
- 바인딩: <xref:System.ServiceModel.WSHttpBinding>. 바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 정보로 지정합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업 방법을 알아보았습니다.
> [!div class="checklist"]
>
> - WCF 클라이언트에 대한 콘솔 앱 프로젝트를 만들고 구성합니다.
> - WCF 서비스에 서비스 참조를 추가하여 클라이언트 응용 프로그램에 대한 프록시 클래스 및 구성 파일을 생성합니다.

생성된 클라이언트를 사용하는 방법을 알아보려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [자습서: WCF 클라이언트 사용](how-to-use-a-wcf-client.md)
