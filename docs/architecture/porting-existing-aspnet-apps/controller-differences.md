---
title: ASP.NET MVC 및 ASP.NET Core의 컨트롤러 비교
description: ASP.NET Core MVC 컨트롤러는 ASP.NET MVC 5 및 Web API 2 컨트롤러와 유사 하지만 중요 한 차이점이 있습니다. 이 섹션에서는 ASP.NET MVC 및 Web API 2에서 ASP.NET Core로 앱을 이식 하는 데 필요한 차이점 및 단계를 검토 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 2c2b7b848162a6ab9901ac9f7779787e2cc994ce
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401783"
---
# <a name="compare-controllers-in-aspnet-mvc-and-web-api-with-controllers-in-aspnet-core"></a>ASP.NET MVC 및 Web API의 컨트롤러와 ASP.NET Core의 컨트롤러 비교

ASP.NET MVC 5 및 Web API 2에는 두 가지 `Controller` 기본 형식이 있습니다. 에서 상속 된 MVC 컨트롤러 `Controller` 에서 상속 된 Web API 컨트롤러 `ApiController` 입니다. ASP.NET Core에서이 개체 계층이 병합 되었습니다. ASP.NET Core의 API 컨트롤러는에서 상속 되 `ControllerBase` 고 특성을 추가 하는 것이 좋습니다 `[ApiController]` . 표준 뷰 기반 MVC 컨트롤러는에서 상속 해야 합니다 `Controller` .

두 프레임 워크에서 컨트롤러는 작업 메서드 집합을 구성 하는 데 사용 됩니다. 필터 및 경로는 작업 수준 뿐만 아니라 컨트롤러 수준에도 적용 될 수 있습니다. `Controller`기본 동작 및 특성이 적용 된 사용자 지정 기본 형식을 사용 하 여 이러한 규칙을 추가로 확장할 수 있습니다.

ASP.NET MVC에서는 콘텐츠 협상이 지원 되지 않습니다. ASP.NET Web API 2는 ASP.NET Core와 같이 콘텐츠 협상을 지원 합니다. 콘텐츠 [협상](/aspnet/core/web-api/advanced/formatting)을 사용 하 여 요청에 반환 되는 콘텐츠의 형식은 클라이언트에서 콘텐츠를 받는 기본 방법을 나타내는 헤더에 의해 결정 될 수 있습니다.

ASP.NET Web API 컨트롤러를 ASP.NET Core으로 마이그레이션하는 경우 몇 가지 구성 요소가 있는 경우 변경 해야 합니다. 여기에는 `ApiController` 기본 클래스, `System.Web.Http` 네임 스페이스 및 인터페이스에 대 한 참조가 포함 됩니다 `IHttpActionResult` . [이러한 특정 차이점을 마이그레이션하는 방법에 대 한 권장 사항은 설명서](/aspnet/core/migration/webapi)를 참조 하세요. ASP.NET Core의 API 작업에 대 한 기본 반환 형식은 `ActionResult<T>` 입니다.

또한 `[ChildActionOnly]` 특성은 ASP.NET Core에서 지원 되지 않습니다. ASP.NET Core [보기 구성 요소](/aspnet/core/mvc/views/view-components)를 사용 하 여 비슷한 기능을 얻을 수 있습니다.

ASP.NET Core에는 두 가지 새로운 특성인 [ConsumesAttribute](/dotnet/api/microsoft.aspnetcore.mvc.consumesattribute) 및 [ProducesAttribute](/dotnet/api/microsoft.aspnetcore.mvc.producesattribute)가 포함 됩니다. 이러한 기능은 작업에서 사용 하거나 생성 하는 형식을 지정 하는 데 사용 됩니다 .이는 [Swagger/OpenAPI](/aspnet/core/tutorials/web-api-help-pages-using-swagger)와 같은 도구를 사용 하 여 API를 라우팅 하 고 문서화 하는 데 유용할 수 있습니다.

## <a name="references"></a>참조

- [ASP.NET Core Web API에서 응답 데이터 서식 지정](/aspnet/core/web-api/advanced/formatting)
- [ASP.NET Web API에서 ASP.NET Core로 마이그레이션](/aspnet/core/migration/webapi)

>[!div class="step-by-step"]
>[이전](identity-differences.md)
>[다음](razor-differences.md)
