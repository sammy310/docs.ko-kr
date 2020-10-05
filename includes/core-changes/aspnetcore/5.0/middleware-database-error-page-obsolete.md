---
ms.openlocfilehash: 10521759d31c3183232cdb1793d78d139f13ce41
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077568"
---
### <a name="middleware-database-error-page-marked-as-obsolete"></a>미들웨어: 사용되지 않는 것으로 표시된 데이터베이스 오류 페이지

[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) 및 연결된 확장 메서드는 ASP.NET Core 5.0에서 사용되지 않는 것으로 표시되었습니다. 미들웨어 및 확장 메서드는 ASP.NET Core 6.0에서 제거될 예정입니다. 대신 `DatabaseDeveloperPageExceptionFilter` 및 해당 확장 메서드를 통해 기능을 제공합니다.

자세한 내용은 [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987)에서 GitHub 이슈를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 RC 1

#### <a name="old-behavior"></a>이전 동작

`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되었습니다.

#### <a name="new-behavior"></a>새 동작

`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

`DatabaseErrorPageMiddleware`가 [개발자 예외 페이지](/aspnet/core/fundamentals/error-handling#developer-exception-page)의 확장 가능한 API로 마이그레이션되었습니다. 확장 가능한 API에 관한 자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536)을 참조하세요.

#### <a name="recommended-action"></a>권장 조치

다음 단계를 완료합니다.

1. 프로젝트에서 `DatabaseErrorPageMiddleware` 사용을 중지합니다. 예를 들어 `Startup.Configure`에서 `UseDatabaseErrorPage` 메서드 호출을 제거합니다.

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. 개발자 예외 페이지를 프로젝트에 추가합니다. 예를 들어 `Startup.Configure`에서 <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> 메서드를 호출합니다.

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. 프로젝트 파일에 [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet 패키지를 추가합니다.

1. 데이터베이스 개발자 페이지 예외 필터를 서비스 컬렉션에 추가합니다. 예를 들어 `Startup.ConfigureServices`에서 `AddDatabaseDeveloperPageExceptionFilter` 메서드를 호출합니다.

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- [Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!-- 

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
