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
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="17e03-103">지역화: 요청 지역화 미들웨어에서 사용되지 않는 생성자가 제거됨</span><span class="sxs-lookup"><span data-stu-id="17e03-103">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="17e03-104"><xref:Microsoft.Extensions.Logging.ILoggerFactory> 매개 변수가 없는 <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> 생성자는 [이 커밋](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0)에서 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-104">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="17e03-105">ASP.NET Core 5.0에서 사용되지 않는 생성자는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-105">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="17e03-106">자세한 내용은 [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17e03-106">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="17e03-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="17e03-107">Version introduced</span></span>

<span data-ttu-id="17e03-108">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="17e03-108">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="17e03-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="17e03-109">Old behavior</span></span>

<span data-ttu-id="17e03-110">사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="17e03-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="17e03-111">New behavior</span></span>

<span data-ttu-id="17e03-112">사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-112">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="17e03-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="17e03-113">Reason for change</span></span>

<span data-ttu-id="17e03-114">이렇게 변경하면 요청 지역화 미들웨어가 로거에 항상 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-114">This change ensures that the request localization middleware always has access to a logger.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="17e03-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="17e03-115">Recommended action</span></span>

<span data-ttu-id="17e03-116">`RequestLocalizationMiddleware` 인스턴스를 수동으로 생성하는 경우 생성자를 통해 `ILoggerFactory` 인스턴스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-116">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="17e03-117">해당 컨텍스트에서 유효한 `ILoggerFactory` 인스턴스를 사용할 수 없는 경우 미들웨어 생성자에 <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> 인스턴스를 전달하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="17e03-117">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="17e03-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="17e03-118">Affected APIs</span></span>

[<span data-ttu-id="17e03-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="17e03-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
