---
title: '호환성이 손상되는 변경: 미들웨어: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 관해 알아보기. Middleware: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw'
author: scottaddie
ms.author: scaddie
ms.date: 02/04/2021
ms.openlocfilehash: 1f49e0df7eaa2eecd83643c9596e745109a340b7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488236"
---
# <a name="middleware-https-redirection-middleware-throws-exception-on-ambiguous-https-ports"></a><span data-ttu-id="06777-103">미들웨어: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw</span><span class="sxs-lookup"><span data-stu-id="06777-103">Middleware: HTTPS Redirection Middleware throws exception on ambiguous HTTPS ports</span></span>

<span data-ttu-id="06777-104">ASP.NET Core 6.0에서 [HTTPS 리디렉션 미들웨어](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A)는 서버 구성에서 여러 HTTPS 포트를 찾을 경우 <xref:System.InvalidOperationException> 형식의 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-104">In ASP.NET Core 6.0, the [HTTPS Redirection Middleware](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A) throws an exception of type <xref:System.InvalidOperationException> when it finds multiple HTTPS ports in the server configuration.</span></span> <span data-ttu-id="06777-105">예외 메시지에는 “IServerAddressesFeature에서 HTTPS 포트를 확인할 수 없습니다. 값이 여러 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06777-105">The exception's message contains the text "Cannot determine the https port from IServerAddressesFeature, multiple values were found.</span></span> <span data-ttu-id="06777-106">HttpsRedirectionOptions.HttpsPort에서 원하는 포트를 명시적으로 설정합니다.”라는 텍스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="06777-106">Set the desired port explicitly on HttpsRedirectionOptions.HttpsPort."</span></span>

<span data-ttu-id="06777-107">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#29222](https://github.com/dotnet/aspnetcore/issues/29222)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06777-107">For discussion, see GitHub issue [dotnet/aspnetcore#29222](https://github.com/dotnet/aspnetcore/issues/29222).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="06777-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="06777-108">Version introduced</span></span>

<span data-ttu-id="06777-109">6.0</span><span class="sxs-lookup"><span data-stu-id="06777-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="06777-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="06777-110">Old behavior</span></span>

<span data-ttu-id="06777-111">HTTPS 리디렉션 미들웨어는 포트를 사용하여 명시적으로 구성되지 않은 경우 첫 번째 요청 중에 <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature>를 검색하여 리디렉션해야 하는 HTTPS 포트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-111">When the HTTPS Redirection Middleware isn't explicitly configured with a port, it searches <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature> during the first request to determine the HTTPS port to which it should redirect.</span></span>

<span data-ttu-id="06777-112">HTTPS 포트가 없거나 여러 개별 포트가 있으면 사용해야 하는 포트가 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06777-112">If there are no HTTPS ports or multiple distinct ports, it's unclear which port should be used.</span></span> <span data-ttu-id="06777-113">미들웨어는 경고를 로그하며 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06777-113">The middleware logs a warning and disables itself.</span></span> <span data-ttu-id="06777-114">HTTP 요청은 정상적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="06777-114">HTTP requests are processed normally.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="06777-115">새 동작</span><span class="sxs-lookup"><span data-stu-id="06777-115">New behavior</span></span>

<span data-ttu-id="06777-116">HTTPS 리디렉션 미들웨어는 포트를 사용하여 명시적으로 구성되지 않은 경우 첫 번째 요청 중에 `IServerAddressesFeature`를 검색하여 리디렉션해야 하는 HTTPS 포트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-116">When the HTTPS Redirection Middleware isn't explicitly configured with a port, it searches `IServerAddressesFeature` during the first request to determine the HTTPS port to which it should redirect.</span></span>

<span data-ttu-id="06777-117">HTTPS 포트가 없어도 미들웨어는 여전히 경고를 로그하며 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06777-117">If there are no HTTPS ports, the middleware still logs a warning and disables itself.</span></span> <span data-ttu-id="06777-118">HTTP 요청은 정상적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="06777-118">HTTP requests are processed normally.</span></span> <span data-ttu-id="06777-119">이 동작은 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-119">This behavior supports:</span></span>

* <span data-ttu-id="06777-120">HTTPS를 사용하지 않는 개발 시나리오.</span><span class="sxs-lookup"><span data-stu-id="06777-120">Development scenarios without HTTPS.</span></span>
* <span data-ttu-id="06777-121">서버에 도달하기 전에 TLS가 종료되는 호스티드 시나리오.</span><span class="sxs-lookup"><span data-stu-id="06777-121">Hosted scenarios in which TLS is terminated before reaching the server.</span></span>

<span data-ttu-id="06777-122">여러 개별 포트가 있는 경우 사용해야 하는 포트가 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06777-122">If there are multiple distinct ports, it's unclear which port should be used.</span></span> <span data-ttu-id="06777-123">미들웨어는 예외를 throw하고 HTTP 요청에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-123">The middleware throws an exception and fails the HTTP request.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="06777-124">변경 이유</span><span class="sxs-lookup"><span data-stu-id="06777-124">Reason for change</span></span>

<span data-ttu-id="06777-125">이 변경은 HTTPS가 사용 가능한 것으로 알려진 경우 암호화되지 않은 HTTP 연결을 통해 잠재적으로 중요한 데이터가 제공되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-125">This change prevents potentially sensitive data from being served over unencrypted HTTP connections when HTTPS is known to be available.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="06777-126">권장 조치</span><span class="sxs-lookup"><span data-stu-id="06777-126">Recommended action</span></span>

<span data-ttu-id="06777-127">서버에 여러 개별 HTTPS 포트가 있을 때 HTTPS 리디렉션을 사용하도록 설정하려면 구성에서 하나의 포트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-127">To enable HTTPS redirection when the server has multiple distinct HTTPS ports, you must specify one port in the configuration.</span></span> <span data-ttu-id="06777-128">자세한 내용은 [포트 구성](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06777-128">For more information, see [Port configuration](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration).</span></span>

<span data-ttu-id="06777-129">앱에서 HTTPS 리디렉션 미들웨어가 필요하지 않은 경우 *Startup.cs* 에서 `UseHttpsRedirection`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-129">If you don't need the HTTPS Redirection Middleware in your app, remove `UseHttpsRedirection` from *Startup.cs*.</span></span>

<span data-ttu-id="06777-130">올바른 HTTPS 포트를 동적으로 선택해야 하는 경우 GitHub 이슈 [dotnet/aspnetcore#21291](https://github.com/dotnet/aspnetcore/issues/21291)에서 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06777-130">If you need to select the correct HTTPS port dynamically, provide feedback in GitHub issue [dotnet/aspnetcore#21291](https://github.com/dotnet/aspnetcore/issues/21291).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="06777-131">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="06777-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection`

-->
