---
title: Windows Communication Foundation 샘플의 일회 설치 절차
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 954ec04d2ef1ca7667b4f75a8a6652010b5dbd33
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121624"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Windows Communication Foundation 샘플의 일회 설치 절차

대부분의 WCF(Windows 통신 재단) 샘플은 IIS(인터넷 정보 서비스)에서 호스팅되며 공통 가상 디렉터리에서 실행됩니다. 이 일회성 설치 절차는 디스크에 폴더를 만듭니다. 또한 IIS라는 서비스 모델 샘플에 가상 **디렉터리를 추가합니다.**

**ServiceModelSamples** 가상 디렉터리는 IIS 호스팅 서비스를 사용하는 모든 샘플을 빌드하고 실행하는 데 사용됩니다. 이 디렉터리는 샘플을 실행하는 데 필요한 유일한 가상 디렉터리입니다. 샘플을 빌드하면 이 가상 디렉터리에서 이전에 배포된 서비스가 대체되고 가장 최근에 빌드된 샘플만 배포되어 이 가상 디렉터리에서 사용할 수 있게 됩니다.

> [!NOTE]
> 모든 명령을 로컬 관리자 계정으로 실행해야 합니다. Windows 7, Windows Vista 또는 Windows Server 2008 R2를 사용하는 경우 권한 상승 권한으로 명령 프롬프트도 실행해야 합니다. 이렇게 하려면 명령 프롬프트 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **관리자로 실행 을**클릭합니다. 이 항목의 모든 명령은 경로 설정이 적절한 명령 프롬프트에서 실행해야 합니다.  이를 위한 가장 쉬운 방법은 Visual Studio 명령 프롬프트를 사용하는 것입니다. 이 프롬프트를 열려면 **시작**, 선택 , **모든 프로그램**선택, Visual **Studio 2010으로**스크롤, **Visual Studio 도구**선택, Visual Studio **명령 프롬프트(2010)를**마우스 오른쪽 단추로 클릭한 다음 **관리자로 실행을**클릭합니다. Visual Studio Express Edition 중 하나가 설치되어 있어 이 명령 프롬프트를 사용할 수 없는 경우에는 시스템 경로에 "C:\Windows\Microsoft.Net\Framework\v4.0"을 추가해야 합니다.

### <a name="one-time-setup-procedure-for-wcf-samples"></a>WCF 샘플의 일회 설치 절차

1. ASP.NET 설정되어 있는지 확인합니다. ASP.NET 설정하는 방법에 대한 자세한 내용은 [인터넷 정보 서비스 호스팅 지침을](internet-information-service-hosting-instructions.md)참조하십시오.

2. .NET 프레임워크 4가 설치되어 있는지 확인합니다. v4.0 (이상)에 대한 다음 디렉토리를 검색 : **\Windows\Microsoft.NET \프레임 워크**

3. Visual Studio 2012 이상설치되어 있거나 운영 체제가 Windows Server 2008 SP2 이상인지 확인합니다.

4. 다음 명령을 실행합니다. 이러한 명령을 실행해야 하는 이유에 대한 자세한 내용은 [IIS 호스팅 서비스 실패](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90))를 참조하십시오.

    > [!WARNING]
    > IIS가 다시 설치된 경우 다음 명령을 다시 실행해야 합니다.

    ```console
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    > 명령을 `aspnet_regiis –i –enable` 실행하면 .NET Framework 4를 사용하여 기본 앱 풀을 실행하게 되며, 이 경우 동일한 컴퓨터의 다른 응용 프로그램에 대한 비호환성 문제가 발생할 수 있습니다.

5. 샘플에서 사용하는 포트를 사용하도록 설정하기 위한 [방화벽 지침을](firewall-instructions.md) 따릅니다.

6. 다음과 같은 기본 디렉토리: \<InstallDrive> 확인:**\WF_WCF_Samples**. 샘플이 이전에 설치된 경우 이 디렉터리가 기본 디렉터리입니다.

7. 샘플이 설치되지 않은 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로파) 샘플에서](https://www.microsoft.com/download/details.aspx?id=21459)샘플을 설치합니다.

8. 샘플을 설치한 후 : \<설치 드라이브> :**\WF_WCF_Samples\WCF\설치\\ **

9. **Setupvroot.bat** 일괄 처리 파일을 실행합니다. 다음 단계를 수행합니다.

    - IIS에 ServiceModelSamples라는 가상 디렉터리가 만들어집니다.

    - %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples and %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin이라는 새 디스크 디렉터리가 만들어집니다.

    이러한 디렉터리를 수동으로 설정하려면 [가상 디렉터리 설정 지침을](virtual-directory-setup-instructions.md)참조하십시오. 이 단계에서 수행한 모든 변경 작업을 되돌리려면 샘플 사용을 마친 후 cleanupvroot.bat를 실행합니다.

    > [!NOTE]
    > cleanupvroot.bat가 실행되지 않은 경우 이 절차는 한 컴퓨터에서 한 번만 수행해야 합니다.

10. 샘플을 빌드 중인 계정과 Network Service 사용자에 %SystemDrive%\inetpub\wwwroot에 대한 수정 권한을 부여해야 합니다. 빌드하는 동안 일부 웹 호스팅 샘플은 컴파일된 이진 파일을 앞에서 설명한 위치에 복사하려고 시도하므로 적절한 사용 권한이 설정되지 않은 경우 빌드가 중지됩니다. 또는 사용 권한을 그대로 두고 SDK 명령 프롬프트 또는 Visual Studio 명령 프롬프트(2012)를 관리자로 실행하거나 Visual Studio 2012에서 샘플을 빌드하여 관리자로 실행할 수도 있습니다.

    > [!NOTE]
    > 이 단계를 완료하지 않으면 IIS에서 호스팅되는 모든 샘플이 빌드 중에 실패합니다. 사용 권한을 올바르게 설정했는지 확인하거나 SDK 명령 프롬프트와 Visual Studio 명령 프롬프트(2012)를 관리자 권한으로 실행하십시오.

11. 컴퓨터에 C:\logs 디렉터리를 만듭니다. 일부 샘플에 이 디렉터리가 필요할 수 있습니다. 적절한 계정에 이 폴더에 대한 쓰기 권한을 부여해야 합니다. Windows 7, Windows Vista 및 Windows 서버 2008 R2의 경우 이 계정은 **네트워크 서비스입니다.** Windows Server 2008의 경우 계정은 NT 기관\네트워크 서비스입니다. Windows XP 및 Windows 서버 2003의 경우 계정은 ASPNET입니다.

12. Setupcerttool.bat 파일을 실행합니다. 이 파일은 \<설치 경로>\WF_WCF_Samples\WCF\설치\ 폴더에 있습니다.  이 스크립트는 다음 작업을 수행합니다.

    - FindPrivateKey 도구를 빌드합니다.

    - %ProgramFiles%\ServiceModelSampleTools라는 디렉터리를 만듭니다.

    - 이 디렉터리에 새 FindPrivateKey 도구를 복사합니다.

    이 도구는 인증서를 사용하고 IIS에서 호스팅되는 샘플에 필요합니다.

    > [!NOTE]
    > 보안을 위해 샘플 사용이 끝나면 Cleanupvroot.bat라는 배치 파일을 실행하여 설치 단계에서 부여된 가상 디렉터리 정의와 사용 권한을 제거해야 합니다.

13. IIS에서 호스팅되지 않고 자체 호스팅되는 샘플의 경우 수신 대기를 위해 컴퓨터에서 HTTP 주소를 등록할 수 있는 권한이 필요합니다. HTTP 네임스페이스 예약을 위한 사용 권한은 샘플을 실행하는 데 사용되는 사용자 계정에서 제공됩니다. 기본적으로 관리자 계정에는 모든 HTTP 주소를 등록할 수 있는 사용 권한이 있습니다. 관리자 이외의 계정에는 샘플에 사용되는 HTTP 네임스페이스에 대한 권한을 부여해야 합니다. 네임스페이스 예약을 구성하는 방법에 대한 자세한 내용은 [HTTP 및 HTTPS 구성](../feature-details/configuring-http-and-https.md)을 참조하세요.

14. 일부 샘플에는 메시지 큐가 필요합니다. 설치 지침은 [MSMQ(메시지 대기열 설치)를](installing-message-queuing-msmq.md) 참조하십시오.

    > [!NOTE]
    > 메시지 큐가 필요한 샘플을 실행하려면 먼저 MSMQ 서비스를 시작해야 합니다.

15. 일부 샘플에는 인증서가 필요합니다. [IIS(인터넷 정보 서비스) 서버 인증서 설치 지침을](iis-server-certificate-installation-instructions.md)참조하십시오.
