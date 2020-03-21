---
title: 애플리케이션 설정 아키텍처
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 078b5f3fc1cd4273af282580f41e68ca9bd8ff51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182621"
---
# <a name="application-settings-architecture"></a>애플리케이션 설정 아키텍처
이 항목에서는 애플리케이션 설정 아키텍처가 작동하는 방식과 그룹화된 설정 및 설정 키와 같은 고급 아키텍처 기능에 대해 설명합니다.

 애플리케이션 설정 아키텍처에서는 애플리케이션 범위 또는 사용자 범위로 강력한 형식의 설정을 정의하고 애플리케이션 세션 간에 설정을 유지할 수 있습니다. 또한 이 아키텍처는 로컬 파일 시스템에 설정을 저장하고 해당 시스템에서 설정을 로드하기 위한 기본 지속성 엔진을 제공하며, 사용자 지정 지속성 엔진을 제공하기 위한 인터페이스도 정의합니다.

 애플리케이션에서 사용자 지정 구성 요소를 호스팅할 때 구성 요소 자체의 설정을 유지할 수 있도록 하는 인터페이스가 제공됩니다. 설정 키를 사용하면 구성 요소에서 구성 요소의 여러 인스턴스에 대한 설정을 개별적으로 유지할 수 있습니다.

## <a name="defining-settings"></a>설정 정의
 응용 프로그램 설정 아키텍처는 ASP.NET 및 Windows Forms 모두에서 사용되며 두 환경에서 공유되는 여러 기본 클래스가 포함되어 있습니다. 가장 중요한 <xref:System.Configuration.SettingsBase>것은 컬렉션을 통해 설정에 대한 액세스를 제공하고 설정을 로드하고 저장하기 위한 하위 수준 메서드를 제공하는 것입니다. 각 환경은 해당 환경에 대한 <xref:System.Configuration.SettingsBase> 추가 설정을 제공하기 위해 파생된 자체 클래스를 구현합니다. Windows Forms 기반 응용 프로그램에서 모든 응용 프로그램 설정은 <xref:System.Configuration.ApplicationSettingsBase> 클래스에서 파생된 클래스에 정의되어야 하며 기본 클래스에 다음 기능을 추가합니다.

- 상위 수준 로드 및 저장 작업

- 사용자 범위 설정 지원

- 사용자 설정을 미리 정의된 기본값으로 되돌리기

- 이전 애플리케이션 버전에서 설정 업그레이드

- 변경하거나 저장하기 전에 설정에 대한 유효성 검사

 네임스페이스 내에 <xref:System.Configuration> 정의된 여러 특성을 사용하여 설정을 설명할 수 있습니다. 이러한 설명은 [응용 프로그램 설정 특성에 설명되어 있습니다.](application-settings-attributes.md) 설정을 정의할 때 는 설정이 <xref:System.Configuration.ApplicationScopedSettingAttribute> 전체 <xref:System.Configuration.UserScopedSettingAttribute>응용 프로그램에 적용되는지 아니면 현재 사용자에게만 적용되는지 여부를 설명하는 에 적용해야 합니다.

 다음 코드 예제에서는 단일 설정인 `BackgroundColor`를 사용하여 사용자 지정 설정 클래스를 정의합니다.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>설정 지속성
 클래스 <xref:System.Configuration.ApplicationSettingsBase> 자체가 유지하거나 로드 설정을 하지 않습니다. 이 작업은 에서 파생되는 클래스인 설정 <xref:System.Configuration.SettingsProvider>공급자에 해당합니다. 파생 된 클래스가 <xref:System.Configuration.ApplicationSettingsBase> <xref:System.Configuration.SettingsProviderAttribute>을 통해 설정 공급자를 지정하지 않으면 <xref:System.Configuration.LocalFileSettingsProvider>기본 공급자가 사용됩니다.

 .NET Framework로 원래 릴리스된 구성 시스템은 로컬 컴퓨터의 machine.config 파일 또는 응용 프로그램과 `app.`함께 배포하는 exe.config 파일 내에서 정적 응용 프로그램 구성 데이터를 제공합니다. 클래스는 <xref:System.Configuration.LocalFileSettingsProvider> 다음과 같은 방법으로 이 기본 지원을 확장합니다.

- 애플리케이션 범위 설정은 machine.config 또는 `app.`exe.config 파일에 저장될 수 있습니다. Machine.config는 항상 읽기 전용이지만, `app`.exe.config는 보안 고려 사항에 따라 대부분의 애플리케이션에서 읽기 전용으로 제한됩니다.

- 사용자 범위 설정은 `app`.exe.config 파일에 저장될 수 있으며, 이 경우 정적 기본값으로 처리됩니다.

- 기본값이 아닌 사용자 범위 설정은 새 파일인 *user*.config에 저장되며, 여기서 *user*는 현재 애플리케이션을 실행 중인 사람의 사용자 이름입니다. <xref:System.Configuration.DefaultSettingValueAttribute>을 사용 하 이 있는 사용자 범위 설정에 대 한 기본값을 지정할 수 있습니다. 사용자 범위 설정이 애플리케이션 실행 중에 자주 변경되기 때문에 `user`.config는 항상 읽기/쓰기입니다.

 세 가지 구성 파일은 모두 설정을 XML 형식으로 저장합니다. 애플리케이션 범위 설정의 최상위 XML 요소는 `<appSettings>`이며, 사용자 범위 설정에는 `<userSettings>`가 사용됩니다. 애플리케이션 범위 설정과 사용자 범위 설정의 기본값을 모두 포함하는 `app`.exe.config 파일은 다음과 같습니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
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

 구성 파일의 애플리케이션 설정 섹션에 있는 요소의 정의는 [애플리케이션 설정 스키마](../../configure-apps/file-schema/application-settings-schema.md)를 참조하세요.

### <a name="settings-bindings"></a>설정 바인딩
 애플리케이션 설정은 Windows Forms 데이터 바인딩 아키텍처를 사용하여 설정 개체와 구성 요소 간의 양방향 통신으로 설정 업데이트를 제공합니다. Visual Studio에서 애플리케이션 설정을 만들어 구성 요소 속성에 할당하면 이러한 바인딩이 자동으로 생성됩니다.

 <xref:System.Windows.Forms.IBindableComponent> 응용 프로그램 설정을 인터페이스를 지원하는 구성 요소에만 바인딩할 수 있습니다. 또한 구성 요소는 특정 바인딩된 속성에 대한 변경 이벤트를 구현하거나 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 통해 속성이 변경되었음을 응용 프로그램 설정에 알려야 합니다. 구성 요소가 구현되지 <xref:System.Windows.Forms.IBindableComponent> 않고 Visual Studio를 통해 바인딩하는 경우 바인딩된 속성이 처음 설정되지만 업데이트되지는 않습니다. 구성 요소가 <xref:System.Windows.Forms.IBindableComponent> 구현하지만 속성 변경 알림을 지원하지 않는 경우 속성이 변경될 때 설정 파일에서 바인딩이 업데이트되지 않습니다.

 와 같은 <xref:System.Windows.Forms.ToolStripItem>일부 Windows Forms 구성 요소는 설정 바인딩을 지원하지 않습니다.

### <a name="settings-serialization"></a>설정 직렬화(Serialization)
 디스크에 설정을 저장해야 하는 경우 <xref:System.Configuration.LocalFileSettingsProvider> 다음 작업을 수행합니다.

1. 리플렉션을 사용하여 파생 클래스에 정의된 모든 속성을 검사하여 <xref:System.Configuration.ApplicationSettingsBase> <xref:System.Configuration.ApplicationScopedSettingAttribute> 또는 <xref:System.Configuration.UserScopedSettingAttribute>에 적용된 속성을 찾습니다.

2. 속성을 디스크에 직렬화합니다(serialize). 먼저 <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> 또는 <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> 형식의 연결된 <xref:System.ComponentModel.TypeConverter>에 호출하려고 시도합니다. 호출하지 못하면 XML serialization을 대신 사용합니다.

3. 설정의 특성에 따라 어떤 파일에 어떤 설정을 사용할지 결정합니다.

 사용자 고유의 설정 클래스를 구현하는 <xref:System.Configuration.SettingsSerializeAsAttribute> 경우 <xref:System.Configuration.SettingsSerializeAs> 열거형 을 사용하여 이진 또는 사용자 지정 직렬화에 대한 설정을 표시하는 데 사용할 수 있습니다. 코드에서 사용자 고유의 설정 클래스를 만드는 방법에 대한 자세한 내용은 [방법: 애플리케이션 설정 만들기](how-to-create-application-settings.md)를 참조하세요.

### <a name="settings-file-locations"></a>설정 파일 위치
 `app`.exe.config 및 *user*.config 파일의 위치는 애플리케이션을 설치하는 방법에 따라 다릅니다. 로컬 컴퓨터에 복사된 Windows Forms 기반 응용 `app`프로그램의 경우 .exe.config는 응용 프로그램의 기본 실행 파일의 기본 디렉터리와 동일한 디렉터리에 상주하며 *user*.config는 <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> 속성에서 지정한 위치에 상주합니다. ClickOnce에 의해 설치된 응용 프로그램의 경우, 이 파일의 두 가지 는 %InstallRoot%\문서\\및 설정*사용자 이름*\로컬 설정 아래 ClickOnce 데이터 디렉토리에 상주합니다.

 사용자가 로밍 프로필을 사용하도록 설정한 경우 이러한 파일의 저장소 위치는 약간 다르므로 사용자가 도메인 내의 다른 컴퓨터를 사용할 때 다른 Windows 및 응용 프로그램 설정을 정의할 수 있습니다. 이 경우 ClickOnce 응용 프로그램과 비 ClickOnce 응용 프로그램 `app`모두 %InstallRoot%\문서 및 설정\\*사용자 이름*\응용 프로그램 데이터 아래에 저장된 자신의 .exe.config 및 *사용자*.config 파일을해야합니다.

 애플리케이션 설정 기능이 새로운 배포 기술을 통해 작동하는 방법에 대한 자세한 내용은 [ClickOnce 및 애플리케이션 설정](/visualstudio/deployment/clickonce-and-application-settings)을 참조하세요. ClickOnce 데이터 디렉토리에 대한 자세한 내용은 [ClickOnce 응용 프로그램에서 로컬 및 원격 데이터에 액세스하는 것을](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)참조하십시오.

## <a name="application-settings-and-security"></a>애플리케이션 설정 및 보안
 애플리케이션 설정은 인터넷이나 인트라넷에서 호스팅되는 Windows Forms 애플리케이션의 기본적인 제한된 환경인 부분 신뢰 환경에서 작동하도록 설계되었습니다. 기본 설정 공급자를 포함한 애플리케이션 설정을 사용하는 데에는 부분 신뢰 권한만 필요합니다.

 응용 프로그램 설정이 ClickOnce 응용 `user`프로그램에서 사용되는 경우 .config 파일은 ClickOnce 데이터 디렉토리에 저장됩니다. 응용 프로그램의 `user`.config 파일의 크기는 ClickOnce에서 설정한 데이터 디렉터리 할당량을 초과할 수 없습니다. 자세한 내용은 [ClickOnce 및 애플리케이션 설정](/visualstudio/deployment/clickonce-and-application-settings)을 참조하세요.

## <a name="custom-settings-providers"></a>사용자 지정 설정 공급자
 응용 프로그램 설정 아키텍처에는 <xref:System.Configuration.ApplicationSettingsBase>에서 파생된 응용 프로그램 설정 래퍼 클래스와 에서 파생된 관련 설정 공급자 <xref:System.Configuration.SettingsProvider>또는 공급자 간에 느슨한 결합이 있습니다. 이 연결은 래퍼 <xref:System.Configuration.SettingsProviderAttribute> 클래스 또는 개별 속성에 적용된 경우에만 정의됩니다. 설정 공급자가 명시적으로 지정되지 않은 경우 <xref:System.Configuration.LocalFileSettingsProvider>기본 공급자, 이가 사용됩니다. 따라서 이 아키텍처는 사용자 지정 설정 공급자를 만들고 사용할 수 있도록 지원합니다.

 예를 들어 Microsoft SQL Server 데이터베이스에 모든 설정 데이터를 저장하는 공급자인 `SqlSettingsProvider`를 개발하여 사용한다고 가정합니다. <xref:System.Configuration.SettingsProvider>-derived 클래스는 메서드에서 `Initialize` 이 정보를 형식의 <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>매개 변수로 수신합니다. 그런 다음 데이터 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> 저장소에서 설정을 검색하고 <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> 저장하는 메서드를 구현합니다. 공급자는 <xref:System.Configuration.SettingsPropertyCollection> 제공된 속성을 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> 사용하여 속성의 이름, 유형 및 범위뿐만 아니라 해당 속성에 대해 정의된 다른 설정 특성을 결정할 수 있습니다.

 공급자는 구현이 분명하지 않은 속성 하나와 메서드 하나를 구현해야 합니다. 속성은 <xref:System.Configuration.SettingsProvider.ApplicationName%2A> 추상 속성입니다. <xref:System.Configuration.SettingsProvider> 다음을 반환하도록 프로그래밍해야 합니다.

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 또한 파생 클래스는 인수를 사용하지 않고 값을 반환하지 않는 `Initialize` 메서드도 구현해야 합니다. 이 메서드는 에 <xref:System.Configuration.SettingsProvider>의해 정의되지 않습니다.

 마지막으로 공급자에서 <xref:System.Configuration.IApplicationSettingsProvider> 설정 새로 고침, 설정 기본값으로 되돌리기, 한 응용 프로그램 버전에서 다른 응용 프로그램 버전으로 설정을 업그레이드하는 지원을 제공하기 위해 공급자를 구현합니다.

 공급자를 구현하고 컴파일했으면 설정 클래스에서 기본값 대신 이 공급자를 사용하도록 지시해야 합니다. 을 통해 이 <xref:System.Configuration.SettingsProviderAttribute>작업을 수행합니다. 전체 설정 클래스에 적용된 경우 공급자는 클래스가 정의하는 각 설정에 대해 사용됩니다. 개별 설정에 적용하는 경우 응용 프로그램 설정 아키텍처는 해당 <xref:System.Configuration.LocalFileSettingsProvider> 설정에 대해서만 해당 공급자를 사용하고 나머지는 사용합니다. 다음 코드 예제에서는 사용자 지정 공급자를 사용하도록 설정 클래스에 지시하는 방법을 보여 줍니다.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 한 공급자를 여러 스레드에서 동시에 호출할 수 있지만, 공급자가 항상 동일한 스토리지 위치에 쓰므로 애플리케이션 아키텍처는 공급자 클래스의 단일 인스턴스만 인스턴스화합니다.

> [!IMPORTANT]
> 공급자가 스레드로부터 안전하며 구성 파일에 쓸 수 있는 스레드를 한 번에 하나씩 허용하는지 확인해야 합니다.

 공급자는 <xref:System.Configuration?displayProperty=nameWithType> 네임스페이스에 정의된 모든 설정 특성을 지원할 필요는 없지만 최소한 지원 <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute>및 을 지원해야 하며 또한 지원해야 <xref:System.Configuration.DefaultSettingValueAttribute>합니다. 지원하지 않는 특성에 대해서는 공급자가 알림 없이 실패해야 하며 예외를 throw하면 안됩니다. 그러나 설정 클래스에서 적용 <xref:System.Configuration.ApplicationScopedSettingAttribute> 및 동일한 설정과 <xref:System.Configuration.UserScopedSettingAttribute> 같은 잘못된 특성 조합을 사용하는 경우 공급자는 예외를 throw하고 작업을 중단해야 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [애플리케이션 설정 개요](application-settings-overview.md)
- [사용자 지정 컨트롤에 대한 애플리케이션 설정](application-settings-for-custom-controls.md)
- [ClickOnce 및 애플리케이션 설정](/visualstudio/deployment/clickonce-and-application-settings)
- [애플리케이션 설정 스키마](../../configure-apps/file-schema/application-settings-schema.md)
