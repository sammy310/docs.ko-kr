---
title: ASP.NET Core로 마이그레이션하는 경우의 배포 시나리오
description: ASP.NET에서 ASP.NET Core로 이식할 때 사용할 수 있는 배포에 대 한 다양 한 접근 방식에 대 한 개요는 side-by-side 마이그레이션과 단계별 마이그레이션을 허용 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 589acd8c66baacc3aef5833dfaa24e2dcc5c1ee5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401772"
---
# <a name="deployment-scenarios-when-migrating-to-aspnet-core"></a>ASP.NET Core로 마이그레이션하는 경우의 배포 시나리오

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

기존 ASP.NET MVC 및 Web API apps는 IIS 및 Windows에서 실행 됩니다. ASP.NET Core로 이식 하는 경우에는 규모가 많은 앱에서 단계별 또는 side-by-side 방법이 필요할 수 있습니다. 이전 장에서는 많은 .NET Framework 앱을 단계별로 ASP.NET Core 단계로 마이그레이션하기 위한 다양 한 전략을 배웠습니다. 이 장에서는 원래 앱의 일부를 마이그레이션하는 동안 프로덕션에서 원래 앱을 유지 해야 하는 경우 다양 한 배포 시나리오를 구현할 수 있는 방법을 확인할 수 있습니다.

## <a name="split-a-large-web-app"></a>대량 웹 앱 분할

현재 단일 웹 사이트의 IIS에서 호스팅되는 대량 웹 앱의 일반적인 시나리오를 살펴보겠습니다. 규모가 많은 앱 내에서 기능은 다른 경로 및/또는 디렉터리로 분할 됩니다. 앱은 MVC 뷰와 API 끝점의 조합입니다. MVC 경로에는 기능에 따라 다양 한 경로가 포함 되며, 표준 경로 템플릿을 사용 하 여 앱의 루트에서 시작 합니다 `/{controller}/{action}/{id?}` . API 끝점은 비슷한 패턴을 따르기는 하지만 모두 루트 아래에 있습니다 `/api` .

응용 프로그램 포팅 작업을 분할 하 여 MVC 기능이 나 API 기능을 먼저 ASP.NET Core로 마이그레이션해야 하는 경우 원본 사이트가 다른 위치에서 실행 중인 새 ASP.NET Core 앱과 원활 하 게 작동 하는 방법 시스템 사용자는 변경 해야 하는 경우를 제외 하 고는 마이그레이션 이전에 수행한 것과 동일한 Url을 계속 표시 해야 합니다.

다행히 IIS는 기능이 풍부한 웹 서버 이며 일정 시간 동안 발생 한 두 가지 기능은 [URL 재작성 모듈 및 응용 프로그램 요청 라우팅](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing)입니다. IIS는 이러한 기능을 사용 하 여 클라이언트 요청을 적절 한 백 엔드 웹 앱으로 라우팅하는 [역방향 프록시](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing)역할을 할 수 있습니다. IIS를 역방향 프록시로 구성 하려면 응용 프로그램 요청 라우팅 기능에서 **프록시 사용** 확인란을 선택 하 고 다음과 같이 URL 재작성 규칙을 추가 합니다.

```xml
<rule name="NetCoreProxy">
  <match url="(.*)> />
  <action type="Rewrite" url="http://servername/{R:1}" />
</rule>
```

역방향 프록시를 통해 IIS는 특정 패턴과 일치 하는 트래픽을 라우팅할 수 있으며,이는 다른 서버에서 잠재적으로 앱을 완전히 분리 합니다.

IIS는 URL 재작성 모듈 (호스트 헤더와 함께 사용)만 사용 하 여 여러 웹 사이트를 쉽게 지원할 수 있으며, 각각 다른 버전의 .NET을 실행할 수 있습니다. 규모가 많은 웹 앱은 개별 사이트의 컬렉션으로 배포 될 수 있습니다. 각 사이트는 서로 다른 IP 주소 및/또는 호스트 헤더에 응답 하거나 특정 URL 경로 (URL 재작성이 필요 하지 않음)에 응답 하는 하나 이상의 하위 응용 프로그램을 단일 웹 사이트로 배포할 수 있습니다.

> [!IMPORTANT]
> 하위 도메인은 일반적으로 상위 두 수준 이전의 도메인 부분을 나타냅니다. 예를 들어 도메인에서는 도메인의 하위 도메인입니다 `api.contoso.com` `api` `contoso.com` (자체는 `contoso` 도메인 이름과 `.com` 최상위 도메인 또는 TLD로 구성 됨). URL 경로는로 시작 하는 도메인 이름 다음에 나오는 URL의 일부를 나타냅니다 `/` . URL `https://contoso.com/api` 의 경로는입니다 `/api` .

동일한 도메인 이나 다른 하위 도메인 (및 도메인)을 사용 하 여 단일 앱을 호스트 하는 것과 같은 장단점이 있습니다. [CORS](/aspnet/core/security/cors) 와 같은 메커니즘을 사용 하는 쿠키 및 앱 내 통신의 기능에는 배포 앱에서 제대로 작동 하기 위해 더 많은 구성이 필요할 수 있습니다. 그러나 다른 하위 도메인을 사용 하는 앱은 더 쉽게 DNS를 사용 하 여 요청을 완전히 다른 네트워크 대상으로 라우팅할 수 있으므로 IIS를 역방향 프록시로 사용 하지 않고도 여러 다른 서버 (가상 또는 기타)에 쉽게 배포할 수 있습니다.

위에서 설명한 예제에서는 API 끝점이 ASP.NET Core로 이식할 앱의 첫 번째 부분으로 지정 되어 있다고 가정 합니다. 이 경우 새 ASP.NET Core 앱은 기존 ASP.NET MVC 웹 *사이트* 내에서 별도의 웹 *응용 프로그램* 으로 만들고 IIS에서 호스팅됩니다. 이 파일은 원래 웹 사이트의 자식으로 추가 되 고 명명 된 *api* 이므로 기본 경로는 더 이상로 시작 하지 않아야 합니다 `api/` . 이를 유지 하면 양식의 Url이 일치 하 게 `/api/api/endpoint` 됩니다.

그림 5-1에서는 ASP.NET Core 2.1 *api* 앱이 IIS 관리자에서 기존 *DotNetMvcApp* 사이트의 일부로 표시 되는 방법을 보여 줍니다.

![.NET Framework 사이트 내에서 api 앱을 보여 주는 IIS 관리자](./media/Figure5-1.png)

**그림 5-1**. IIS의 .NET Core 앱을 사용 하 여 사이트를 .NET Framework 합니다.

*DotNetMvcApp* 사이트는 .NET Framework 4.7.2에서 실행 되는 MVC 5 앱으로 호스팅됩니다. 통합 모드에서 구성 된 자체 IIS 응용 프로그램 풀과 .NET CLR 버전 4.0.30319을 실행 하 고 있습니다. *Api* 앱은 .NET Framework 4.6.1 ()에서 실행 되는 ASP.NET Core 앱입니다 `net461` . 새 IIS 앱으로 *DotNetMvcApp* 에 추가 되 고 자체 응용 프로그램 풀을 사용 하도록 구성 되었습니다. 응용 프로그램 풀이 통합 모드에서 실행 되 고 있지만, [ASP.NET Core 모듈](/aspnet/core/host-and-deploy/aspnet-core-module?preserve-view=true&view=aspnetcore-2.1)을 사용 하 여 실행 되기 때문에 **관리 코드가 없는** .net CLR 버전으로 구성 되어 있습니다. ASP.NET Core 앱의 버전은 예제 일 뿐입니다. 또한 .NET Core 3.1 또는 .NET 5.0에서 실행 되도록 구성할 수 있습니다. 그러나이 시점에서는 더 이상 .NET Framework 라이브러리를 대상으로 지정할 수 없습니다 ( [올바른 .Net Core 버전 선택](choose-net-core-version.md)참조).

이러한 방식으로 구성 된 ASP.NET Core 앱의 Api를 적절히 라우팅하도록 하려면 기본 경로 템플릿을에서로 변경 해야 합니다 `[Route("[api/controller]")]` `[Route("[controller]")]` .

또는 ASP.NET Core 앱은 IIS의 다른 최상위 웹 사이트 일 수 있습니다. 이 경우 경로가로 시작 하는 경우 다른 앱으로 리디렉션하는 재작성 규칙 ( [URL 재작성](https://www.iis.net/downloads/microsoft/url-rewrite)포함)을 사용 하도록 원래 사이트를 구성할 수 있습니다 `/api` . ASP.NET Core 앱은 주 앱과 충돌 하지 않지만 루트 기반 경로를 사용 하 여 요청에 응답할 수 있도록 해당 경로에 대해 다른 호스트 헤더를 사용할 수 있습니다.

예를 들어, 그림 5-1에 사용 된 것과 동일한 ASP.NET Core 앱을 IIS 웹 사이트로 구성 된 다른 폴더에 배포할 수 있습니다. 사이트는 **관리 코드 없이** 이전 처럼 구성 된 응용 프로그램 풀을 사용 해야 합니다. 서버에서 고유한 호스트 이름에 응답 하도록 바인딩을 구성 합니다 (예:) `api.contoso.com` . URL 다시 쓰기를 구성 하 여 요청을 다시 작성 하려면 `/api` IIS 서버 (또는 개별 사이트) 수준에서 새 인바운드 규칙을 추가 하면 됩니다. 패턴을 일치 `^/api(.*)` 시키고의 동작 유형과의 `Rewrite` 재작성 URL을 지정 `api.contoso.com/{R:1}` 합니다. `(.*)`일치 패턴 및 재작성 URL에서를 사용 하면 `{R:1}` 나머지 경로가 새 URL에 사용 됩니다. 이를 위해 동일한 IIS 서버의 개별 사이트는 별도의 .NET 버전을 실행할 수 있지만 하나의 웹 앱으로 인터넷에 표시 되도록 설정할 수 있습니다. 그림 5-2에서는 별도의 웹 사이트를 사용 하 여 IIS에서 구성 된 재작성 규칙을 보여 줍니다.

![개별 웹 사이트에 하위 폴더 요청을 라우팅하는 URL 다시 쓰기 규칙을 보여 주는 IIS 관리자](./media/Figure5-2.png)

**그림 5-2**. 하위 폴더 요청을 다른 웹 사이트에 다시 작성 하는 규칙을 다시 작성 합니다.

앱에서 IIS 내의 서로 다른 사이트나 앱 간에 Single Sign-On 필요한 경우이 시나리오를 지 원하는 방법에 대 한 자세한 지침은 [ASP.NET apps 간에 인증 쿠키를 공유 하는 방법](/aspnet/core/host-and-deploy/iis/) 에 대 한 설명서를 참조 하세요.

## <a name="summary"></a>요약

.NET Framework에서 ASP.NET Core로 대량 앱을 이식 하는 일반적인 방법은 앱의 개별 부분을 선택 하 여 하나씩 마이그레이션하는 것입니다. 앱의 각 부분이 이식 될 때 전체 앱은 원래 구성에서 실행 되는 일부와 일부 버전의 .NET Core에서 실행 되는 다른 파트와 함께 실행 중이 고 사용 가능한 상태로 유지 됩니다. 이 방법에 따라 큰 앱 마이그레이션은 증분 방식으로 수행할 수 있습니다. 이러한 접근 방식을 통해 보다 신속한 피드백을 제공 하 고 테스트와 관련 된 전체 노출 영역을 줄여 위험을 제한 합니다. 또한 성능 향상과 같은 .NET Core의 이점에 대 한 보다 신속한 실현을 허용 합니다. ASP.NET Core 앱은 더 이상 IIS에서 호스팅될 필요가 없지만 IIS는 동일한 IIS 인스턴스에서 .NET Framework 및 ASP.NET Core 앱을 모두 포함 하거나 다른 서버에서 호스트 되는 다양 한 호스팅 시나리오를 지원 하도록 구성할 수 있는 매우 유연 하 고 강력한 웹 서버를 유지 합니다.

## <a name="references"></a>참조

- [IIS가 있는 Windows에서 ASP.NET Core 호스팅](/aspnet/core/host-and-deploy/iis/)
- [URL 재작성 모듈 및 응용 프로그램 요청 라우팅](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing)
- [URL 재작성](https://www.iis.net/downloads/microsoft/url-rewrite)
- [ASP.NET Core 모듈](/aspnet/core/host-and-deploy/aspnet-core-module?preserve-view=true&view=aspnetcore-2.1)
- [ASP.NET apps 간에 인증 쿠키 공유](/aspnet/core/host-and-deploy/iis/)
- [이 섹션에서 사용 되는 샘플](https://github.com/ardalis/MigrateDotNetWithIIS)

>[!div class="step-by-step"]
>[이전](more-migration-scenarios.md)
>[다음](summary.md)
