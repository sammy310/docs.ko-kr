---
title: ASP.NET MVC와 ASP.NET Core 간의 구성 차이점
description: 구성 값이 저장 되 고 ASP.NET와 ASP.NET Core 간에 읽기가 크게 변경 되는 방식입니다. 이 섹션에서는 ASP.NET에서 ASP.NET Core로 구성을 마이그레이션하는 방법 및 세부 정보를 검토 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 1e8e4d4ac408862f0216a5744476047186222304
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401789"
---
# <a name="configuration-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 구성 차이점

구성 값이 저장 되 고 ASP.NET와 ASP.NET Core 간에 읽기가 크게 변경 되는 방식입니다.

## <a name="aspnet-mvc-configuration"></a>ASP.NET MVC 구성

ASP.NET apps에서 구성은 기본 제공 .NET 구성 파일을 사용 하 고, 앱 폴더에서 *web.config* 하 고, 서버의 *machine.config* 를 사용 합니다. 대부분의 ASP.NET MVC 및 Web API apps는 해당 설정을 구성 파일의 `appSettings` 또는 요소에 저장 `connectionStrings` 합니다. 또한 settings 클래스에 매핑할 수 있는 사용자 지정 구성 섹션을 사용 합니다.

.NET Framework 앱의 구성은 클래스를 사용 하 여 액세스할 수 `System.Configuration.ConfigurationManager` 있습니다. 아쉽게도이 클래스는 구성 요소에 대 한 정적 액세스를 제공 합니다. 결과적으로, ASP.NET MVC 앱은 구성 설정에 대 한 액세스를 추상화 하거나 필요한 경우 삽입 하는 경향이 있습니다. 대신 대부분의 .NET Framework 앱은 앱에서 설정을 사용 해야 하는 모든 곳에서 구성 시스템에 직접 액세스 하는 경향이 있습니다.

일반적인 ASP.NET MVC 구성 액세스:

```csharp
string connectionString =
    ConfigurationManager.ConnectionStrings["DefaultConnection"]
        .ConnectionString;
```

## <a name="aspnet-core-configuration"></a>ASP.NET Core 구성

ASP.NET Core 앱에서 구성은 자체 구성 가능 합니다. 그러나 대부분의 앱은 표준 프로젝트 템플릿의 일부로 제공 되는 기본값 집합과 `ConfigureWebHostDefaults` 여기에 사용 되는 메서드를 사용 합니다. 기본 설정에는 JSON 형식의 파일이 사용 되며, *appsettings.Development.js* 와 같은 환경 특정 파일을 사용 하 여 파일 *에 대 한 기본appsettings.js* 설정을 재정의할 수 있습니다. 또한 기본 구성 시스템은 동일한 명명 된 설정에 대해 존재 하는 환경 변수를 사용 하 여 모든 파일 기반 설정을 추가로 재정의 합니다. 이는 많은 시나리오에서 유용 하며, 호스팅 환경에 배포할 때 특히 유용 합니다. 구성 파일을 배포할 때 중요 한 프로덕션 구성 설정을 실수로 덮어쓸지 여부를 걱정 하지 않아도 되기 때문입니다. 구성 값은 명령줄 인수로 제공 될 수도 있습니다.

.NET Core에서 구성 값에 액세스 하는 것은 여러 가지 방법으로 수행할 수 있습니다. 종속성 주입은 .NET Core에 기본 제공 되므로 일반적으로이를 필요로 하는 클래스에 삽입 되는 인터페이스를 통해 구성 값에 액세스 합니다. 여기에는와 같은 인터페이스를 전달 하는 작업이 포함 될 수 <xref:Microsoft.Extensions.Configuration.IConfiguration> 있지만 일반적으로 [옵션 패턴](/aspnet/core/fundamentals/configuration/options)을 사용 하 여 클래스에 필요한 설정만 전달 하는 것이 좋습니다.

그림 2-2에서는 `IConfiguration` Razor 페이지에 전달 하 고 여기에서 구성 설정에 액세스 하는 방법을 보여 줍니다.

```csharp
using Microsoft.Extensions.Configuration;

public class TestModel : PageModel
{
    private readonly IConfiguration _configuration;

    public TestModel(IConfiguration configuration)
    {
        _configuration= configuration;
    }

    public ContentResult OnGet()
    {
        var myKeyValue = _configuration["MyKey"];

        // ...
    }
}
```

**그림 2-2.** 를 사용 하 여 구성 값에 액세스 `IConfiguration` 합니다.

옵션 패턴을 사용 하는 설정 액세스는 유사 하지만, 그림 2-3에서 보여 주는 것 처럼 사용 하는 클래스에 필요한 설정에 대 한 보다 구체적이 고 강력 하 게 형식화 됩니다.

```csharp
public class PositionOptions
{
    public const string Position = nameof(Position);

    public string Title { get; set; }
    public string Name { get; set; }
}

public class Test2Model : PageModel
{
    private readonly PositionOptions _options;

    public Test2Model(IOptions<PositionOptions> options)
    {
        _options = options.Value;
    }

    public ContentResult OnGet()
    {
        return Content($"Title: {_options.Title}\nName: {_options.Name}");
    }
}
```

**그림 2-3.** ASP.NET Core에서 옵션 패턴을 사용 합니다.

옵션 패턴이 작동 하려면 `ConfigureServices` 앱이 시작 될 때에서 옵션 유형을 구성 해야 합니다.

```csharp
// required in ConfigureServices
services.Configure<PositionOptions>(Configuration.GetSection(PositionOptions.Position));
```

## <a name="migrate-configuration"></a>구성 마이그레이션

앱의 구성 설정을 .NET Framework에서 .NET Core로 이식 하는 방법을 고려할 때 첫 번째 단계는 사용 중인 모든 구성 설정을 확인 하는 것입니다. 이러한 파일의 대부분은 앱의 루트 폴더에 있는 *web.config* 파일에 있지만, 일부 앱은 공유 *machine.config* 파일 에서도 설정을 찾을 것으로 요구 합니다.

구성 파일의 모든 설정이 카탈로그로 된 후 다음 단계는 앱 자체에서 설정을 사용 하는 위치와 방법을 식별 하는 것입니다. 일부 설정을 사용 하지 않는 경우 마이그레이션에서 생략 될 수 있습니다. 각 설정에 대해 사용 되는 모든 위치를 확인 하 여 코드를 마이그레이션할 때 누락 되지 않도록 합니다.

ASP.NET 앱을 계속 유지 관리 하는 경우에 대 한 정적 참조를 방지 하 `ConfigurationManager` 고 인터페이스를 통해 액세스로 바꾸는 것이 유용할 수 있습니다. 이렇게 하면 ASP.NET Core의 구성 시스템으로 쉽게 전환할 수 있습니다. 일반적으로 외부 리소스에 대 한 정적 액세스를 사용 하면 코드를 테스트 하 고 유지 관리 하는 데 어려움이 있으므로 응용 프로그램이이 패턴을 준수할 수 있습니다.

## <a name="references"></a>참조

- [ASP.NET Core의 구성](/aspnet/core/fundamentals/configuration/)
- [ASP.NET Core의 옵션 패턴](/aspnet/core/fundamentals/configuration/options)
- [구성을 ASP.NET Core로 마이그레이션](/aspnet/core/migration/configuration)
- [정적 구성 액세스 리팩터링](https://ardalis.com/refactoring-static-config-access/)

>[!div class="step-by-step"]
>[이전](middleware-modules-handlers.md)
>[다음](routing-differences.md)
