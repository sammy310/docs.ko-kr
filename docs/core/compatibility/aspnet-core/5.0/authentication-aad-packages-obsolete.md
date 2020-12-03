---
title: '호환성이 손상되는 변경: 인증: AzureAD.UI 및 AzureADB2C.UI API와 패키지는 사용되지 않는 것으로 표시됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 인증: AzureAD.UI 및 AzureADB2C.UI API와 패키지는 사용되지 않는 것으로 표시됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c977ba4d6e34fc5f11133bdd1446a94d54efcb63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759995"
---
# <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="6978d-103">인증: AzureAD.UI 및 AzureADB2C.UI API와 패키지는 사용되지 않는 것으로 표시됨</span><span class="sxs-lookup"><span data-stu-id="6978d-103">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="6978d-104">ASP.NET Core 2.1에서 Azure AD(Azure Active Directory) 및 Azure AD B2C(Azure Active Directory B2C) 인증과의 통합은 [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) 및 [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) 패키지에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-104">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="6978d-105">이러한 패키지에서 제공되는 기능은 Azure AD v1.0 엔드포인트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-105">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="6978d-106">ASP.NET Core 5.0 이상에서 Azure AD 및 Azure AD B2C 인증과의 통합은 [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) 패키지에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-106">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="6978d-107">이 패키지는 Microsoft ID 플랫폼(이전에는 Azure AD v2.0 엔드포인트라고 함)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-107">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="6978d-108">따라서, `Microsoft.AspNetCore.Authentication.AzureAD.UI` 및 `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` 패키지의 이전 API는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-108">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="6978d-109">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6978d-109">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6978d-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6978d-110">Version introduced</span></span>

<span data-ttu-id="6978d-111">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="6978d-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6978d-112">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6978d-112">Old behavior</span></span>

<span data-ttu-id="6978d-113">해당 API는 사용되지 않는 것으로 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-113">The APIs weren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6978d-114">새 동작</span><span class="sxs-lookup"><span data-stu-id="6978d-114">New behavior</span></span>

<span data-ttu-id="6978d-115">해당 API는 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-115">The APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6978d-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6978d-116">Reason for change</span></span>

<span data-ttu-id="6978d-117">Azure AD 및 Azure AD B2C 인증 기능은 `Microsoft.Identity.Web`에서 제공하는 Microsoft 인증 라이브러리(MSAL) API로 마이그레이션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6978d-117">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6978d-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6978d-118">Recommended action</span></span>

<span data-ttu-id="6978d-119">[웹앱](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) 및 [웹 API](https://github.com/azuread/microsoft-identity-web/wiki/web-apis)에 대한 `Microsoft.Identity.Web` API 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6978d-119">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6978d-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6978d-120">Affected APIs</span></span>

* [<span data-ttu-id="6978d-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="6978d-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="6978d-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="6978d-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="6978d-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="6978d-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="6978d-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="6978d-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="6978d-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="6978d-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="6978d-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="6978d-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
