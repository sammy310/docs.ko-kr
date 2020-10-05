---
ms.openlocfilehash: 10521759d31c3183232cdb1793d78d139f13ce41
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077568"
---
### <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="280a6-101">미들웨어: 사용되지 않는 것으로 표시된 데이터베이스 오류 페이지</span><span class="sxs-lookup"><span data-stu-id="280a6-101">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="280a6-102">[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) 및 연결된 확장 메서드는 ASP.NET Core 5.0에서 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-102">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="280a6-103">미들웨어 및 확장 메서드는 ASP.NET Core 6.0에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-103">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="280a6-104">대신 `DatabaseDeveloperPageExceptionFilter` 및 해당 확장 메서드를 통해 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-104">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="280a6-105">자세한 내용은 [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987)에서 GitHub 이슈를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="280a6-105">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="280a6-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="280a6-106">Version introduced</span></span>

<span data-ttu-id="280a6-107">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="280a6-107">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="280a6-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="280a6-108">Old behavior</span></span>

<span data-ttu-id="280a6-109">`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-109">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="280a6-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="280a6-110">New behavior</span></span>

<span data-ttu-id="280a6-111">`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-111">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="280a6-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="280a6-112">Reason for change</span></span>

<span data-ttu-id="280a6-113">`DatabaseErrorPageMiddleware`가 [개발자 예외 페이지](/aspnet/core/fundamentals/error-handling#developer-exception-page)의 확장 가능한 API로 마이그레이션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-113">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="280a6-114">확장 가능한 API에 관한 자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="280a6-114">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="280a6-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="280a6-115">Recommended action</span></span>

<span data-ttu-id="280a6-116">다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-116">Complete the following steps:</span></span>

1. <span data-ttu-id="280a6-117">프로젝트에서 `DatabaseErrorPageMiddleware` 사용을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-117">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="280a6-118">예를 들어 `Startup.Configure`에서 `UseDatabaseErrorPage` 메서드 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-118">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="280a6-119">개발자 예외 페이지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-119">Add the developer exception page to your project.</span></span> <span data-ttu-id="280a6-120">예를 들어 `Startup.Configure`에서 <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-120">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="280a6-121">프로젝트 파일에 [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-121">Add the [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet package to the project file.</span></span>

1. <span data-ttu-id="280a6-122">데이터베이스 개발자 페이지 예외 필터를 서비스 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-122">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="280a6-123">예를 들어 `Startup.ConfigureServices`에서 `AddDatabaseDeveloperPageExceptionFilter` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="280a6-123">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

#### <a name="category"></a><span data-ttu-id="280a6-124">범주</span><span class="sxs-lookup"><span data-stu-id="280a6-124">Category</span></span>

<span data-ttu-id="280a6-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="280a6-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="280a6-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="280a6-126">Affected APIs</span></span>

- [<span data-ttu-id="280a6-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="280a6-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="280a6-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="280a6-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!-- 

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
