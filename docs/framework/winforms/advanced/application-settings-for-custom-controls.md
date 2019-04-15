---
title: 사용자 지정 컨트롤에 대한 애플리케이션 설정
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: 69a5caef8bab45503b9f34422de8c2ba2e7f01ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317300"
---
# <a name="application-settings-for-custom-controls"></a>사용자 지정 컨트롤에 대한 애플리케이션 설정
사용자 지정 컨트롤에서 타사 응용 프로그램에서 컨트롤을 호스팅할 때 응용 프로그램 설정을 유지할 수 있도록 특정 작업을 완료 해야 합니다.  
  
 대부분의 응용 프로그램 설정 기능에 대 한 설명서는 독립 실행형 응용 프로그램을 만든다고 가정 아래 작성 됩니다. 그러나 응용 프로그램에서 다른 개발자가 호스트 하는 컨트롤을 만드는 경우 해당 설정을 유지 하 여 컨트롤에 대 한 몇 가지 추가 단계를 수행 하려면 적절 합니다.  
  
## <a name="application-settings-and-custom-controls"></a>응용 프로그램 설정 및 사용자 지정 컨트롤  
 제대로 해당 설정을 유지 하기 위해 컨트롤에 대 한 설정 래퍼 클래스에서 파생 된 고유한 전용된 응용 프로그램을 만들어 프로세스를 캡슐화 해야 것 <xref:System.Configuration.ApplicationSettingsBase>입니다. 또한 기본 컨트롤 클래스를 구현 해야 합니다는 <xref:System.Configuration.IPersistComponentSettings>합니다. 인터페이스를 두 가지 방법 뿐만 아니라 여러 속성이 포함 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 고 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>입니다. 사용 하 여 폼 컨트롤을 추가 하는 경우는 **Windows Forms 디자이너** Visual Studio에서 Windows Forms 호출 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 컨트롤이 초기화 될 때 자동으로; 호출 해야 합니다 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 보십시오를 `Dispose` 컨트롤의 메서드입니다.  
  
 또한 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동 하려면 사용자 지정 컨트롤에 대 한 응용 프로그램 설정에 대 한 순서에는 다음을 구현 해야 합니다.  
  
1. 사용 하는 생성자를 사용 하 여 사용자 지정 응용 프로그램 설정 클래스를 <xref:System.ComponentModel.IComponent> 단일 매개 변수로 합니다. 저장 하 고 모든 응용 프로그램 설정을 로드할이 클래스를 사용 합니다. 이 클래스의 새 인스턴스를 만든 경우 생성자를 사용 하 여 사용자 지정 컨트롤을 전달 합니다.  
  
2. 컨트롤 생성 및와 같은 폼의 폼에 배치 된 후이 사용자 지정 설정 클래스를 만드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.  
  
 사용자 지정 설정 클래스를 만드는 방법에 대 한 지침을 참조 하세요. [방법: 응용 프로그램 설정 만들기](how-to-create-application-settings.md)합니다.  
  
## <a name="settings-keys-and-shared-settings"></a>설정 키 및 공유 설정  
 일부 컨트롤은 동일한 폼 내에서 여러 번 사용할 수 있습니다. 대부분의 경우 이러한 컨트롤을 개별 설정을 유지 해야 합니다. 사용 하 여 합니다 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 속성을 <xref:System.Configuration.IPersistComponentSettings>, 폼에서 컨트롤의 여러 버전을 명확 하 게 작동 하는 고유 문자열을 제공할 수 있습니다.  
  
 구현 하는 가장 간단한 방법은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 사용 하는 것을 <xref:System.Windows.Forms.Control.Name%2A> 에 대 한 컨트롤의 속성을 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>입니다. 값을 전달으로 로드 하거나 컨트롤의 설정을 저장 하는 경우 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 에 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 의 속성을 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다. XML로 사용자 설정을 유지할 때 고유 키를 사용 하는 응용 프로그램 설정 합니다. 다음 코드 예제에서는 어떻게를 `<userSettings>` 이라는 사용자 지정 컨트롤의 인스턴스에 대 한 섹션 보일 수 있습니다 `CustomControl1` 에 대 한 설정을 저장 하는 해당 `Text` 속성입니다.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 에 대 한 값을 제공 하지 않는 컨트롤의 모든 인스턴스 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 동일한 설정을 공유 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [애플리케이션 설정 아키텍처](application-settings-architecture.md)
