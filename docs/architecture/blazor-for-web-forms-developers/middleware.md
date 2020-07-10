---
title: 모듈, 처리기 및 미들웨어
description: 모듈, 처리기 및 미들웨어를 사용 하 여 HTTP 요청을 처리 하는 방법을 알아봅니다.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: ff2b3fd41316a1c8c20a0eed9a585e5fd2733af3
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173187"
---
# <a name="modules-handlers-and-middleware"></a>모듈, 처리기 및 미들웨어

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Core 앱은 일련의 *미들웨어*를 기반으로 빌드됩니다. 미들웨어는 요청 및 응답을 처리 하기 위해 파이프라인으로 정렬 되는 처리기입니다. Web Forms 앱에서 HTTP 처리기와 모듈은 유사한 문제를 해결 합니다. ASP.NET Core 모듈, 처리기, *Global.asax.cs*및 앱 수명 주기가 미들웨어로 바뀝니다. 이 장에서는 앱의 컨텍스트에서 미들웨어에 대해 알아봅니다 Blazor .

## <a name="overview"></a>개요

ASP.NET Core 요청 파이프라인은 하나씩 차례로 호출되는 요청 대리자 시퀀스로 구성됩니다. 다음 다이어그램은 그 개념을 보여줍니다. 실행 스레드는 검은색 화살표를 따릅니다.

![pipeline](media/middleware/request-delegate-pipeline.png)

이전 다이어그램에는 수명 주기 이벤트 개념이 없습니다. 이 개념은 ASP.NET Web Forms 요청이 처리 되는 방식에 기초 합니다. 이 시스템을 사용 하면 발생 하는 프로세스를 보다 쉽게 파악할 수 있으며 미들웨어를 언제 든 지 삽입할 수 있습니다. 미들웨어는 요청 파이프라인에 추가 된 순서 대로 실행 됩니다. 일반적으로 *Startup.cs*에서 구성 파일 대신 코드에 추가 됩니다.

## <a name="katana"></a>Katana

Katana에 익숙한 독자는 ASP.NET Core에 익숙해질 것입니다. 실제로 Katana는 ASP.NET Core 파생 되는 프레임 워크입니다. ASP.NET 4.x에 대해 비슷한 미들웨어 및 파이프라인 패턴이 도입 되었습니다. Katana 용으로 설계 된 미들웨어는 ASP.NET Core 파이프라인을 사용 하도록 조정할 수 있습니다.

## <a name="common-middleware"></a>일반적인 미들웨어

ASP.NET 4.x에는 많은 모듈이 포함 되어 있습니다. 마찬가지로 ASP.NET Core에도 많은 미들웨어 구성 요소가 제공 됩니다. IIS 모듈은 일부 경우에 ASP.NET Core 사용할 수 있습니다. 다른 경우에는 네이티브 ASP.NET Core 미들웨어를 사용할 수 있습니다.

다음 표에서는 ASP.NET Core의 대체 미들웨어 및 구성 요소를 보여 줍니다.

|모듈                 |ASP.NET 4.x 모듈           |ASP.NET Core 옵션|
|-----------------------|-----------------------------|-------------------|
|HTTP 오류            |`CustomErrorModule`          |[상태 코드 페이지 미들웨어](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|기본 문서       |`DefaultDocumentModule`      |[기본 파일 미들웨어](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|디렉터리 검색     |`DirectoryListingModule`     |[디렉터리 검색 미들웨어](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|동적 압축    |`DynamicCompressionModule`   |[응답 압축 미들웨어](/aspnet/core/performance/response-compression)|
|실패 한 요청 추적|`FailedRequestsTracingModule`|[ASP.NET Core 로깅](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|파일 캐싱           |`FileCacheModule`            |[응답 캐싱 미들웨어](/aspnet/core/performance/caching/middleware)|
|HTTP 캐싱           |`HttpCacheModule`            |[응답 캐싱 미들웨어](/aspnet/core/performance/caching/middleware)|
|HTTP 로깅           |`HttpLoggingModule`          |[ASP.NET Core 로깅](/aspnet/core/fundamentals/logging/index)|
|HTTP 리디렉션       |`HttpRedirectionModule`      |[URL 재작성 미들웨어](/aspnet/core/fundamentals/url-rewriting)|
|ISAPI 필터          |`IsapiFilterModule`          |[미들웨어](/aspnet/core/fundamentals/middleware/index)|
|ISAPI                  |`IsapiModule`                |[미들웨어](/aspnet/core/fundamentals/middleware/index)|
|요청 필터링      |`RequestFilteringModule`     |[URL 재작성 미들웨어 IRule](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|URL 재작성&#8224;   |`RewriteModule`              |[URL 재작성 미들웨어](/aspnet/core/fundamentals/url-rewriting)|
|정적 압축     |`StaticCompressionModule`    |[응답 압축 미들웨어](/aspnet/core/performance/response-compression)|
|정적 콘텐츠         |`StaticFileModule`           |[정적 파일 미들웨어](/aspnet/core/fundamentals/static-files)|
|URL 권한 부여      |`UrlAuthorizationModule`     |[ASP.NET Core ID](/aspnet/core/security/authentication/identity)|

이 목록은 완전 하지는 않지만 두 프레임 워크 사이에 존재 하는 매핑에 대해 아이디어를 제공 해야 합니다. 자세한 목록은 [ASP.NET Core를 사용 하는 IIS 모듈](/aspnet/core/host-and-deploy/iis/modules)을 참조 하세요.

## <a name="custom-middleware"></a>사용자 지정 미들웨어

기본 제공 미들웨어는 앱에 필요한 모든 시나리오를 처리 하지 못할 수 있습니다. 이러한 경우 고유한 미들웨어를 만드는 것이 좋습니다. 미들웨어를 정의 하는 방법에는 여러 가지가 있으며 간단한 대리자가 가장 간단 합니다. 쿼리 문자열에서 문화권 요청을 수락 하는 다음 미들웨어를 고려 합니다.

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

미들웨어는 인터페이스를 구현 하거나 미들웨어 규칙을 따라 클래스로 정의할 수도 있습니다 `IMiddleware` . 자세한 내용은 [사용자 지정 ASP.NET Core 미들웨어 작성](/aspnet/core/fundamentals/middleware/write)을 참조 하세요.

>[!div class="step-by-step"]
>[이전](data.md)
>[다음](config.md)
