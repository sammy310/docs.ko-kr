---
title: '호환성이 손상되는 변경: 미들웨어: 사용되지 않는 것으로 표시된 데이터베이스 오류 페이지'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Middleware: 사용되지 않는 것으로 표시된 데이터베이스 오류 페이지'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f828b5e20c2a9a709d675e435caa99727aebd5b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759899"
---
# <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="cc2b5-103">미들웨어: 사용되지 않는 것으로 표시된 데이터베이스 오류 페이지</span><span class="sxs-lookup"><span data-stu-id="cc2b5-103">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="cc2b5-104">[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) 및 연결된 확장 메서드는 ASP.NET Core 5.0에서 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-104">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="cc2b5-105">미들웨어 및 확장 메서드는 ASP.NET Core 6.0에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-105">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="cc2b5-106">대신 `DatabaseDeveloperPageExceptionFilter` 및 해당 확장 메서드를 통해 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-106">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="cc2b5-107">자세한 내용은 [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987)에서 GitHub 이슈를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-107">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cc2b5-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="cc2b5-108">Version introduced</span></span>

<span data-ttu-id="cc2b5-109">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="cc2b5-109">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="cc2b5-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="cc2b5-110">Old behavior</span></span>

<span data-ttu-id="cc2b5-111">`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-111">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="cc2b5-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="cc2b5-112">New behavior</span></span>

<span data-ttu-id="cc2b5-113">`DatabaseErrorPageMiddleware` 및 연결된 확장 메서드가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-113">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cc2b5-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="cc2b5-114">Reason for change</span></span>

<span data-ttu-id="cc2b5-115">`DatabaseErrorPageMiddleware`가 [개발자 예외 페이지](/aspnet/core/fundamentals/error-handling#developer-exception-page)의 확장 가능한 API로 마이그레이션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-115">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="cc2b5-116">확장 가능한 API에 관한 자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-116">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cc2b5-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="cc2b5-117">Recommended action</span></span>

<span data-ttu-id="cc2b5-118">다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-118">Complete the following steps:</span></span>

1. <span data-ttu-id="cc2b5-119">프로젝트에서 `DatabaseErrorPageMiddleware` 사용을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-119">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="cc2b5-120">예를 들어 `Startup.Configure`에서 `UseDatabaseErrorPage` 메서드 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-120">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="cc2b5-121">개발자 예외 페이지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-121">Add the developer exception page to your project.</span></span> <span data-ttu-id="cc2b5-122">예를 들어 `Startup.Configure`에서 <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-122">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="cc2b5-123">프로젝트 파일에 [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-123">Add the [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet package to the project file.</span></span>

1. <span data-ttu-id="cc2b5-124">데이터베이스 개발자 페이지 예외 필터를 서비스 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-124">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="cc2b5-125">예를 들어 `Startup.ConfigureServices`에서 `AddDatabaseDeveloperPageExceptionFilter` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-125">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a><span data-ttu-id="cc2b5-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cc2b5-126">Affected APIs</span></span>

- [<span data-ttu-id="cc2b5-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="cc2b5-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="cc2b5-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="cc2b5-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
