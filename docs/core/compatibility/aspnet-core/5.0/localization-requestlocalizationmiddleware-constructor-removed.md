---
title: '호환성이 손상되는 변경: 지역화: 요청 지역화 미들웨어에서 사용되지 않는 생성자가 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 지역화: 요청 지역화 미들웨어에서 사용되지 않는 생성자가 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759959"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a>지역화: 요청 지역화 미들웨어에서 사용되지 않는 생성자가 제거됨

<xref:Microsoft.Extensions.Logging.ILoggerFactory> 매개 변수가 없는 <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> 생성자는 [이 커밋](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0)에서 사용되지 않는 것으로 표시되었습니다. ASP.NET Core 5.0에서 사용되지 않는 생성자는 제거되었습니다. 자세한 내용은 [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

## <a name="old-behavior"></a>이전 동작

사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 있습니다.

## <a name="new-behavior"></a>새 동작

사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 없습니다.

## <a name="reason-for-change"></a>변경 이유

이렇게 변경하면 요청 지역화 미들웨어가 로거에 항상 액세스할 수 있습니다.

## <a name="recommended-action"></a>권장 조치

`RequestLocalizationMiddleware` 인스턴스를 수동으로 생성하는 경우 생성자를 통해 `ILoggerFactory` 인스턴스를 전달합니다. 해당 컨텍스트에서 유효한 `ILoggerFactory` 인스턴스를 사용할 수 없는 경우 미들웨어 생성자에 <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> 인스턴스를 전달하는 것이 좋습니다.

## <a name="affected-apis"></a>영향을 받는 API

[RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
