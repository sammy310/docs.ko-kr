---
title: Windows 커뮤니케이션 재단 자습서 시작 문제 해결
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 92e986370fe1b6e067d9f8aebc73179c1ac6a20f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183088"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Windows 커뮤니케이션 재단 자습서 시작 문제 해결

이 문서에서는 [자습서: Windows 통신 Foundation 응용 프로그램을 시작할](getting-started-tutorial.md)때 직면할 수 있는 가장 일반적인 문제 및 오류에 대 한 솔루션을 제공 합니다.
  
## <a name="common-problems"></a>일반적인 문제

**하드 드라이브에서 프로젝트 파일을 찾을 수 없습니다.**

 Visual Studio는 *C:\\사용자\\&lt;사용자&gt;이름 \source\repos에*프로젝트 파일을 저장합니다.  

***Svcutil.exe에서*생성된 *App.config* 파일을 찾을 수 없습니다.**

 Visual Studio에서 **기존 항목 추가** 창에는 기본적으로 다음과 같은 확장명이 있는 파일만 표시됩니다.

- *.cs*
- *.resx*
- *.설정*
- *.xsd*
- *.wsdl*

모든 파일 형식을 표시하려면 **기존 항목 추가** 창의 오른쪽 아래 모서리에 있는 드롭다운 목록에서 모든 파일 **(.\*\*)을** 선택합니다.  
  
## <a name="common-errors"></a>일반 오류

### <a name="compile-the-service-application"></a>서비스 응용 프로그램 컴파일

**오류 BC30420 '하위 주'에서 '점점 시작 호스트.Module1'에서 찾을 수 없습니다.**

Visual Basic 응용 프로그램에 대한 진입점이 올바르지 않습니다. 다음을 변경합니다.

   1. 솔루션 **탐색기** 창에서 **GettingStartedHost** 폴더를 선택한 다음 바로 가기 메뉴에서 **속성을** 선택합니다.
    a. 시작 **시작 개체의** **GettingStartedHost** 창에서 목록에서 **Service.Program(또는** 특정 응용 프로그램의 진입점)을 선택합니다.
    b. 기본 메뉴에서 모두**저장** **파일을** > 선택합니다.

### <a name="run-the-service-application"></a>서비스 응용 프로그램 실행

**HTTP는 URL 'http:\//+8000/GettingStarted/계산기 서비스'를 등록할 수 없습니다. 프로세스에 이 네임스페이스에 대한 액세스 권한이 없습니다.**

 적절한 액세스를 위해 관리 권한이 있는 WCF(Windows Communication Foundation) 서비스를 호스팅하는 프로세스를 시작합니다.

- Visual Studio의 경우: **시작** 메뉴에서 Visual Studio 프로그램을 선택한 다음 바로 가기 메뉴에서**관리자로** **더 실행 을** > 선택합니다.
- 콘솔 창의 경우: **시작** 메뉴에서 **명령 프롬프트를** 선택한 다음 바로 가기 메뉴에서**관리자로** **더 실행 을** > 선택합니다.
- Windows 탐색기의 경우: 실행 을 선택한 다음 바로 가기 메뉴에서 **관리자로 실행을** 선택합니다.

### <a name="compile-the-client-application"></a>클라이언트 응용 프로그램 컴파일

**'CalculatorClient', '>\<메서드 이름'에 대한 정의가 포함되어\<있지 않으며 확장 메서드 '>'는 형식의 첫 번째 인수를 사용할 수 없습니다 (using 지시문 또는 어셈블리 참조가 누락되었습니까?)**  

`ServiceOperationAttribute` 특성으로 표시하는 메서드만 공개적으로 노출됩니다. 인터페이스의 `ServiceOperationAttribute` 메서드에서 특성을 `ICalculator` 생략하면 컴파일 중에 이 오류 메시지가 나타납니다.  

**형식 또는 네임스페이스 이름 'CalculatorClient'를 찾을 수 없습니다(using 지시문 또는 어셈블리 참조가 누락되었습니까?)**

 *Svcutil.exe* 도구를 사용하여 파일을 생성할 때 클라이언트 프로젝트에 *generatedProxy.cs(또는* *generatedProxy.vb)* 파일을 추가하지 않으면 이 오류가 발생합니다.  

### <a name="run-the-client-application"></a>클라이언트 응용 프로그램 실행

**처리되지 않은 예외: System.ServiceModel.EndpointNotFoundException: 'http:\//localhost:8000/시작/계산기 서비스'에 연결할 수 없습니다. TCP 오류 코드 10061: 대상 컴퓨터가 적극적으로 거부했기 때문에 연결할 수 없습니다.**

이 오류는 서비스를 처음 시작하지 않고 클라이언트 응용 프로그램을 실행하는 경우에 발생합니다. 먼저 호스트 응용 프로그램을 실행하여 서비스를 시작한 다음 클라이언트 응용 프로그램을 실행합니다.

### <a name="use-the-svcutilexe-tool"></a>Svcutil.exe 도구 사용

**'Svcutil'은 내부 또는 외부 명령, 작동 가능한 프로그램 또는 배치 파일로 인식되지 않습니다.**

 *Svcutil.exe는* 시스템 경로에 있어야 합니다. 가장 쉬운 해결책은 Visual Studio 명령 프롬프트를 사용하는 것입니다. **시작** 메뉴에서 Visual ** \<Studio 버전>** 디렉터리를 선택한 다음 VS ** \<버전>대한 개발자 명령 프롬프트를 **선택합니다. 이 명령 프롬프트는 Visual Studio의 일부로 제공된 모든 도구의 올바른 위치로 시스템 경로를 설정합니다.  
  
### <a name="run-the-service-and-client-applications"></a>서비스 및 클라이언트 응용 프로그램 실행

**System.ServiceModel.Security.SecurityNegotiationException: 'http:\//localhost:8000/GettingStarted/계산기 서비스'와 SOAP 보안 협상\/'http: /localhost:8000/GettingStarted/계산기 서비스' 실패**  

이 오류는 네트워크 연결이 없는 도메인 에 가입된 컴퓨터에서 발생합니다. 컴퓨터를 네트워크에 연결하거나 서비스와 클라이언트 모두에 대한 보안을 끕니다.

보안을 해제하려면 다음 을 수행하십시오.

- 서비스의 경우 다음 코드를 만드는 `WSHttpBinding` 코드를 바꿉니다.  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- 클라이언트의 경우 구성 파일에서 다음과 같이 바인딩 ** \<>** 요소 아래의 ** \<보안>** 요소를 업데이트합니다.  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>참고 항목  
 [WCF 응용 프로그램 시작하기](getting-started-tutorial.md)  
 [WCF 문제 해결 빠른 시작](wcf-troubleshooting-quickstart.md)  
 [설정 문제 해결](troubleshooting-setup-issues.md)
