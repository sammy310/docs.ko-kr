---
title: 앱 구성
description: ConfigurationManager를 사용하지 않고 Blazor 앱을 구성하는 방법에 대해 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588241"
---
# <a name="app-configuration"></a>앱 구성

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Web Forms에서 앱 구성을 로드하는 기본 방법은 web.config 파일의&mdash;항목을 서버또는 *web.config에서* 참조하는 관련 구성 파일입니다. *web.config* 정적 `ConfigurationManager` 개체를 사용하여 앱 설정, 데이터 리포지토리 연결 문자열 및 앱에 추가된 기타 확장 된 구성 공급자와 상호 작용할 수 있습니다. 다음 코드에서 볼 수 있듯이 앱 구성과의 상호 작용을 확인하는 것이 일반적입니다.

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

ASP.NET 코어 및 서버 측 Blazor를 사용하면 앱이 Windows IIS 서버에서 호스팅되는 경우 *web.config* 파일이 있을 수 있습니다. 그러나 이 구성과의 `ConfigurationManager` 상호 작용은 없으며 다른 소스에서 보다 구조화된 앱 구성을 받을 수 있습니다. 구성을 수집하는 방법과 *web.config* 파일에서 구성 정보에 계속 액세스하는 방법을 살펴보겠습니다.

## <a name="configuration-sources"></a>구성 원본

ASP.NET Core는 앱에 사용할 수 있는 구성 소스가 많다는 것을 알고 있습니다. 프레임워크는 기본적으로 이러한 기능 중 최고를 제공하려고 시도합니다. 구성은 ASP.NET Core에 의해 이러한 다양한 소스에서 읽고 집계됩니다. 동일한 구성 키에 대해 나중에 로드된 값이 이전 값보다 우선합니다.

ASP.NET Core는 클라우드를 인식하고 운영자와 개발자 모두 앱을 더 쉽게 구성할 수 있도록 설계되었습니다. ASP.NET Core는 환경을 인식하고 사용자 또는 `Production` `Development` 환경에서 실행되고 있는지 알고 있습니다. 환경 표시기는 시스템 `ASPNETCORE_ENVIRONMENT` 환경 변수에 설정됩니다. 값이 구성되지 않은 경우 앱은 기본적으로 `Production` 환경에서 실행됩니다.

앱은 환경 이름에 따라 여러 소스에서 구성을 트리거하고 추가할 수 있습니다. 기본적으로 구성은 나열된 순서대로 다음 리소스에서 로드됩니다.

1. *appsettings.json* 파일(있는 경우)
1. *앱 설정. {ENVIRONMENT_NAME}.json* 파일(있는 경우)
1. 디스크에 있는 사용자 비밀 파일(있는 경우)
1. 환경 변수
1. 명령줄 인수

## <a name="appsettingsjson-format-and-access"></a>appsettings.json 형식 및 액세스

*appsettings.json* 파일은 다음과 같은 구조의 값으로 계층적일 수 있습니다.

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

앞의 JSON과 함께 제공될 때 구성 시스템은 자식 값을 평평하게 하고 정규화된 계층 적 경로를 참조합니다. 콜론`:`() 문자는 계층 구조의 각 속성을 구분합니다. 예를 들어 구성 `section1:key0` 키는 개체 `section1` 리터럴값에 `key0` 액세스합니다.

## <a name="user-secrets"></a>사용자 비밀

사용자 암호는 다음과 같습니다.

* 앱 개발 폴더 외부의 개발자 워크스테이션의 JSON 파일에 저장된 구성 값입니다.
* 환경에서 실행할 때만 `Development` 로드됩니다.
* 특정 앱과 연결되었습니다.
* .NET 코어 CLI의 `user-secrets` 명령으로 관리됩니다.

명령을 실행하여 비밀 저장소에 `user-secrets` 대한 앱을 구성합니다.

```dotnetcli
dotnet user-secrets init
```

앞의 명령은 프로젝트 `UserSecretsId` 파일에 요소를 추가합니다. 요소에는 비밀을 앱과 연결하는 데 사용되는 GUID가 포함되어 있습니다. 그런 다음 명령을 통해 `set` 암호를 정의할 수 있습니다. 예를 들어:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

위의 명령은 개발자의 `Parent:ApiKey` 워크스테이션에서 구성 키를 값으로 `12345`사용할 수 있게 합니다.

사용자 기밀을 생성, 저장 및 관리하는 데 대한 자세한 내용은 ASP.NET Core 문서에서 [개발 중 앱 비밀의 안전한 저장소를](/aspnet/core/security/app-secrets) 참조하십시오.

## <a name="environment-variables"></a>환경 변수

앱 구성에 로드된 다음 값 집합은 시스템의 환경 변수입니다. 이제 구성 API를 통해 시스템의 모든 환경 변수 설정에 액세스할 수 있습니다. 계층 적 값은 앱 내에서 읽을 때 병합 문자로 병합되고 구분됩니다. 그러나 일부 운영 체제에서는 콜론 문자 환경 변수 이름을 허용하지 않습니다. ASP.NET Core는 이중 밑줄()`__`값이 있는 값을 액세스할 때 콜론으로 변환하여 이러한 제한을 해결합니다. 위의 `Parent:ApiKey` 사용자 암호 섹션의 값을 환경 변수로 `Parent__ApiKey`재정의할 수 있습니다.

## <a name="command-line-arguments"></a>명령줄 인수

구성은 앱을 시작할 때 명령줄 인수로 제공될 수도 있습니다. 이중 대시 ()`--`또는 정방향`/`슬래시 () 표기법() 표기법으로 설정할 구성 값의 이름과 구성할 값을 나타냅니다. 구문은 다음 명령과 유사합니다.

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>web.config의 반환

IIS에서 Windows에 앱을 배포한 경우에도 *web.config* 파일은 여전히 IIS를 관리하도록 구성합니다. 기본적으로 IIS는 ASP.NET 코어 모듈(ANCM)에 대한 참조를 추가합니다. ANCM은 Kestrel 웹 서버 대신 앱을 호스팅하는 기본 IIS 모듈입니다. 이 *web.config* 섹션은 다음과 같은 XML 태그와 유사합니다.

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

앱별 구성은 `environmentVariables` `aspNetCore` 요소에 요소를 중첩하여 정의할 수 있습니다. 이 섹션에 정의된 값은 ASP.NET Core 앱에 환경 변수로 표시됩니다. 환경 변수는 앱 시작 세그먼트 동안 적절하게 로드됩니다.

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

ASP.NET 코어는 인터페이스를 <xref:Microsoft.Extensions.Configuration.IConfiguration> 통해 앱 구성을 제공합니다. 이 구성 인터페이스는 Blazor 구성 요소, Blazor 페이지 및 구성에 액세스해야 하는 기타 ASP.NET Core 관리 클래스에서 요청해야 합니다. ASP.NET Core 프레임워크는 이 인터페이스를 이전에 구성된 해결된 구성으로 자동으로 채웁니다. Blazor 페이지 또는 구성 요소의 Razor 태그에서 다음과 `IConfiguration` 같은 `@inject` *.razor* 파일 의 맨 위에 지시문과 함께 개체를 삽입할 수 있습니다.

```razor
@inject IConfiguration Configuration
```

이 앞의 문은 `IConfiguration` 개체를 `Configuration` Razor 템플릿의 나머지 부분에서 변수로 사용할 수 있게 합니다.

개별 구성 설정은 인덱서 매개 변수로 검색되는 구성 설정 계층 구조를 지정하여 읽을 수 있습니다.

```csharp
var mySetting = Configuration["section1:key0"];
```

이전 예제에서 section1에 <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> 대한 구성을 검색하는 것과 `GetSection("section1")` 유사한 구문을 사용하여 특정 위치에서 키 컬렉션을 검색하는 메서드를 사용하여 전체 구성 섹션을 가져올 수 있습니다.

## <a name="strongly-typed-configuration"></a>강력한 형식의 구성

Web Forms를 사용하면 <xref:System.Configuration.ConfigurationSection> 형식 및 관련 형식에서 상속된 강력한 형식의 구성 형식을 만들 수 있었습니다. A를 `ConfigurationSection` 사용하면 이러한 구성 값에 대한 일부 비즈니스 규칙 및 처리를 구성할 수 있습니다.

ASP.NET Core에서 구성 값을 수신하는 클래스 계층구조를 지정할 수 있습니다. 이러한 클래스는 다음과 같은 것입니다.

* 부모 클래스에서 상속할 필요가 없습니다.
* 캡처하려는 `public` 구성 구조에 대한 속성 및 형식 참조와 일치하는 속성을 포함해야 합니다.

이전 *appsettings.json* 샘플의 경우 다음 클래스를 정의하여 값을 캡처할 수 있습니다.

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

이 클래스 계층 구조는 `Startup.ConfigureServices` 메서드에 다음 줄을 추가하여 채울 수 있습니다.

```csharp
services.Configure<MyConfig>(Configuration);
```

앱의 나머지 부분에서는 클래스에 입력 매개 변수를 `@inject` 추가하거나 유형의 `IOptions<MyConfig>` Razor 템플릿에 지시문을 추가하여 강력한 형식의 구성 설정을 받을 수 있습니다. 속성은 `IOptions<MyConfig>.Value` 구성 `MyConfig` 설정에서 채워진 값을 생성합니다.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

옵션 기능에 대한 자세한 내용은 ASP.NET 핵심 문서의 [옵션 패턴에서](/aspnet/core/fundamentals/configuration/options#options-interfaces) 확인할 수 있습니다.

>[!div class="step-by-step"]
>[이전](middleware.md)
>[다음](security-authentication-authorization.md)
