---
title: .NET의 구성 공급자
description: 구성 공급자 API를 사용하여 .NET 애플리케이션을 구성하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 03/08/2021
ms.openlocfilehash: 5f248c93de1773a8bbe8209f002806fb196bb260
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605011"
---
# <a name="configuration-providers-in-net"></a>.NET의 구성 공급자

.NET에서 구성은 구성 공급자를 사용하여 수행할 수 있습니다. 다양한 구성 소스를 사용하는 여러 유형의 공급자가 있습니다. 이 문서에서는 모든 다양한 구성 공급자와 해당 소스를 자세히 설명합니다.

- [파일 구성 공급자](#file-configuration-provider)
- [환경 변수 구성 공급자](#environment-variable-configuration-provider)
- [명령줄 구성 공급자](#command-line-configuration-provider)
- [파일별 키 구성 공급자](#key-per-file-configuration-provider)
- [메모리 구성 공급자](#memory-configuration-provider)

## <a name="file-configuration-provider"></a>파일 구성 공급자

<xref:Microsoft.Extensions.Configuration.FileConfigurationProvider>는 파일 시스템에서 구성을 로드하기 위한 기본 클래스입니다. 다음 구성 공급자는 `FileConfigurationProvider`에서 파생됩니다.

- [JSON 구성 공급자](#json-configuration-provider)
- [XML 구성 공급자](#xml-configuration-provider)
- [INI 구성 공급자](#ini-configuration-provider)

### <a name="json-configuration-provider"></a>JSON 구성 공급자

<xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> 클래스는 JSON 파일에서 구성을 로드합니다. [`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json) NuGet 패키지를 설치합니다.

오버로드는 다음을 지정할 수 있습니다.

- 파일이 선택 사항인지 여부
- 파일을 변경하는 경우 구성이 다시 로드되는지 여부

다음 코드를 살펴보세요.

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="1-39,43-44" highlight="23-29":::

위의 코드는

- <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> 메서드에 기본적으로 추가된 기존 구성 공급자를 모두 지웁니다.
- 다음 옵션을 사용하여 *appsettings.json* 및 *appsettings*.`Environment`.*json* 파일을 로드하도록 JSON 구성 공급자를 구성합니다.
  - `optional: true`: 파일은 선택 사항입니다.
  - `reloadOnChange: true`은: 변경 내용이 저장되면 파일이 다시 로드됩니다.

JSON 설정은 [환경 변수 구성 공급자](#environment-variable-configuration-provider) 및 [명령줄 구성 공급자](#command-line-configuration-provider)의 설정에 따라 재정의됩니다.

다양한 구성 설정을 사용하는 예제 *appsettings.json* 파일은 다음과 같습니다.

:::code language="json" source="snippets/configuration/console-json/appsettings.json":::

구성 공급자가 추가된 후 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> 인스턴스에서 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType>를 호출하여 <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> 개체를 가져올 수 있습니다. 구성 루트는 구성 계층 구조의 루트를 나타냅니다. 구성의 섹션은 .NET 개체의 인스턴스에 바인딩되고 나중에 <xref:Microsoft.Extensions.Options.IOptions%601> 종속성 주입을 통해 제공될 수 있습니다.

다음과 같이 정의된 `TransientFaultHandlingOptions` 클래스를 고려하세요.

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs":::

다음 코드는 구성 루트를 빌드하고, 섹션을 `TransientFaultHandlingOptions` 클래스 형식에 바인딩하고, 바인딩된 값을 콘솔 창에 출력합니다.

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

애플리케이션은 다음 샘플 출력을 작성합니다.

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="40-42":::

### <a name="xml-configuration-provider"></a>XML 구성 공급자

<xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> 클래스는 런타임에 XML 파일에서 구성을 로드합니다. [`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml) NuGet 패키지를 설치합니다.

다음 코드에서는 XML 구성 공급자를 사용한 XML 파일의 구성을 보여 줍니다.

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="1-34,52,58-59" highlight="23-34":::

앞의 코드가 하는 역할은 다음과 같습니다.

- <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> 메서드에 기본적으로 추가된 기존 구성 공급자를 모두 지웁니다.
- 다음 옵션을 사용하여 *appsettings.xml* 및 *repeating-example.xml* 파일을 로드하도록 XML 구성 공급자를 구성합니다.
  - `optional: true`: 파일은 선택 사항입니다.
  - `reloadOnChange: true`은: 변경 내용이 저장되면 파일이 다시 로드됩니다.
- 환경 변수 구성 공급자를 구성합니다.
- 지정된 `args`에 인수가 포함된 경우 명령줄 구성 공급자를 구성합니다.

XML 설정은 [환경 변수 구성 공급자](#environment-variable-configuration-provider) 및 [명령줄 구성 공급자](#command-line-configuration-provider)의 설정에 따라 재정의됩니다.

다양한 구성 설정을 사용하는 예제 *appsettings.xml* 파일은 다음과 같습니다.

:::code language="xml" source="snippets/configuration/console-xml/appsettings.xml":::

같은 요소 이름을 사용하는 반복 요소는 다음과 같이 `name` 특성을 사용하여 요소를 구분하면 작동합니다.

:::code language="xml" source="snippets/configuration/console-xml/repeating-example.xml":::

다음 코드는 이전 구성 파일을 읽고 키 및 값을 표시합니다.

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="36-51":::

애플리케이션은 다음 샘플 출력을 작성합니다.

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="53-57":::

특성을 사용하여 값을 제공할 수 있습니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <key attribute="value" />
  <section>
    <key attribute="value" />
  </section>
</configuration>
```

이전 구성 파일은 `value`와 함께 다음 키를 로드합니다.

- `key:attribute`
- `section:key:attribute`

### <a name="ini-configuration-provider"></a>INI 구성 공급자

<xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> 클래스는 런타임에 INI 파일에서 구성을 로드합니다. [`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini) NuGet 패키지를 설치합니다.

다음 코드는 모든 구성 공급자를 지우고 두 개의 INI 파일을 소스로 사용하여 `IniConfigurationProvider`를 추가합니다.

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="1-37,44-45" highlight="24-30":::

다양한 구성 설정을 사용하는 예제 *appsettings.ini* 파일은 다음과 같습니다.

:::code language="ini" source="snippets/configuration/console-ini/appsettings.ini":::

다음 코드는 이전 구성 설정을 콘솔 창에 기록하여 표시합니다.

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="32-36":::

애플리케이션은 다음 샘플 출력을 작성합니다.

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="38-43":::

## <a name="environment-variable-configuration-provider"></a>환경 변수 구성 공급자

기본 구성을 사용하여 <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider>는 *appsettings.json*, *appsettings.* `Environment` *.json*, 비밀 관리자를 읽은 후 환경 변수 키-값 쌍에서 구성을 로드합니다. 따라서 환경에서 읽은 키 값이 *appsettings.json*, *appsettings.* `Environment` *.json* 및 비밀 관리자에서 읽은 값을 재정의합니다.

`:` 구분 기호는 모든 플랫폼의 환경 변수 계층적 키에서 작동하지 않습니다. 이중 밑줄(`__`)은 자동으로 `:`으로 바뀌며 모든 플랫폼에서 지원됩니다. 예를 들어 `:` 구분 기호는 [Bash](https://linuxhint.com/bash-environment-variables)에서 지원되지 않지만 `__`은 지원됩니다.

다음 `set` 명령은,

- Windows에서 위의 예제에 나오는 환경 키 및 값을 설정합니다.
- 기본값에서 설정을 변경하여 테스트합니다. `dotnet run` 명령은 프로젝트 디렉터리에서 실행해야 합니다.

```dotnetcli
set SecretKey="Secret key from environment"
set TransientFaultHandlingOptions__Enabled="true"
set TransientFaultHandlingOptions__AutoRetryDelay="00:00:13"

dotnet run
```

위의 환경 설정은,

- 설정된 명령 창에서 시작된 프로세스에서만 설정됩니다.
- Visual Studio에서 시작된 웹앱에서는 읽을 수 없습니다.

다음 [setx](/windows-server/administration/windows-commands/setx) 명령을 사용하여 Windows에서 환경 키 및 값을 설정할 수 있습니다. `set`와 달리, `setx` 설정은 유지됩니다. `/M`은 시스템 환경에서 변수를 설정합니다. `/M` 스위치를 사용하지 않으면 사용자 환경 변수가 설정됩니다.

```dotnetcli
setx SecretKey "Secret key from setx environment" /M
setx TransientFaultHandlingOptions__Enabled "true" /M
setx TransientFaultHandlingOptions__AutoRetryDelay "00:00:05" /M

dotnet run
```

위의 명령이 *apsettings.json* 및 *appsettings.* `Environment` *.json* 을 재정의하는지 테스트하려면:

- Visual Studio를 사용하는 경우: Visual Studio를 종료했다가 다시 시작합니다.
- CLI를 사용하는 경우: 새 명령 창을 시작하고 `dotnet run`을 입력합니다.

환경 변수의 접두사를 지정하는 문자열을 사용하여 <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A>를 호출합니다.

:::code language="csharp" source="snippets/configuration/console-env/Program.cs" highlight="21-22":::

위의 코드에서

- `config.AddEnvironmentVariables(prefix: "CustomPrefix_")`는 기본 구성 공급자 뒤에 추가됩니다. 구성 공급자 순서 지정 예제는 [XML 구성 공급자](#xml-configuration-provider)를 참조하세요.
- `CustomPrefix_` 접두사를 사용하여 설정된 환경 변수는 기본 구성 공급자를 재정의합니다. 여기에는 접두사 없는 환경 변수가 포함됩니다.

구성 키-값 쌍을 읽으면 접두사는 제거됩니다.

다음 명령은 사용자 지정 접두사를 테스트합니다.

```dotnetcli
set CustomPrefix__SecretKey="Secret key with CustomPrefix_ environment"
set CustomPrefix__TransientFaultHandlingOptions__Enabled=true
set CustomPrefix__TransientFaultHandlingOptions__AutoRetryDelay=00:00:21

dotnet run
```

기본 구성은 `DOTNET_` 접두사가 붙은 환경 변수 및 명령줄 인수를 로드합니다. `DOTNET_` 접두사는 .NET에서 [호스트](generic-host.md#host-configuration) 및 [앱 구성](generic-host.md#app-configuration)에 사용되지만 사용자 구성에는 사용되지 않습니다.

호스트 및 앱 구성에 대한 자세한 내용은 [.NET 제네릭 호스트](generic-host.md)를 참조하세요.

[Azure App Service](https://azure.microsoft.com/services/app-service)의 **설정 > 구성** 페이지에서 **새 애플리케이션 설정** 을 선택합니다. Azure App Service 애플리케이션 설정은,

- 미사용 시 암호화되고 암호화된 채널을 통해 전송됩니다.
- 환경 변수로 노출됩니다.

### <a name="connection-string-prefixes"></a>연결 문자열 접두사

구성 API에는 네 개의 연결 문자열 환경 변수에 대한 특별한 처리 규칙이 있습니다. 해당 연결 문자열은 앱 환경의 Azure 연결 문자열을 구성하는 데 관련됩니다. 기본 구성을 사용하거나 `AddEnvironmentVariables`에 제공된 접두사가 없는 경우 표에 표시된 접두사가 붙은 환경 변수가 앱에 로드됩니다.

| 연결 문자열 접두사 | 공급자                                                                |
|--------------------------|-------------------------------------------------------------------------|
| `CUSTOMCONNSTR_`         | 사용자 지정 공급자                                                         |
| `MYSQLCONNSTR_`          | [MySQL](https://www.mysql.com)                                          |
| `SQLAZURECONNSTR_`       | [Azure SQL Database](https://azure.microsoft.com/services/sql-database) |
| `SQLCONNSTR_`            | [SQL Server](https://www.microsoft.com/sql-server)                      |

표에 표시된 네 개 접두사 중 하나가 붙은 환경 변수가 검색되어 구성으로 로드되면 다음과 같이 됩니다.

- 환경 변수 접두사를 제거하고 구성 키 섹션(`ConnectionStrings`)을 추가하여 구성 키가 생성됩니다.
- 데이터베이스 연결 제공자(지정된 공급자가 없는 `CUSTOMCONNSTR_` 제외)를 나타내는 새 구성 키-값 쌍이 생성됩니다.

| 환경 변수 키 | 변환된 구성 키 | 공급자 구성 항목                                                    |
|--------------------------|-----------------------------|---------------------------------------------------------------------------------|
| `CUSTOMCONNSTR_{KEY}`    | `ConnectionStrings:{KEY}`   | 구성 항목이 생성되지 않습니다.                                                |
| `MYSQLCONNSTR_{KEY}`     | `ConnectionStrings:{KEY}`   | 키: `ConnectionStrings:{KEY}_ProviderName`:<br>값: `MySql.Data.MySqlClient` |
| `SQLAZURECONNSTR_{KEY}`  | `ConnectionStrings:{KEY}`   | 키: `ConnectionStrings:{KEY}_ProviderName`:<br>값: `System.Data.SqlClient`  |
| `SQLCONNSTR_{KEY}`       | `ConnectionStrings:{KEY}`   | 키: `ConnectionStrings:{KEY}_ProviderName`:<br>값: `System.Data.SqlClient`  |

### <a name="environment-variables-set-in-launchsettingsjson"></a>launchSettings.json에 설정된 환경 변수

*launchSettings.json* 에 설정된 환경 변수는 시스템 환경에 설정된 변수를 재정의합니다.

## <a name="command-line-configuration-provider"></a>명령줄 구성 공급자

기본 구성을 사용하여 <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider>는 다음 구성 소스 뒤에 명령줄 인수 키-값 쌍에서 구성을 로드합니다.

- *appsettings.json* 및 *appsettings*.`Environment`.*json* 파일
- `Development` 발 환경의 앱 비밀(비밀 관리자)
- 환경 변수.

기본적으로 명령줄에 설정된 구성 값은 다른 모든 구성 공급자를 사용하여 설정된 구성 값을 재정의합니다.

### <a name="command-line-arguments"></a>명령줄 인수

다음 명령은 `=`을 사용하여 키 및 값을 설정합니다.

```dotnetcli
dotnet run SecretKey="Secret key from command line"
```

다음 명령은 `/`를 사용하여 키 및 값을 설정합니다.

```dotnetcli
dotnet run /SecretKey "Secret key set from forward slash"
```

다음 명령은 `--`를 사용하여 키 및 값을 설정합니다.

```dotnetcli
dotnet run --SecretKey "Secret key set from double hyphen"
```

키 값은,

- `=` 다음에 와야 합니다. 또는 값이 공백에 다음에 오는 경우 키에 `--` 또는 `/` 접두사가 있어야 합니다.
- `=`이 사용된 경우 필요하지 않습니다. 예: `SomeKey=`.

같은 명령 내에서 `=`을 사용하는 명령줄 인수 키-값 쌍을 공백을 사용하는 키-값 쌍과 함께 사용하지 마세요.

## <a name="key-per-file-configuration-provider"></a>파일별 키 구성 공급자

<xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider>는 디렉터리의 파일을 구성 키-값 쌍으로 사용합니다. 키는 파일 이름이고, 값은 파일의 콘텐츠입니다. 파일별 키 구성 공급자는 Docker 호스팅 시나리오에서 사용됩니다.

파일별 키 구성을 활성화하려면 <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> 인스턴스에서 <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> 확장 메서드를 호출합니다. 파일의 `directoryPath`는 절대 경로여야 합니다.

오버로드에서는 다음을 지정할 수 있습니다.

- 소스를 구성하는 `Action<KeyPerFileConfigurationSource>` 대리자
- 디렉터리가 선택 사항인지 여부와 디렉터리의 경로

두 개의 밑줄(`__`)은 파일 이름에서 구성 키 구분 기호로 사용됩니다. 예를 들어, 파일 이름 `Logging__LogLevel__System`은 구성 키 `Logging:LogLevel:System`을 생성합니다.

호스트를 빌드할 때 `ConfigureAppConfiguration`을 호출하여 앱의 구성을 지정합니다.

```csharp
.ConfigureAppConfiguration((_, configuration) =>
{
    var path = Path.Combine(
        Directory.GetCurrentDirectory(), "path/to/files");

    configuration.AddKeyPerFile(directoryPath: path, optional: true);
})
```

## <a name="memory-configuration-provider"></a>메모리 구성 공급자

<xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider>는 메모리 내 컬렉션을 구성 키-값 쌍으로 사용합니다.

다음 코드는 구성 시스템에 메모리 컬렉션을 추가합니다.

:::code language="csharp" source="snippets/configuration/console-memory/Program.cs" highlight="22-29":::

이전 코드에서 <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType>은 기본 구성 공급자 뒤에 메모리 공급자를 추가합니다. 구성 공급자 순서 지정 예제는 [XML 구성 공급자](#xml-configuration-provider)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [.NET의 구성](configuration.md)
- [.NET 일반 호스트](generic-host.md)
- [사용자 지정 구성 공급자 구현](custom-configuration-provider.md)
