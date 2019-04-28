---
title: Get 문제 해결 Windows Communication Foundation 자습서 시작
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 8089e0fee262d07be591069982b1aacfbeae2521
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791471"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Get 문제 해결 Windows Communication Foundation 자습서 시작

이 문서에서는 가장 일반적인 문제 및 오류에 단계를 수행할 때 발생할 수에 대 한 솔루션을 제공 합니다 [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다. 
  
## <a name="common-problems"></a>일반적인 문제

**하드 드라이브에 있는 프로젝트 파일을 찾을 수 없습니다.**

 Visual Studio에서 프로젝트 파일을 저장 *C:\Users\\&lt;사용자 이름&gt;\source\repos*합니다.  

**찾을 수 없습니다. 합니다 *App.config* 에서 생성 된 파일 *Svcutil.exe*합니다.**

 Visual Studio에는 **기존 항목 추가** 창 기본적으로 다음 확장을 사용 하 여 파일에 표시 합니다. 
- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

모든 파일 형식을 표시 하려면 선택한 **모든 파일 (\*.\*)**  의 오른쪽 아래 모서리에 있는 드롭다운 목록에는 **기존 항목 추가** 창입니다.  
  
## <a name="common-errors"></a>일반적인 오류

### <a name="compile-the-service-application"></a>서비스 응용 프로그램 컴파일 

**오류 BC30420 'GettingStartedHost.Module1'에서 ' Sub Main'를 찾을 수 없습니다.**

진입점은 Visual Basic 응용 프로그램에 대해 올바르지 않습니다. 다음과 같이 변경 합니다.

   1. 에 **솔루션 탐색기** 창에서 합니다 **GettingStartedHost** 폴더를 선택한 후 **속성** 바로 가기 메뉴에서.
    a. 에 **GettingStartedHost** 창에 대 한 **시작 개체**를 선택 **Service.Program** (또는 특정 응용 프로그램에 대 한 진입점) 목록에서. 
    b. 주 메뉴에서 선택 **파일** > **모두 저장**합니다.

### <a name="run-the-service-application"></a>서비스 응용 프로그램 실행 

**HTTP URL을 등록할 수 없습니다. ' http:\// +: 8000/GettingStarted/CalculatorService '. 사용자의 프로세스에 이 네임스페이스에 액세스할 수 있는 권한이 없습니다.** 

 적절 한 액세스에 대 한 관리자 권한으로 Windows Communication Foundation (WCF) 서비스를 호스트 하는 프로세스를 시작:
- Visual studio: Visual Studio 프로그램을 선택 합니다 **시작** 메뉴를 선택한 후 **자세한** > **관리자 권한으로 실행** 바로 가기 메뉴에서.
- 콘솔 창의 경우: 선택 **명령 프롬프트** 에 **시작** 메뉴를 선택한 후 **자세한** > **관리자 권한으로 실행** 바로 가기에서 메뉴입니다.
- Windows 탐색기: 실행 파일을 선택한 후 **관리자 권한으로 실행** 바로 가기 메뉴에서.

### <a name="compile-the-client-application"></a>클라이언트 응용 프로그램 컴파일

**'CalculatorClient'에 대 한 정의가 없습니다. '\<메서드 이름 >' 및 확장 메서드 '\<메서드 이름 >' 찾을 수 없습니다 'CalculatorClient' 형식의 첫 번째 인수를 허용 (사용 하는 누락 된 지시문 또는 어셈블리 참조?)**  

사용 하 여 표시 하는 방법만을 `ServiceOperationAttribute` 특성은 공개적으로 노출 합니다. 생략 하면는 `ServiceOperationAttribute` 특성에서 메서드에 `ICalculator` 인터페이스를 컴파일하는 동안이 오류 메시지를 수신 합니다.  

**'CalculatorClient'를 찾을 수 없는 형식 또는 네임 스페이스 이름 (사용 하는 누락 된 지시문 또는 어셈블리 참조가?)**

 추가 하지 않으면이 오류를 수신 합니다 *generatedProxy.cs* (또는 *generatedProxy.vb*) 파일을 사용 하 여 생성 하는 경우 클라이언트 프로젝트를 *Svcutil.exe* 도구 .  

### <a name="run-the-client-application"></a>클라이언트 응용 프로그램 실행

**처리 되지 않은 예외: System.ServiceModel.EndpointNotFoundException: 에 연결 하지 못했습니다 ' http:\//localhost:8000 GettingStarted/CalculatorService '. TCP 오류 코드 10061: 대상 컴퓨터에서 적극적으로 거부 없음 연결을 설정할 수 없습니다.**

첫 번째 서비스를 시작 하지 않고 클라이언트 응용 프로그램을 실행 하면이 오류가 발생 합니다. 먼저 서비스를 시작 하려면 호스트 응용 프로그램을 실행 하 고 클라이언트 응용 프로그램을 실행 합니다.

### <a name="use-the-svcutilexe-tool"></a>Svcutil.exe 도구를 사용 합니다.
   
**'Svcutil' 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일이 인식 되지 않습니다.**

 *Svcutil.exe* 시스템 경로에 있어야 합니다. 가장 쉬운 해결 방법은 Visual Studio 명령 프롬프트를 사용 하는 것입니다. **시작** 메뉴를 선택 합니다 **Visual Studio \<버전 >** 디렉터리를 선택 **VS 용 개발자 명령 프롬프트 \<버전 >**. 이 명령 프롬프트는 Visual Studio의 일부로 제공 되는 모든 도구에 대 한 올바른 위치를 시스템 경로 설정 합니다.  
  
### <a name="run-the-service-and-client-applications"></a>서비스 및 클라이언트 응용 프로그램 실행

**System.ServiceModel.Security.SecurityNegotiationException: SOAP 보안 협상을 사용 하 여 ' http:\//localhost:8000 GettingStarted/CalculatorService ' 대상에 대 한 ' http:\//localhost:8000 GettingStarted/CalculatorService ' 실패**  

네트워크 연결 되지 않은 도메인에 가입 된 컴퓨터에서이 오류가 발생 합니다. 네트워크에 컴퓨터를 연결 하거나 서비스와 클라이언트 모두에 대 한 보안을 해제 합니다. 

보안 해제 하려면:

- 서비스를 만드는 코드를 대체 합니다 `WSHttpBinding` 다음 코드를 사용 하 여:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- 클라이언트 구성 파일에 대 한 업데이트를  **\<보안 >** 아래에 있는 요소를  **\<바인딩 >** 다음과 같은 요소:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>참고자료  
 [WCF 응용 프로그램 시작](getting-started-tutorial.md)  
 [WCF 문제 해결 퀵 스타트](wcf-troubleshooting-quickstart.md)  
 [설치 문제 해결](troubleshooting-setup-issues.md)
