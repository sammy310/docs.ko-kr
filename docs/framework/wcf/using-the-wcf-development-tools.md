---
title: WCF 개발 도구 사용
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 1ffa3be4a6b8976ab978ea995e8b2c1faaacf0ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144640"
---
# <a name="using-the-wcf-development-tools"></a>WCF 개발 도구 사용
이 섹션에서는 WCFservice 개발을 활용할 수 있는 Visual Studio 개발 도구를 설명 합니다.  
  
 고유한 서비스를 신속 하 게 빌드를 기반으로 Visual Studio 템플릿을 사용 다음 WCF 서비스 자동 호스트 및 WCF 테스트 클라이언트를 사용 하 여 디버깅 하 고 서비스를 테스트할 수 있습니다. 이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.  
  
## <a name="the-wcf-developer-tools"></a>WCF 개발자 도구  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 신속 하 게 WCF 서비스와 관련 응용 프로그램을 빌드하려면 Visual Studio에서 미리 정의 된 Visual Studio 프로젝트 및 항목 템플릿을 사용할 수 있습니다.  
  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 WCF 서비스 자동 호스트 (WcfSvcHost.exe)를 사용 하면 Visual Studio 디버거 (F5) 자동으로 호스팅하고 테스트할 구현한 서비스를 시작할 수 있습니다. 다음 찾기 및 잠재적인 오류를 해결 하려면 WCF 테스트 클라이언트 (wcfTestClient.exe) 또는 사용자 고유의 클라이언트를 사용 하는 서비스를 테스트할 수 있습니다.  
  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 WCF 테스트 클라이언트 (WcfTestClient.exe)는 임의 형식의 매개 변수 입력, 입력 하 고 서비스에서 되돌려 보내는 응답 서비스 보기를 제출할 수 있는 GUI 도구입니다. 서비스를 매끄럽게 테스트할 WCF 서비스 자동 호스트를 함께 사용 하면 환경을 제공 합니다.  
  
 [XML에서 데이터 형식 클래스 생성](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다. 데이터에 정의된 클래스는 코드 형식으로 변환됩니다.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>관리자 권한 없이 도구 사용  
 WCF 서비스를 개발 하려면 관리자 권한이 없는 사용자를 사용 하려면 네임 스페이스에 대 한 ACL (액세스 제어 목록) 만들어집니다 "http://+:8731/Design_Time_Addresses" Visual Studio 설치 중입니다. ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다. 관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다. 또한 사용자가 관리자 권한을 부여 하지 않고 WCF 서비스 자동 호스트 (wcfSvcHost.exe)를 사용할 수 있습니다.  
  
 [!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 Netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다. 다음은 Netsh.exe를 사용하는 예입니다.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe에 대 한 자세한 내용은 참조 하세요. [Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법을](https://go.microsoft.com/fwlink/?LinkId=97877)합니다.  
  
## <a name="see-also"></a>참고자료

- [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)
- [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
