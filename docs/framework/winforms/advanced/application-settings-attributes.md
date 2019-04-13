---
title: 애플리케이션 설정 특성
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: f945d8e6918c271eeb5fdf3cf9c357b1c2bbca66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079645"
---
# <a name="application-settings-attributes"></a>애플리케이션 설정 특성
응용 프로그램 설정 아키텍처는 응용 프로그램 설정 래퍼 클래스 또는 해당 개별 속성에 적용할 수 있는 여러 특성을 제공 합니다. 이러한 특성은 맞게 사용자 지정 래퍼 명시 된 요구 사항에 기능을 조절 하기 위해 종종 특별히 설정 공급자를 응용 프로그램 설정 인프라에서 런타임에 검사 합니다.  
  
 다음 표에서 응용 프로그램 설정 래퍼 클래스,이 클래스의 개별 속성 또는 둘 다에 적용할 수 있는 특성을 나열 합니다. 정의상, 단일 범위 특성만 —**UserScopedSettingAttribute** 또는 **ApplicationScopedSettingAttribute**-각 설정 속성에 적용 되어야 합니다.  
  
> [!NOTE]
>  파생 된 사용자 지정 설정 공급자를 <xref:System.Configuration.SettingsProvider> 클래스를 다음 세 가지 특성을 인식 하도록 하기만 하면 됩니다. **ApplicationScopedSettingAttribute**하십시오 **UserScopedSettingAttribute**, 및 **DefaultSettingValueAttribute**합니다.  
  
|특성|대상|설명|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Both|지 속성을 위해 사용 하는 설정 공급자의 약식 이름을 지정 합니다.<br /><br /> 이 특성을 제공 하지 않으면 기본 공급자 인 <xref:System.Configuration.LocalFileSettingsProvider>, 것으로 간주 됩니다.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Both|사용자 범위 응용 프로그램 설정으로 속성을 정의합니다.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Both|응용 프로그램 범위 응용 프로그램 설정 대로 속성을 정의합니다.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|속성|이 속성에 대 한 하드 코드 된 기본값에 공급자가 deserialize 할 수 있는 문자열을 지정 합니다.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> 이 특성이 필요 하지 않으며이 특성이 없는 경우 값을 이미 유지 제공 된 모든 값을 재정의 합니다.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|속성|런타임 및 디자인 타임 도구에서 주로 사용 하는 개별 설정에 대 한 설명이 포함 된 테스트를 제공 합니다.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|클래스|설정 그룹에 명시적 이름을 제공합니다. 이 특성을 사용할 수 없는 경우 <xref:System.Configuration.ApplicationSettingsBase> 래퍼 클래스 이름을 사용 합니다.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|클래스|런타임 및 디자인 타임 도구에서 주로 사용 하는 설정 그룹에 대 한 설명이 포함 된 테스트를 제공 합니다.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Both|설정 그룹 또는 속성에 제공 해야 하는 0 개 이상의 관리 서비스를 지정 합니다. 사용 가능한 서비스에서 설명 되는 <xref:System.Configuration.SettingsManageability> 열거형입니다.|  
|<xref:System.Configuration.SpecialSettingAttribute>|속성|설정을 설정 공급자가 특수 한 처리를 제안 하는 연결 문자열과 같은 특수 한 미리 정의 된 범주에 속함을 나타냅니다. 이 특성에 대 한 미리 정의 된 범주에 의해 정의 됩니다는 <xref:System.Configuration.SpecialSetting> 열거형입니다.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Both|설정 그룹이 나 속성에 대 한 기본 serialization 메커니즘을 지정 합니다. 사용 가능한 serialization 메커니즘에 의해 정의 됩니다는 <xref:System.Configuration.SettingsSerializeAs> 열거형입니다.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|속성|설정 공급자가 표시 된 속성에 대 한 모든 응용 프로그램 업그레이드 기능 하지 않도록 지정 합니다.|  
  
 *클래스* 특성을 응용 프로그램 설정 래퍼 클래스에만 적용 되어야 함을 나타냅니다. *속성* 특성 설정 속성에만 적용할된 수 있음을 나타냅니다. *둘 다* 각 수준에서 특성을 적용할 수 있음을 나타냅니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [애플리케이션 설정 아키텍처](application-settings-architecture.md)
- [방법: 애플리케이션 설정 만들기](how-to-create-application-settings.md)
