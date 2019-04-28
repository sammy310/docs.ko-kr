---
title: 응용 프로그램 구성
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 94bf5f4bbee8bb8bb462c4bf91be75d1627ec567
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784997"
---
# <a name="configuring-your-application"></a>응용 프로그램 구성
Windows Communication Foundation (WCF).NET 구성 시스템을 사용 하 고 컴퓨터 및 응용 프로그램 범위에서 서비스를 구성할 수 있습니다.  
  
 WCF에서 정의한 구성 설정은 `<system.serviceModel>` 섹션 그룹입니다. WCF 서비스를 구성 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.  
  
- [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)  
  
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 응용 프로그램에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다. .NET 구성 파일에서 응용 프로그램 설정에 대 한 자세한 내용은 참조 하세요. [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)합니다.  
  
## <a name="using-the-configuration-editor"></a>Configuration Editor 사용  
 WCF [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 관리자와 개발자가 그래픽 사용자 인터페이스를 사용 하 여 WCF 서비스에 대 한 구성 설정을 만들고 수정할 수 있습니다. 이 도구를 사용 하 여 XML 구성 파일을 직접 편집 하지 않고도 WCF 바인딩, 동작, 서비스 및 진단에 대 한 설정을 관리할 수 있습니다.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Visual Studio에서 구성 파일 편집  
 Visual Studio에서 WCF 서비스 프로젝트의 구성 파일을 편집 하려면 마우스 오른쪽 단추로 클릭에 **솔루션 탐색기** 선택 합니다 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다. 그러면 합니다 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.  
  
> [!NOTE]
>  마우스 오른쪽 단추로 클릭 하 여 Visual Studio에서 WCF 웹 서비스 프로젝트의 구성 파일을 편집 하는 경우 **솔루션 탐색기**, 있음을 합니다 **WCF 구성 편집** 상황에 맞는 메뉴 항목이 누락 되었습니다. 문제를 해결 하려면이 문제를 클릭 합니다 **도구** 메뉴에서 선택한 **WCF 서비스 구성 편집기**합니다. 그 후 구성 파일을 마우스 오른쪽 단추로 클릭 하 사용할 수는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.  
  
## <a name="see-also"></a>참고자료

- [Configuration Editor 도구(SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
