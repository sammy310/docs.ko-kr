---
title: '자습서: Windows Communication Foundation 클라이언트 만들기'
ms.dat8: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 051275e56a8e63c6ab8136dbb9e24bdcf4c387df
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411859"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>자습서: Windows Communication Foundation 클라이언트 만들기

이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 네 번째를 설명 합니다. 자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.

WCF 응용 프로그램을 만드는 다음 작업을 WCF 서비스에서 메타 데이터를 검색 하 여 클라이언트를 만드는 것입니다. Visual Studio를 사용 하 여 서비스의 MEX 끝점에서 메타 데이터를 가져오는 서비스 참조를 추가 합니다. 그러면 visual Studio 사용자가 선택한 언어로 클라이언트 프록시에 대 한 관리 되는 소스 코드 파일을 생성 합니다. 또한 클라이언트 구성 파일을 만듭니다 (*App.config*). 이 파일에는 클라이언트 응용 프로그램을 서비스 끝점에 연결할 수 있습니다. 

> [!NOTE]
> Visual Studio에서 클래스 라이브러리 프로젝트에서 WCF 서비스를 호출 하는 경우 사용 합니다 **서비스 참조 추가** 프록시 및 관련된 구성 파일을 자동으로 생성 하는 기능입니다. 그러나 클래스 라이브러리 프로젝트에서이 구성 파일을 사용 하지 때문에 추가 해야 설정을 생성 된 구성 파일에는 *App.config* 클래스 라이브러리를 호출 하는 파일입니다.

> [!NOTE]
> 대신 사용 합니다 [ServiceModel Metadata 유틸리티 도구](#servicemodel-metadata-utility-tool) 프록시 클래스와 구성 파일을 생성 하기 위해 Visual Studio 대신 합니다.

클라이언트 응용 프로그램은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다. 이 절차에 설명 되어 [자습서: 클라이언트를 사용 하 여](how-to-use-a-wcf-client.md)입니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
> - 만들고 WCF 클라이언트에 대 한 콘솔 앱 프로젝트를 구성 합니다.
> - 프록시 클래스와 구성 파일을 생성 하는 WCF 서비스에 대 한 서비스 참조를 추가 합니다.


## <a name="create-a-windows-communication-foundation-client"></a>Windows Communication Foundation 클라이언트 만들기

1. Visual Studio에서 콘솔 앱 프로젝트를 만듭니다. 

    1. **파일** 메뉴에서 **열기** > **프로젝트/솔루션** 로 이동한 합니다 **GettingStarted** 솔루션 있습니다 이전에 만든 (*GettingStarted.sln*). **열기**를 선택합니다.

    2. **뷰** 메뉴에서 **솔루션 탐색기**합니다.

    3. 에 **솔루션 탐색기** 창에서 선택 합니다 **GettingStarted** 솔루션 (최상위 노드)를 선택한 후 **추가** > **새 프로젝트** 바로 가기 메뉴에서. 
    
    4. 에 **새 프로젝트 추가** 창의 왼쪽된에 있는 선택 합니다 **Windows Desktop** 에서 범주 **Visual C#**  또는 **Visual Basic**. 

    5. 선택 합니다 **콘솔 앱 (.NET Framework)** 템플릿을 enter *GettingStartedClient* 에 대 한 합니다 **이름**합니다. **확인**을 선택합니다.

2. 참조를 추가 합니다 **GettingStartedClient** 프로젝트를 <xref:System.ServiceModel> 어셈블리: 

    1.  에 **솔루션 탐색기** 창에서를 **참조** 아래에 폴더를 **GettingStartedClient** 프로젝트를 선택한 후 **참조추가** 바로 가기 메뉴에서. 

    2. 에 **참조 추가** 창 아래에 있는 **어셈블리** 창의 왼쪽에서 선택 **Framework**합니다.
    
    3. 찾기 및 선택 **System.ServiceModel**를 선택한 후 **확인**합니다. 

    4. 선택 하 여 솔루션을 저장할 **파일** > **모두 저장**합니다.

3. 계산기 서비스에 대 한 서비스 참조를 추가 합니다.

   1. 에 **솔루션 탐색기** 창에서 합니다 **참조** 아래에 폴더를 **GettingStartedClient** 프로젝트를 선택한 후 **서비스 참조 추가**  바로 가기 메뉴에서.

   2. 에 **서비스 참조 추가** 창에서 **Discover**합니다.

      CalculatorService 서비스 시작 및 Visual Studio에 표시 된 **Services** 상자입니다.

   3. 선택 **CalculatorService** 여 확장 하 고 서비스에서 구현 되는 서비스 계약을 표시 합니다. 기본값을 그대로 두고 **Namespace** 선택한 **확인**합니다.

      Visual Studio에서 새 항목을 추가 합니다 **연결 된 서비스** 폴더에는 **GettingStartedClient** 프로젝트입니다. 


### <a name="servicemodel-metadata-utility-tool"></a>ServiceModel Metadata 유틸리티 도구

다음 예에서는 선택적으로 사용 하는 방법을 보여 줍니다 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 프록시 클래스 파일을 생성 합니다. 이 도구는 프록시 클래스 파일을 생성 하며 *App.config* 파일입니다. 다음 예제에서 프록시를 생성 하는 방법을 보여 줍니다 C# 및 Visual Basic의 경우 각각:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>클라이언트 구성 파일

클라이언트를 만든 후 Visual Studio 만듭니다는 **App.config** 에서 구성 파일을 **GettingStartedClient** 다음 예제와 유사 해야 하는 프로젝트:

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

아래는 [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) 섹션을 확인 합니다 [ \<끝점 >](../configure-apps/file-schema/wcf/endpoint-element.md) 요소입니다. 합니다 **&lt;끝점&gt;** 요소는 다음과 같이 서비스에 액세스 하는 클라이언트 끝점을 정의 합니다.
- 주소: `http://localhost:8000/GettingStarted/CalculatorService`합니다. 엔드포인트의 주소입니다.
- 서비스 계약: `ServiceReference1.ICalculator`합니다. WCF 클라이언트와 서비스 간의 통신을 처리 하는 서비스 계약입니다. Visual Studio에서이 계약 생성 하는 데 사용 하는 경우 해당 **서비스 참조 추가** 함수입니다. 본질적으로 GettingStartedLib 프로젝트에 정의 된 계약의 복사본 것입니다. 
- 바인딩: <xref:System.ServiceModel.WSHttpBinding>합니다. HTTP 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정 하는 바인딩.

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
> - 만들고 WCF 클라이언트에 대 한 콘솔 앱 프로젝트를 구성 합니다.
> - 클라이언트 응용 프로그램에 대 한 프록시 클래스와 구성 파일을 생성 하는 WCF 서비스에 대 한 서비스 참조를 추가 합니다.

생성된 된 클라이언트를 사용 하는 방법을 알아보려면 다음 자습서로 이동 합니다.

> [!div class="nextstepaction"]
> [자습서: WCF 클라이언트를 사용 합니다.](how-to-use-a-wcf-client.md)


