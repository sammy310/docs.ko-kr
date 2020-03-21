---
title: Windows용 WCF 서비스 및 이벤트 추척
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183208"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Windows용 WCF 서비스 및 이벤트 추척
이 샘플에서는 WCF(Windows 통신 재단)의 분석 추적을 사용하여 ETW(Windows용 이벤트 추적)에서 이벤트를 내보하는 방법을 보여 줍니다. 분석 추적은 프로덕션 환경에서 WCF 서비스 문제를 해결할 수 있는 WCF 스택의 핵심 지점에서 내보낸 이벤트입니다.

 WCF 서비스의 분석 추적은 성능에 미치는 영향을 최소화하면서 프로덕션 환경에서 켜질 수 있는 추적입니다. 이러한 추적은 ETW 세션에 이벤트로 내보내집니다.

 이 샘플에는 이벤트 뷰어를 사용하여 볼 수 있는 이벤트로 이벤트가 서비스에서 이벤트로 내보내지는 기본 WCF 서비스가 포함되어 있습니다. WCF 서비스의 이벤트를 수신하는 전용 ETW 세션을 시작할 수도 있습니다. 이 샘플에는 이벤트 뷰어를 사용하여 읽을 수 있는 이진 파일에 이벤트를 저장하는 전용 ETW 세션을 만드는 스크립트가 포함되어 있습니다.

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Visual Studio 2012를 사용하여 EtwAnalyticTraceSample.sln 솔루션 파일을 엽니다.

2. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

3. Ctrl+F5를 눌러 솔루션을 실행합니다.

     웹 브라우저에서 **계산기.svc를 클릭합니다.** 서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다. 이 URI를 복사합니다.

     기본적으로 서비스는 포트 1378에서 `http://localhost:1378/Calculator.svc`요청을 수신 대기하기 시작합니다.

4. WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.

     WCF 테스트 클라이언트(WcfTestClient.exe)는 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`에 있습니다.  기본 Visual Studio 2012 `C:\Program Files\Microsoft Visual Studio 10.0`설치 dir은 .

5. WCF 테스트 클라이언트 내에서 **파일**을 선택한 다음 **서비스 추가를**선택하여 서비스를 추가합니다.

     입력 상자에 엔드포인트 주소를 추가합니다. 기본값은 `http://localhost:1378/Calculator.svc`입니다.

6. 이벤트 뷰어 애플리케이션을 엽니다.

     서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 WCF 서비스에서 내보낸 이벤트를 추적하는 지 확인합니다.

7. **시작** 메뉴에서 **관리 도구를**선택한 다음 이벤트 **뷰어**를 선택합니다.  **분석** 및 **디버그** 로그를 활성화합니다.

8. 이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows**및 응용 프로그램 서버 응용 **프로그램으로 이동합니다.** **응용 프로그램 서버-응용 프로그램을**마우스 오른쪽 단추로 클릭하고 **보기를**선택한 다음 분석 및 디버그 로그 표시 를 **선택합니다.**

     **분석 및 디버그 로그 표시** 옵션이 선택되어 있는지 확인합니다.

9. 분석 로그를 **활성화합니다.**

     이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows**및 응용 프로그램 서버 응용 **프로그램으로 이동합니다.** **분석** 클릭하고 **로그 사용 을**선택합니다.

#### <a name="to-test-the-service"></a>서비스를 테스트하려면

1. WCF 테스트 클라이언트로 다시 전환하고 두 번 클릭하고 `Divide` 분모를 0으로 지정하는 기본값을 유지합니다.

     분모가 0이면 서비스에서는 오류를 throw합니다.

2. 서비스에서 내보낸 이벤트를 확인합니다.

     이벤트 뷰어로 다시 전환 하고 **이벤트 뷰어로**이동 , **응용 프로그램 및 서비스 로그**, **마이크로 소프트**, **윈도우**, 다음 응용 프로그램 서버 **응용 프로그램**. **분석** 단추를 클릭하고 **새로 고침을**선택합니다.

     WCF 분석 추적 이벤트가 이벤트 뷰어에 표시됩니다. 서비스에서 오류가 throw되었으므로 이벤트 뷰어에 오류 추적 이벤트가 표시됩니다.

3. 1-2단계를 반복하되 이번에는 유효한 입력을 사용합니다. `N2` 매개 변수 값으로는 0 이외의 모든 숫자를 사용할 수 있습니다.

     분석 채널을 새로 고쳐 WCF 이벤트에 오류 이벤트가 포함되어 있지 않은지 확인합니다.

 이 샘플에서는 WCF 서비스에서 내보낸 분석 추적 이벤트를 보여 줍니다.

#### <a name="to-cleanup-optional"></a>정리하려면(옵션)

1. 이벤트 뷰어를 엽니다.

2. 이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft**, **Windows**및 **응용 프로그램-서버-응용 프로그램으로**이동합니다. 분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 사용 안 함**선택.

3. 이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft**, **Windows**및 **응용 프로그램-서버-응용 프로그램으로**이동합니다. 분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 지우기**를 선택합니다.

4. 이벤트를 지우려면 **지우기** 옵션을 선택합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>참고 항목

- [AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
