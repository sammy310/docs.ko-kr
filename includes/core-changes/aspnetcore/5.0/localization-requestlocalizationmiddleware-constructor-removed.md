---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309159"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="9c301-101">지역화: 요청 지역화 미들웨어에서 사용되지 않는 생성자가 제거됨</span><span class="sxs-lookup"><span data-stu-id="9c301-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="9c301-102"><xref:Microsoft.Extensions.Logging.ILoggerFactory> 매개 변수가 없는 <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> 생성자는 [이 커밋](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0)에서 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="9c301-103">ASP.NET Core 5.0에서 사용되지 않는 생성자는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="9c301-104">자세한 내용은 [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c301-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9c301-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="9c301-105">Version introduced</span></span>

<span data-ttu-id="9c301-106">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="9c301-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9c301-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="9c301-107">Old behavior</span></span>

<span data-ttu-id="9c301-108">사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9c301-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="9c301-109">New behavior</span></span>

<span data-ttu-id="9c301-110">사용되지 않는 `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9c301-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="9c301-111">Reason for change</span></span>

<span data-ttu-id="9c301-112">이렇게 변경하면 요청 지역화 미들웨어가 로거에 항상 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9c301-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="9c301-113">Recommended action</span></span>

<span data-ttu-id="9c301-114">`RequestLocalizationMiddleware` 인스턴스를 수동으로 생성하는 경우 생성자를 통해 `ILoggerFactory` 인스턴스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="9c301-115">해당 컨텍스트에서 유효한 `ILoggerFactory` 인스턴스를 사용할 수 없는 경우 미들웨어 생성자에 <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> 인스턴스를 전달하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c301-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="9c301-116">범주</span><span class="sxs-lookup"><span data-stu-id="9c301-116">Category</span></span>

<span data-ttu-id="9c301-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c301-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9c301-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9c301-118">Affected APIs</span></span>

[<span data-ttu-id="9c301-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="9c301-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
