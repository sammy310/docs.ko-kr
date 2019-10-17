---
title: WCF 서비스 게시
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 90d2a841fa5ce14b1ad5295b3bb6493df0350339
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321231"
---
# <a name="wcf-service-publishing"></a>WCF 서비스 게시

Wcf (Windows Communication Foundation) 서비스 게시를 사용 하면 WCF 서비스 호스트 및 WCF 테스트 클라이언트에서 제공 하는 초기 개발 환경에서 테스트를 위해 실제로 응용 프로그램을 프로덕션 환경에 배포 하는 데 도움이 됩니다. 최종 배포 계획을 커밋하기 전에 wcf (Windows Communication Foundation) 서비스 게시를 사용 하 여 WCF 서비스가 올바르게 수행 되 고 게시할 준비가 되었는지 확인할 수 있습니다. 테스트를 위해 WCF 서비스 라이브러리를 다양 한 대상 위치에 배포 하도록 선택할 수도 있습니다.

## <a name="supported-services-and-target-locations"></a>지원되는 서비스 및 대상 위치

WCF 서비스 게시는 WCF 서비스 라이브러리 템플릿 집합에서 만든 WCF 서비스와 해당 항목 템플릿 (다음을 포함)을 게시할 수 있도록 지원 합니다.

- 항목 템플릿이 있는 WCF 서비스 라이브러리 템플릿

- 배포 서비스 라이브러리

**파일**  > **새 프로젝트** > [**Visual Basic** 또는 **Visual C#** ] > **WCF**를 선택 하 여 이러한 서비스 템플릿을 찾을 수 있습니다. WCF Workflow Service 응용 프로그램 및 WCF 서비스 응용 프로그램을 포함 하 여이 위치에 있는 다른 WCF 템플릿의 경우, [웹 응용 프로그램에 대해 한 번 클릭 게시](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))를 사용 하 여 게시할 수 있습니다.

다음과 같은 대상 위치에 서비스를 게시할 수 있습니다.

- 로컬 IIS

- 파일 시스템

- FTP 사이트

## <a name="using-wcf-service-publishing"></a>WCF 서비스 게시 사용

서비스 구현을 배포하려면 다음 단계를 수행합니다.

1. 높은 권한으로 Visual Studio를 엽니다 (실행 파일을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 하 여 엽니다).  IIS 7.0 이상 버전을 사용 하는 경우 제어판의 "Windows 기능 사용/사용 안 함"을 사용 하 여 "IIS 메타 베이스 및 IIS6 구성 호환성" 구성 요소를 설치 했는지 확인 합니다.

2. 서비스 프로젝트를 열고 기본 메뉴에서 **빌드**  >  **\<Project 이름 > 게시** 를 선택 하거나 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **게시**를 클릭 합니다.

3. **게시** 창이 나타납니다. **...를 클릭**합니다. 단추를 클릭하여 서비스를 배포할 대상 위치를 지정합니다. 로컬 IIS, 파일 시스템 또는 FTP 사이트에 응용 프로그램을 배포 하도록 선택할 수 있습니다. 로컬 IIS에 응용 프로그램을 배포 하는 경우 오른쪽 위 모서리에서 **새 웹 응용 프로그램 만들기** 아이콘을 클릭 하 여 웹 사이트를 선택 하 고 그 아래에서 웹 응용 프로그램을 만들 수 있습니다.

4. 주 창에서 **게시** 를 클릭 한 후 Visual Studio는 지정 된 대상 위치에 응용 프로그램을 배포 하 고 web.config, .svc 및 어셈블리 파일을 대상 디렉터리에 복사 합니다. 이어야 합니다. .Svc의 이름은 "ProjectName. ServiceName"이 됩니다. 서비스를 성공적으로 게시 한 후 Visual Studio 출력 창에서 hotlink를 찾을 수 있습니다 .이 창에는 "`http://localhost/WebApplicationFolderName...` 연결"과 유사 하 게 표시 됩니다. Ctrl 키를 누르고 링크를 클릭하여 Visual Studio 내에서 브라우저 페이지를 열고 서비스 디렉터리 구조를 볼 수 있습니다.

     사이트를 찾을 수 없으면 IIS에서 디렉터리 브라우저를 사용하도록 설정되지 않았을 수 있습니다. "시도해 볼 수 있는 항목" 섹션의 팁을 따라 사용 하도록 설정 하세요. 또는 `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc`를 직접 입력 하 여 서비스 페이지를 볼 수 있습니다.

**게시** 를 사용 하 여 프로젝트에 정의 된 모든 서비스에 대 한 어셈블리, 구성 및 .svc 파일을 대상 위치에 복사할지 여부를 지정 하 고 대상에서 기존 파일을 덮어쓸 수 있습니다.

애플리케이션을 로컬 IIS에 배포하도록 선택하면 IIS 설치와 관련된 오류가 발생할 수 있습니다. IIS가 제대로 설치되었는지 확인하세요. 브라우저의 주소 표시줄에 `http://localhost`를 입력 하 고 IIS 기본 페이지가 표시 되는지 여부를 확인할 수 있습니다. 일부 경우에는 IIS에서 ASP.NET 또는 WCF를 잘못 등록 하는 경우에도 문제가 발생할 수 있습니다. Visual Studio에 대 한 개발자 명령 프롬프트를 열고 명령 `aspnet_regiis.exe -ir`를 실행 하 여 ASP.NET 등록 문제를 해결 하거나 명령 `ServiceModelReg.exe –ia`를 실행 하 여 WCF 등록 문제를 해결할 수 있습니다.

## <a name="files-generated-for-publishing"></a>게시를 위해 생성되는 파일
 WCF 서비스 라이브러리를 웹 호스트로 만들려면 도구에서 어셈블리 파일, web.config 파일, .svc 파일 등의 파일을 생성 합니다. 이러한 파일이 모두 대상 위치에 복사된 후에 서비스가 게시됩니다.

### <a name="assembly-files"></a>어셈블리 파일
 이 도구를 사용 하 여 WCF 서비스를 게시 하면 서비스가 먼저 자동으로 빌드되고 빌드 후에 서비스 프로젝트에 어셈블리 파일이 생성 됩니다.

### <a name="svc-file"></a>.SVC 파일
 게시 작업은 버전 유효성을 확인 하기 위해 각 WCF 서비스에 대해 파일이 있는지 여부에 관계 없이 * .svc 파일을 생성 합니다. 두 가지 svc 파일, 즉 WCF 서비스 라이브러리 및 배포 서비스 라이브러리와 순차 및 상태 시스템 워크플로 서비스 라이브러리에 대 한 두 가지 다른 종류의 svc 파일이 있습니다. 생성 된 \* .svc 파일은 대상 위치의 루트 폴더에 복사 됩니다.

### <a name="webconfig-file"></a>Web.config 파일
 서비스 프로젝트를 특정 대상 위치에 게시할 때마다 Web.config 파일이 만들어집니다.

 생성 된 web.config 파일에는 웹 호스팅에 유용한 웹 섹션과 다음과 같이 변경 된 WCF 서비스 라이브러리의 App.config 내용이 포함 되어 있습니다.

- 기본 주소는 제외됩니다.

- `<diagnostics>` 요소의 설정은 대상 플랫폼의 추적 설정을 유지하기 위해 제외됩니다.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>HTTP가 아닌 바인딩을 사용하여 WCF 서비스를 IIS에 게시
 IIS 7.0 이상을 사용 하는 경우 HTTP가 아닌 바인딩을 사용 하 여 WCF 서비스를 IIS에 게시할 수 있습니다. 몇 가지 사전 구성 작업을 수행해야 합니다. 자세한 내용은 [Windows Process Activation Service에서 호스팅](./feature-details/hosting-in-windows-process-activation-service.md)항목을 참조 하세요.

## <a name="security"></a>보안
 IIS는 관리자 계정으로 실행해야 하므로 로컬 IIS에 게시하려면 관리자 권한이 필요합니다. 관리자 권한이 없는 사용자가 WCF 서비스 게시를 열면 IIS를 대상 위치로 사용할 수 없습니다. 파일 시스템 또는 FTP 사이트에 대 한 게시는 관리자 권한 없이 작동 합니다.

## <a name="see-also"></a>참조

- [WCF Visual Studio 템플릿](wcf-vs-templates.md)
- [WCF 서비스 호스트(WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF 테스트 클라이언트(WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
