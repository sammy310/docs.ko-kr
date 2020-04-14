---
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242831"
---
# <a name="application-settings-schema"></a>응용 프로그램 설정 스키마

응용 프로그램 설정을 사용하면 Windows Forms 또는 ASP.NET 응용 프로그램이 응용 프로그램 범위 및 사용자 범위 설정을 저장하고 검색할 수 있습니다. 이 컨텍스트에서 *설정은* 응용 프로그램에 특정하거나 현재 사용자에 특정할 수 있는 모든 정보(데이터베이스 연결 문자열에서 사용자의 기본 기본 창 크기에 이르기까지)입니다.

기본적으로 Windows Forms 응용 프로그램의 응용 <xref:System.Configuration.LocalFileSettingsProvider> 프로그램 설정은 .NET 구성 시스템을 사용하여 XML 구성 파일에 설정을 저장하는 클래스를 사용합니다. 응용 프로그램 설정에서 사용되는 파일에 대한 자세한 내용은 [응용 프로그램 설정 아키텍처](../../winforms/advanced/application-settings-architecture.md)를 참조하십시오.

응용 프로그램 설정은 다음 요소를 사용하는 구성 파일의 일부로 정의합니다.

| 요소                    | Description                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<응용 프로그램설정>** | 응용 프로그램에 ** \<특정한** 모든 설정>태그를 포함합니다.                         |
| **\<사용자 설정>**        | 현재 ** \<** 사용자와 관련된 모든 설정>태그를 포함합니다.                        |
| **\<>설정**             | 설정을 정의합니다. 응용 프로그램의 하위>또는 ** \<** ** \<사용자설정>**. |
| **\<값>**               | 설정 값을 정의합니다. 설정의 자식>. ** \< **                                   |

## <a name="applicationsettings-element"></a>\<응용 프로그램설정> 요소

이 요소에는 ** \<** 클라이언트 컴퓨터에서 응용 프로그램의 인스턴스와 관련된 모든 설정>태그가 포함됩니다. 특성 없음을 정의합니다.

## <a name="usersettings-element"></a>\<사용자 설정> 요소

이 요소에는 ** \<** 현재 응용 프로그램을 사용하는 사용자와 관련된 모든 설정>태그가 포함됩니다. 특성 없음을 정의합니다.

## <a name="setting-element"></a>\<> 요소 설정

이 요소는 설정을 정의합니다. 다음과 같은 특성이 있습니다.

| attribute        | Description |
| ---------------- | ----------- |
| **(이름)**         | 필수 사항입니다. 설정의 고유 ID입니다. Visual Studio를 통해 만든 설정은 이름으로 `ProjectName.Properties.Settings`저장됩니다. |
| **직렬화** | 필수 사항입니다. 값을 텍스트로 직렬화하는 데 사용할 형식입니다. 유효한 값은 다음과 같습니다.<br><br>- `string`. 값은 <xref:System.ComponentModel.TypeConverter>을 사용하여 문자열로 직렬화됩니다.<br>- `xml`. 값은 XML 직렬화를 사용하여 직렬화됩니다.<br>- `binary`. 이중 직렬화를 사용하여 텍스트 인코딩된 바이너리로 직렬화됩니다.<br />- `custom`. 설정 공급자는 이 설정에 대한 고유한 지식을 가지고 있으며 직렬화하고 직렬화합니다. |

## <a name="value-element"></a>\<값> 요소

이 요소에는 설정 값이 포함됩니다.

## <a name="example"></a>예제

다음 예제에서는 두 개의 응용 프로그램 범위 설정과 두 개의 사용자 범위 설정을 정의하는 응용 프로그램 설정 파일을 보여 주십니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [애플리케이션 설정 개요](../../winforms/advanced/application-settings-overview.md)
- [애플리케이션 설정 아키텍처](../../winforms/advanced/application-settings-architecture.md)
