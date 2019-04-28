---
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: a74716bcdf3c85c08d0ff3bf66407dce30ee91cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705443"
---
# <a name="application-settings-schema"></a>응용 프로그램 설정 스키마

응용 프로그램 설정에 Windows Forms 또는 ASP.NET 응용 프로그램을 저장 하 고 응용 프로그램 범위 설정과 사용자 범위 설정을 검색할 수 있습니다. 이 컨텍스트에서 *설정은* 조각을 나타내는 응용 프로그램 또는 현재 사용자에 게 관련 될 수 있는 정보는-사용자에 게 데이터베이스 연결 문자열에서 모든 항목의 기본 창 크기 기본 설정 합니다.

기본적으로 Windows Forms 응용 프로그램에서 응용 프로그램 설정을 사용 하는 <xref:System.Configuration.LocalFileSettingsProvider> 설정을 XML 구성 파일에 저장 하는.NET 구성 시스템을 사용 하는 클래스입니다. 응용 프로그램 설정에 의해 사용 되는 파일에 대 한 자세한 내용은 참조 하세요. [응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)합니다.

응용 프로그램 설정을 사용 하 여 구성 파일의 일부로 다음과 같은 요소를 정의 합니다.

| 요소                    | 설명                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | 모든 포함  **\<설정 >** 응용 프로그램에 특정 태그입니다.                         |
| **\<userSettings>**        | 모든 포함  **\<설정 >** 현재 사용자에 게 특정 태그입니다.                        |
| **\<setting>**             | 설정을 정의합니다. 자식  **\<applicationSettings >** 하거나  **\<userSettings >** 합니다. |
| **\<value>**               | 설정 값을 정의합니다. 자식의  **\<설정 >** 합니다.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > 요소

이 요소는 모두 포함  **\<설정 >** 클라이언트 컴퓨터에서 응용 프로그램 인스턴스에 관련 된 태그입니다. 특성 없음을 정의합니다.

## <a name="usersettings-element"></a>\<userSettings > 요소

이 요소는 모두 포함  **\<설정 >** 응용 프로그램을 현재 사용 중인 사용자에 관련 된 태그입니다. 특성 없음을 정의합니다.

## <a name="setting-element"></a>\<설정 > 요소

이 요소에는 설정을 정의 합니다. 다음 특성을 가집니다.

| 특성        | 설명 |
| ---------------- | ----------- |
| **name**         | 필수 요소. 설정의 고유 ID입니다. Visual Studio를 통해 만든 설정을 이름으로 저장 됩니다 `ProjectName.Properties.Settings`합니다. |
| **serializedAs** | 필수 요소. 텍스트 값을 직렬화 하는 데 사용할 형식입니다. 올바른 값은 다음과 같습니다.<br><br>- `string`. 사용 하 여 문자열 값이 serialize 되는 <xref:System.ComponentModel.TypeConverter>합니다.<br>- `xml`. 값은 XML serialization을 사용 하 여 serialize 됩니다.<br>- `binary`. 값은 이진 serialization을 사용 하 여 텍스트 인코딩된 이진으로 serialize 됩니다.<br />- `custom`. 설정 공급자가이 설정에 대 한 기본 지식이 직렬화 및 역직렬화 합니다. |

## <a name="value-element"></a>\<값 > 요소

이 요소는 설정의 값을 포함합니다.

## <a name="example"></a>예제

다음 예제에서는 두 개의 응용 프로그램 범위 설정 및 두 사용자 범위 설정을 정의 하는 응용 프로그램 설정 파일을 보여 줍니다.

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

## <a name="see-also"></a>참고자료

- [응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md)
- [응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)
