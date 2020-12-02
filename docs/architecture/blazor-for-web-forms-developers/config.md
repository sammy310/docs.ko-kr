---
title: 앱 구성
description: BlazorConfigurationManager를 사용 하지 않고 앱을 구성 하는 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 11/20/2020
ms.openlocfilehash: 360d9077bc981a2e9875bb1f86b49c0029424d6e
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509795"
---
# <a name="app-configuration"></a>앱 구성

Web Forms에서 앱 구성을 로드 하는 기본적인 방법은 *web.config* 파일의 항목을 &mdash; 서버 또는 *web.config* 에서 참조 하는 관련 구성 파일에 포함 하는 것입니다. 정적 개체를 사용 하 여 앱 `ConfigurationManager` 설정, 데이터 저장소 연결 문자열 및 앱에 추가 되는 기타 확장 된 구성 공급자와 상호 작용할 수 있습니다. 다음 코드에 표시 된 것 처럼 앱 구성과의 상호 작용을 확인 하는 것이 일반적입니다.

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

ASP.NET Core 및 서버 쪽에서 Blazor 앱이 WINDOWS IIS 서버에서 호스팅되는 경우 *web.config* 파일이 있을 수 있습니다. 그러나 `ConfigurationManager` 이 구성과 상호 작용 하지 않으며 다른 원본에서 더 많은 구조화 된 앱 구성을 받을 수 있습니다. 구성이 수집 되는 방법 및 *web.config* 파일에서 구성 정보에 액세스 하는 방법을 살펴보겠습니다.

## <a name="configuration-sources"></a>구성 원본

ASP.NET Core는 앱에 사용할 수 있는 많은 구성 원본을 인식 합니다. 프레임 워크는 기본적으로 이러한 기능을 가장 잘 제공 하려고 시도 합니다. ASP.NET Core 하 여 이러한 다양 한 원본에서 구성을 읽고 집계 합니다. 나중에 동일한 구성 키에 대해 로드 된 값이 이전 값 보다 우선적으로 적용 됩니다.

ASP.NET Core는 클라우드를 인식 하 고 연산자와 개발자 모두를 위해 앱을 쉽게 구성할 수 있도록 설계 되었습니다. ASP.NET Core는 환경에서 인식 되며 또는 환경에서 실행 중인지 확인 `Production` `Development` 합니다. 환경 표시기는 `ASPNETCORE_ENVIRONMENT` 시스템 환경 변수에 설정 됩니다. 구성 된 값이 없는 경우 앱은 기본적으로 환경에서 실행 중으로 설정 됩니다 `Production` .

앱은 환경 이름을 기반으로 여러 소스에서 구성을 트리거하고 추가할 수 있습니다. 기본적으로 구성은 다음 리소스에서 나열 된 순서 대로 로드 됩니다.

1. 파일 *에appsettings.js* (있는 경우)
1. *appsettings. {ENVIRONMENT_NAME}. json* 파일 (있는 경우)
1. 디스크의 사용자 비밀 파일 (있는 경우)
1. 환경 변수
1. 명령줄 인수

## <a name="appsettingsjson-format-and-access"></a>appsettings.js형식 및 액세스

파일 *의appsettings.js* 는 다음 JSON 처럼 구조화 된 값이 있는 계층적 일 수 있습니다.

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

위의 JSON을 사용 하 여 표시 되 면 구성 시스템은 자식 값을 평면화 하 고 정규화 된 계층적 경로를 참조 합니다. 콜론 ( `:` ) 문자는 계층의 각 속성을 구분 합니다. 예를 들어 구성 키는 `section1:key0` `section1` 개체 리터럴의 값에 액세스 합니다 `key0` .

## <a name="user-secrets"></a>사용자 비밀

사용자 암호는 다음과 같습니다.

* 앱 개발 폴더 외부의 개발자 워크스테이션에서 JSON 파일에 저장 되는 구성 값입니다.
* 환경에서 실행 될 때만 로드 `Development` 됩니다.
* 특정 앱과 연결 됩니다.
* .NET CLI의 명령을 사용 하 여 관리 `user-secrets` 됩니다.

다음 명령을 실행 하 여 암호 저장소에 대 한 앱을 구성 합니다 `user-secrets` .

```dotnetcli
dotnet user-secrets init
```

이전 명령은 `UserSecretsId` 프로젝트 파일에 요소를 추가 합니다. 요소는 암호를 앱에 연결 하는 데 사용 되는 GUID를 포함 합니다. 그런 다음 명령을 사용 하 여 비밀을 정의할 수 있습니다 `set` . 예를 들어:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

위의 명령은 `Parent:ApiKey` 값을 사용 하 여 개발자의 워크스테이션에서 구성 키를 사용할 수 있도록 합니다 `12345` .

사용자 암호를 만들고, 저장 하 고, 관리 하는 방법에 대 한 자세한 내용은 [ASP.NET Core 문서에서 개발 중인 앱 비밀의 안전한 저장소](/aspnet/core/security/app-secrets) 를 참조 하세요.

## <a name="environment-variables"></a>환경 변수

앱 구성에 로드 되는 다음 값 집합은 시스템의 환경 변수입니다. 이제 모든 시스템 환경 변수 설정을 구성 API를 통해 액세스할 수 있습니다. 응용 프로그램 내에서 읽을 때 계층적 값은 콜론 문자로 구분 됩니다. 그러나 일부 운영 체제에서는 콜론 문자 환경 변수 이름을 사용할 수 없습니다. ASP.NET Core는 이중 밑줄 ()이 있는 값에 액세스할 때 콜론으로 변환 하 여이 제한을 해결 `__` 합니다. `Parent:ApiKey`위의 사용자 암호 섹션의 값은 환경 변수를 사용 하 여 재정의할 수 있습니다 `Parent__ApiKey` .

## <a name="command-line-arguments"></a>명령줄 인수

앱이 시작 될 때 구성도 명령줄 인수로 제공할 수 있습니다. 이중 대시 ( `--` ) 또는 슬래시 ( `/` ) 표기법을 사용 하 여 설정할 구성 값의 이름과 구성할 값을 표시 합니다. 구문은 다음 명령과 유사 합니다.

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>반환 web.config

IIS의 Windows에 앱을 배포한 경우 *web.config* 파일은 여전히 앱을 관리 하도록 iis를 구성 합니다. 기본적으로 IIS는 ASP.NET Core 모듈 (간에 m)에 대 한 참조를 추가 합니다. C l i m은 Kestrel 웹 서버 대신 앱을 호스트 하는 네이티브 IIS 모듈입니다. 이 *web.config* 섹션은 다음 XML 태그와 유사 합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

요소에 요소를 중첩 하 여 앱 별 구성을 정의할 수 있습니다 `environmentVariables` `aspNetCore` . 이 섹션에 정의 된 값은 ASP.NET Core 앱에 환경 변수로 제공 됩니다. 환경 변수는 해당 앱 시작 세그먼트에서 적절 하 게 로드 됩니다.

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a>앱에서 구성 읽기

ASP.NET Core는 인터페이스를 통해 앱 구성을 제공 <xref:Microsoft.Extensions.Configuration.IConfiguration> 합니다. 구성 Blazor 요소, Blazor 페이지 및 구성에 액세스 해야 하는 기타 ASP.NET Core 관리 클래스에서이 구성 인터페이스를 요청 해야 합니다. ASP.NET Core 프레임 워크는 이전에 구성 된 확인 된 구성으로이 인터페이스를 자동으로 채웁니다. Blazor페이지 또는 구성 요소의 razor 태그에서 `IConfiguration` `@inject` 다음과 같이 *razor* 파일 상단에 지시문을 사용 하 여 개체를 주입할 수 있습니다.

```razor
@inject IConfiguration Configuration
```

이 이전 문은 `IConfiguration` `Configuration` Razor 템플릿의 나머지 부분에서 개체를 변수로 사용할 수 있도록 합니다.

인덱서 매개 변수로 찾는 구성 설정 계층을 지정 하 여 개별 구성 설정을 읽을 수 있습니다.

```csharp
var mySetting = Configuration["section1:key0"];
```

<xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> `GetSection("section1")` 이전 예제에서 section1에 대 한 구성을 검색 하는 것과 유사한 구문을 사용 하 여 특정 위치의 키 컬렉션을 검색 하는 메서드를 사용 하 여 전체 구성 섹션을 페치할 수 있습니다.

## <a name="strongly-typed-configuration"></a>강력한 형식의 구성

Web Forms에서는 <xref:System.Configuration.ConfigurationSection> 형식 및 관련 형식에서 상속 되는 강력한 형식의 구성 형식을 만들 수 있었습니다. 를 통해 `ConfigurationSection` 이러한 구성 값에 대 한 비즈니스 규칙 및 처리를 구성할 수 있습니다.

ASP.NET Core에서 구성 값을 받을 클래스 계층 구조를 지정할 수 있습니다. 이러한 클래스:

* 부모 클래스에서 상속할 필요가 없습니다.
* `public`캡처할 구성 구조에 대 한 속성 및 형식 참조와 일치 하는 속성을 포함 해야 합니다.

이전appsettings.js샘플 *에서* 다음 클래스를 정의 하 여 값을 캡처할 수 있습니다.

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

이 클래스 계층 구조는 메서드에 다음 줄을 추가 하 여 채울 수 있습니다 `Startup.ConfigureServices` .

```csharp
services.Configure<MyConfig>(Configuration);
```

응용 프로그램의 나머지 부분에서는 `@inject` `IOptions<MyConfig>` 강력한 형식의 구성 설정을 수신 하기 위해 형식의 Razor 템플릿에서 클래스 또는 지시문에 입력 매개 변수를 추가할 수 있습니다. `IOptions<MyConfig>.Value`속성은 `MyConfig` 구성 설정에서 채워진 값을 생성 합니다.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

옵션 기능에 대 한 자세한 내용은 [ASP.NET Core의 옵션 패턴](/aspnet/core/fundamentals/configuration/options#options-interfaces) 에서 찾을 수 있습니다.

>[!div class="step-by-step"]
>[이전](middleware.md)
>[다음](security-authentication-authorization.md)
