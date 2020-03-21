---
title: WCF 개발 도구 사용
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183076"
---
# <a name="using-the-wcf-development-tools"></a>WCF 개발 도구 사용
이 섹션에서는 WCFservice 개발에 도움이 되는 Visual Studio 개발 도구에 대해 설명합니다.  
  
 Visual Studio 템플릿을 기반으로 사용하여 자체 서비스를 신속하게 빌드한 다음 WCF 서비스 자동 호스트 및 WCF 테스트 클라이언트를 사용하여 서비스를 디버깅하고 테스트할 수 있습니다. 이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.  

 > [!NOTE]
 > Visual Studio 2017부터 WCF 개발 도구는 기본적으로 설치되지 않습니다. 이러한 기능을 사용하려면 Visual Studio 설치 관리자에서 Windows 통신 기반 구성 요소가 선택되었는지 확인해야 합니다.
  
## <a name="the-wcf-developer-tools"></a>WCF 개발자 도구  
 [WCF Visual Studio 템플릿](wcf-vs-templates.md)  
  
 Visual Studio에서 미리 정의된 Visual Studio 프로젝트 및 항목 템플릿을 사용하여 WCF 서비스 및 주변 응용 프로그램을 신속하게 빌드할 수 있습니다.  
  
 [WCF 서비스 호스트(WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 WCF 서비스 자동 호스트(WcfSvcHost.exe)를 사용하면 Visual Studio 디버거(F5)를 시작하여 구현한 서비스를 자동으로 호스팅하고 테스트할 수 있습니다. 그런 다음 WCF 테스트 클라이언트(wcfTestClient.exe) 또는 사용자 고유의 클라이언트를 사용하여 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.  
  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 WCF 테스트 클라이언트(WcfTestClient.exe)는 임의의 형식의 매개 변수를 입력하고, 해당 입력을 서비스에 제출하고, 서비스가 다시 보내는 응답을 볼 수 있는 GUI 도구입니다. WCF 서비스 자동 호스트와 결합하면 원활한 서비스 테스트 환경을 제공합니다.  
  
 [XML에서 데이터 형식 클래스 생성](generating-data-type-classes-from-xml.md)  
  
 클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다. 데이터에 정의된 클래스는 코드 형식으로 변환됩니다.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>관리자 권한 없이 도구 사용  
 관리자 권한이 없는 사용자가 WCF 서비스를 개발할 수 있도록 Visual Studio를 설치하는 동안http://+:8731/Design_Time_Addresses네임스페이스 "에 대한 ACL(액세스 제어 목록)이 만들어집니다. ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다. 관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다. 또한 사용자가 관리자 권한을 부여하지 않고 WCF 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.  
  
 높은 관리자 계정 아래 Windows Vista의 Netsh.exe 도구를 사용하여 액세스를 수정할 수 있습니다. 다음은 Netsh.exe를 사용하는 예입니다.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe에 대한 자세한 내용은 [Netsh.exe 도구 및 명령줄 스위치를 사용하는 방법을](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [WCF Visual Studio 템플릿](wcf-vs-templates.md)
- [WCF 서비스 호스트(WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF 테스트 클라이언트(WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
