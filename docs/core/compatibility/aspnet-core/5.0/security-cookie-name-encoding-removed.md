---
title: '호환성이 손상되는 변경: 보안: 쿠키 이름 인코딩이 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 보안: 쿠키 이름 인코딩이 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 00764493fb2d8d300612f2bd9dc6e512b10be25f
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190062"
---
# <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="26e18-103">보안: 쿠키 이름 인코딩이 제거됨</span><span class="sxs-lookup"><span data-stu-id="26e18-103">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="26e18-104">[HTTP 쿠키 표준](https://tools.ietf.org/html/rfc6265#section-4.1.1)에서는 쿠키 이름과 값에 특정 문자만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-104">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="26e18-105">허용되지 않는 문자를 지원하기 위해 ASP.NET Core에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-105">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="26e18-106">응답 쿠키를 만드는 경우 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-106">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="26e18-107">요청 쿠키를 읽는 경우 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-107">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="26e18-108">ASP.NET Core 5.0에서는 보안 문제에 대한 응답으로 이 인코딩 동작이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-108">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="26e18-109">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26e18-109">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="26e18-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="26e18-110">Version introduced</span></span>

<span data-ttu-id="26e18-111">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="26e18-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="26e18-112">이전 동작</span><span class="sxs-lookup"><span data-stu-id="26e18-112">Old behavior</span></span>

<span data-ttu-id="26e18-113">응답 쿠키 이름이 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-113">Response cookie names are encoded.</span></span> <span data-ttu-id="26e18-114">요청 쿠키 이름이 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-114">Request cookie names are decoded.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="26e18-115">새 동작</span><span class="sxs-lookup"><span data-stu-id="26e18-115">New behavior</span></span>

<span data-ttu-id="26e18-116">쿠키 이름의 인코딩 및 디코딩이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-116">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="26e18-117">[지원되는 이전 ASP.NET Core 버전](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)에 대해 팀은 현재 위치에서 디코딩 문제를 완화할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-117">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="26e18-118">또한 잘못된 쿠키 이름으로 <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType>을 호출하면 <xref:System.ArgumentException> 형식의 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-118">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="26e18-119">쿠키 값의 인코딩 및 디코딩은 변경되지 않고 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-119">Encoding and decoding of cookie values remains unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="26e18-120">변경 이유</span><span class="sxs-lookup"><span data-stu-id="26e18-120">Reason for change</span></span>

<span data-ttu-id="26e18-121">[여러 개의 웹 프레임워크](https://github.com/advisories/GHSA-j6w9-fv6q-3q52)에서 문제가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-121">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="26e18-122">인코딩 및 디코딩을 통해 공격자가 `__Host-` 등의 예약된 접두사를 `__%48ost-` 등의 인코딩된 값으로 스푸핑하여 [쿠키 접두사](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00)라는 보안 기능을 무시할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-122">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="26e18-123">이 공격을 수행하려면 웹 사이트에 XSS(교차 사이트 스크립팅) 취약성과 같은 스푸핑된 쿠키를 삽입하기 위한 보조 익스플로잇이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-123">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="26e18-124">해당 접두사는 ASP.NET Core 또는 `Microsoft.Owin` 라이브러리나 템플릿에서 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-124">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="26e18-125">권장 조치</span><span class="sxs-lookup"><span data-stu-id="26e18-125">Recommended action</span></span>

<span data-ttu-id="26e18-126">프로젝트를 ASP.NET Core 5.0 이상으로 이동하는 경우 해당 쿠키 이름이 [토큰 사양 요구 사항](https://tools.ietf.org/html/rfc2616#section-2.2)을 준수하는지 확인합니다. 즉, 컨트롤과 구분 기호를 제외하고 ASCII 문자를 사용해야 합니다(`"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`).</span><span class="sxs-lookup"><span data-stu-id="26e18-126">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="26e18-127">쿠키 이름 또는 다른 HTTP 헤더에 비ASCII 문자를 사용하면 서버에서 예외가 발생하거나 클라이언트에서 부적절한 라운드트립이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26e18-127">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="26e18-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="26e18-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- `Microsoft.Owin.IOwinRequest.Cookies`
- `Microsoft.Owin.IOwinResponse.Cookies`

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
