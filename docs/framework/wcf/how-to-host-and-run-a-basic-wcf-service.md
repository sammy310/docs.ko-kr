---
title: '자습서: 기본 Windows 통신 재단 서비스 호스트 및 실행'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184078"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>자습서: 기본 Windows 통신 재단 서비스 호스트 및 실행

이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 세 번째 작업을 설명합니다. 자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.

WCF 응용 프로그램을 만드는 다음 작업은 콘솔 응용 프로그램에서 WCF 서비스를 호스트하는 것입니다. WCF 서비스는 하나 이상의 *끝점을*노출하며, 각 끝점은 하나 이상의 서비스 작업을 노출합니다. 서비스 끝점은 다음 정보를 지정합니다.

- 서비스를 찾을 수 있는 주소입니다.
- 클라이언트가 서비스와 통신하는 방법을 설명하는 정보를 포함하는 바인딩입니다.
- 서비스가 클라이언트에 제공하는 기능을 정의하는 계약입니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WCF 서비스를 호스팅하기 위한 콘솔 앱 프로젝트를 만들고 구성합니다.
> - WCF 서비스를 호스트하는 코드를 추가합니다.
> - 구성 파일을 업데이트합니다.
> - WCF 서비스를 시작하고 실행 중인지 확인합니다.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>서비스 호스팅을 위한 콘솔 앱 프로젝트 생성 및 구성

1. Visual Studio에서 콘솔 앱 프로젝트 만들기:

    1. **파일** 메뉴에서**프로젝트/솔루션** **열기를** > 선택하고 이전에 만든 **GettingStarted** *솔루션(GettingStarted.sln)을*찾아봅니다. **열기**를 선택합니다.

    2. **보기** 메뉴에서 **솔루션 탐색기를**선택합니다.

    3. 솔루션 **탐색기** 창에서 **GettingStarted** 솔루션(맨 위 노드)을 선택한 다음 바로 가기 메뉴에서**새 프로젝트** **추가를** > 선택합니다.

    4. 새 **프로젝트 추가** 창왼쪽에서 **Visual C#** 또는 **Visual Basic**에서 Windows **데스크톱** 범주를 선택합니다.

    5. 콘솔 **앱(.NET 프레임워크)** 템플릿을 선택하고 **이름에**대해 *GettingStartedHost를* 입력합니다. **확인**을 선택합니다.

2. **GettingStarted호스트** 프로젝트에 참조를 **추가합니다.**

    1. 솔루션 **탐색기** 창에서 **GettingStartedHost** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **참조 추가를** 선택합니다.

    2. 참조 **추가** 대화 상자에서 창 왼쪽에 있는 **프로젝트** 아래에서 **해결 을**선택합니다.

    3. 창의 가운데 섹션에서 **시작 해제** 를 선택한 다음 **확인을**선택합니다.

       이 작업을 수행하면 **GettingStartedLib** 프로젝트에 정의된 형식을 **GettingStartedHost** 프로젝트에서 사용할 수 있습니다.

3. 어셈블리에 **GettingStartedHost** 프로젝트에서 <xref:System.ServiceModel> 참조를 추가합니다.

    1. 솔루션 **탐색기** 창에서 **GettingStartedHost** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **참조 추가를** 선택합니다.

    2. 참조 **추가** 창에서 창 왼쪽에 있는 **어셈블리** 아래에서 **프레임워크**를 선택합니다.

    3. **System.ServiceModel을**선택한 다음 **확인을**선택합니다.

    4. **파일** > 저장 모두를 선택하여 솔루션을**저장합니다.**

## <a name="add-code-to-host-the-service"></a>서비스를 호스트하는 코드 추가

서비스를 호스트하려면 다음 단계를 수행하는 코드를 추가합니다.

1. 기본 주소에 대한 URI를 만듭니다.
2. 서비스를 호스팅하기 위한 클래스 인스턴스를 만듭니다.
3. 서비스 끝점을 만듭니다.
4. 메타데이터 교환을 사용하도록 설정합니다.
5. 서비스 호스트를 열어 들어오는 메시지를 수신합니다.
  
코드를 다음과 같이 변경합니다.

1. **GettingStartedHost** 프로젝트에서 **Program.cs** 또는 **Module1.vb** 파일을 열고 코드를 다음 코드로 바꿉니다.

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    이 코드의 작동 방식에 대한 자세한 내용은 [서비스 호스팅 프로그램 단계를](#service-hosting-program-steps)참조하십시오.

2. 프로젝트 속성 업데이트:

   1. 솔루션 **탐색기** 창에서 **GettingStartedHost** 폴더를 선택한 다음 바로 가기 메뉴에서 **속성을** 선택합니다.

   2. **GettingStartedHost** 속성 페이지에서 응용 **프로그램** 탭을 선택합니다.

      - C# 프로젝트의 경우 **시작 개체** 목록에서 **GettingStartedHost.Program을** 선택합니다.

      - 시각적 기본 프로젝트의 경우 **시작 개체** 목록에서 **Service.Program을** 선택합니다.

   3. **파일** 메뉴에서 **모두 저장을**선택합니다.

## <a name="verify-the-service-is-working"></a>서비스가 작동하는지 확인

1. 솔루션을 빌드한 다음 Visual Studio 내부에서 **GettingStartedHost** 콘솔 응용 프로그램을 실행합니다.

    서비스는 관리자 권한으로 실행되어야 합니다. 관리자 권한으로 Visual Studio를 열었기 때문에 Visual Studio에서 **GettingStartedHost를** 실행할 때 응용 프로그램도 관리자 권한으로 실행됩니다. 또는 관리자로 새 명령 프롬프트를 열고(바로 가기 메뉴에서**관리자로** **더 실행 추가** > 를 선택) 그 안에 **GettingStartedHost.exe를** 실행할 수 있습니다.

2. 웹 브라우저를 열고 에서 `http://localhost:8000/GettingStarted/CalculatorService`서비스 페이지로 이동합니다.

   > [!NOTE]
   > 이와 같은 서비스는 수신대기를 위해 컴퓨터에 HTTP 주소를 등록할 수 있는 적절한 권한이 필요합니다. 관리자 계정에는 이 권한이 있지만, 관리자 이외의 계정에는 HTTP 네임스페이스에 대한 권한을 부여해야 합니다. 네임스페이스 예약을 구성하는 방법에 대한 자세한 내용은 [HTTP 및 HTTPS 구성](feature-details/configuring-http-and-https.md)을 참조하세요.

## <a name="service-hosting-program-steps"></a>서비스 호스팅 프로그램 단계

서비스를 호스트하기 위해 추가한 코드의 단계는 다음과 같습니다.

- **1단계**: 서비스의 기본 `Uri` 주소를 보유할 클래스의 인스턴스를 만듭니다. 기본 주소를 포함하는 URL에는 서비스를 식별하는 선택적 URI가 있습니다. 기본 주소는 다음과 같이 `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`서식이 지정됩니다. 계산기 서비스의 기본 주소는 HTTP 전송, 로컬 호스트, 포트 8000 및 URI 세그먼트인 GettingStarted를 사용합니다.

- **2단계**: 서비스를 호스트하는 데 사용하는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만듭니다. 생성자는 서비스 계약을 구현하는 클래스의 형식과 서비스의 기본 주소라는 두 가지 매개 변수를 사용합니다.

- **3단계**: <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스를 만듭니다. 서비스 엔드포인트는 주소, 바인딩 및 서비스 계약으로 구성되어 있습니다. 생성자는 <xref:System.ServiceModel.Description.ServiceEndpoint> 서비스 계약 인터페이스 유형, 바인딩 및 주소로 구성됩니다. 서비스 계약은 사용자가 정의한 `ICalculator`이며 서비스 형식에 구현합니다. 이 샘플의 바인딩은 <xref:System.ServiceModel.WSHttpBinding>기본 제공 바인딩이며 WS-* 사양을 준수하는 끝점에 연결됩니다. WCF 바인딩에 대한 자세한 내용은 [WCF 바인딩 개요를](bindings-overview.md)참조하십시오. 주소를 기본 주소에 부가하여 끝점을 식별합니다. 코드는 주소를 CalculatorService로 지정하고 끝점에 대해 정규화된 `http://localhost:8000/GettingStarted/CalculatorService`주소를 로 지정합니다.

    > [!IMPORTANT]
    > .NET 프레임워크 버전 4 이상에 대한 서비스 끝점을 추가하는 것은 선택 사항입니다. 이러한 버전의 경우 코드 또는 구성을 추가하지 않는 경우 WCF는 서비스에서 구현한 기본 주소와 계약의 각 조합에 대해 하나의 기본 끝점을 추가합니다. 기본 끝점에 대한 자세한 내용은 [끝점 주소 지정을](specifying-an-endpoint-address.md)참조하십시오. 기본 끝점, 바인딩 및 동작에 대한 자세한 내용은 WCF 서비스에 대한 [단순화된 구성](simplified-configuration.md) 및 [단순화된 구성을](samples/simplified-configuration-for-wcf-services.md)참조하십시오.

- **4단계**: 메타데이터 교환을 활성화합니다. 클라이언트는 메타데이터 교환을 사용하여 서비스 작업을 호출하기 위한 프록시를 생성합니다. 메타데이터 교환을 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 사용하려면 인스턴스를 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> 만들고 `true`의 속성을 `ServiceMetadataBehavior` 로 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 설정하고 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스 컬렉션에 추가합니다.

- **5 단계** <xref:System.ServiceModel.ServiceHost> : 들어오는 메시지를 듣기 위해 열립니다. 응용 프로그램은 **Enter**를 누를 때까지 기다립니다. 응용 프로그램이 인스턴스화되면 <xref:System.ServiceModel.ServiceHost>try/catch 블록을 실행합니다. throw된 <xref:System.ServiceModel.ServiceHost>예외를 안전하게 catch하는 자세한 내용은 [닫기 및 중단 을 사용하여 WCF 클라이언트 리소스를 해제합니다.](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> WCF 서비스 라이브러리를 추가하면 서비스 호스트를 시작하여 디버깅하는 경우 Visual Studio에서 호스트합니다. 충돌을 방지하려면 Visual Studio에서 WCF 서비스 라이브러리를 호스팅하지 못하도록 할 수 있습니다.
>
> 1. **솔루션 탐색기에서** **GettingStartedLib** 프로젝트를 선택하고 바로 가기 메뉴에서 **속성을** 선택합니다.
> 2. **동일한 솔루션에서 다른 프로젝트를 디버깅할 때** **WCF 옵션을** 선택하고 WCF 서비스 호스트 시작을 선택 취소합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업 방법을 알아보았습니다.
> [!div class="checklist"]
>
> - WCF 서비스를 호스팅하기 위한 콘솔 앱 프로젝트를 만들고 구성합니다.
> - WCF 서비스를 호스트하는 코드를 추가합니다.
> - 구성 파일을 업데이트합니다.
> - WCF 서비스를 시작하고 실행 중인지 확인합니다.

WCF 클라이언트를 만드는 방법을 알아보려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [자습서: WCF 클라이언트 만들기](how-to-create-a-wcf-client.md)
