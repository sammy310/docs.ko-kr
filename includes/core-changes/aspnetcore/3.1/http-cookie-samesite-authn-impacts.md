---
ms.openlocfilehash: b0d093cc30a09b3248cc57a521b386bf581b5451
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552158"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a><span data-ttu-id="3d771-101">HTTP: 브라우저 SameSite 변경 내용이 인증에 영향</span><span class="sxs-lookup"><span data-stu-id="3d771-101">HTTP: Browser SameSite changes impact authentication</span></span>

<span data-ttu-id="3d771-102">Chrome 및 Firefox와 같은 일부 브라우저에서는 쿠키에 대한 `SameSite`의 구현에 호환성이 손상되는 변경이 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-102">Some browsers, such as Chrome and Firefox, made breaking changes to their implementations of `SameSite` for cookies.</span></span> <span data-ttu-id="3d771-103">이 변경 사항은 `SameSite=None`을 전송하여 옵트아웃해야 하는 OpenID Connect 및 WS-Federation과 같은 원격 인증 시나리오에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-103">The changes impact remote authentication scenarios, such as OpenID Connect and WS-Federation, which must opt out by sending `SameSite=None`.</span></span> <span data-ttu-id="3d771-104">그러나 `SameSite=None`이(가) iOS 12 및 일부 이전 버전의 기타 브라우저에서 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-104">However, `SameSite=None` breaks on iOS 12 and some older versions of other browsers.</span></span> <span data-ttu-id="3d771-105">이 앱에서 이 버전을 찾아 `SameSite`를 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-105">The app needs to sniff these versions and omit `SameSite`.</span></span>

<span data-ttu-id="3d771-106">이 문제에 대한 자세한 내용은 [aspnet/AspNetCore#14996](https://github.com/aspnet/AspNetCore/issues/14996)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-106">For discussion on this issue, see [aspnet/AspNetCore#14996](https://github.com/aspnet/AspNetCore/issues/14996).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3d771-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3d771-107">Version introduced</span></span>

<span data-ttu-id="3d771-108">3.1 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="3d771-108">3.1 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3d771-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="3d771-109">Old behavior</span></span>

<span data-ttu-id="3d771-110">`SameSite`은(는) HTTP 쿠키의 2016 초안 표준 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-110">`SameSite` is a 2016 draft standard extension to HTTP cookies.</span></span> <span data-ttu-id="3d771-111">CSRF(교차 사이트 요청 위조)를 완화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-111">It's intended to mitigate Cross-Site Request Forgery (CSRF).</span></span> <span data-ttu-id="3d771-112">원래는 새 매개 변수를 추가하여 서버에서 옵트인하는 기능으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-112">This was originally designed as a feature the servers would opt into by adding the new parameters.</span></span> <span data-ttu-id="3d771-113">ASP.NET Core 2.0에서 `SameSite`에 대한 초기 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-113">ASP.NET Core 2.0 added initial support for `SameSite`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3d771-114">새 동작</span><span class="sxs-lookup"><span data-stu-id="3d771-114">New behavior</span></span>

<span data-ttu-id="3d771-115">Google은 이전 버전과 호환되지 않는 새 초안 표준을 제안했습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-115">Google proposed a new draft standard that isn't backwards compatible.</span></span> <span data-ttu-id="3d771-116">이 표준은 기본 모드를 `Lax`으로 변경하고 옵트아웃할 새 항목 `None`을 추가합니다. 대부분의 앱 쿠키의 경우 `Lax`가 충분하지만, OpenID Connect 및 WS-Federation 로그인과 같은 교차 사이트 시나리오는 방해합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-116">The standard changes the default mode to `Lax` and adds a new entry `None` to opt out. `Lax` suffices for most app cookies; however, it breaks cross-site scenarios like OpenID Connect and WS-Federation login.</span></span> <span data-ttu-id="3d771-117">대부분의 OAuth 로그인은 요청 진행 방법의 차이로 인해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-117">Most OAuth logins aren't affected because of differences in how the request flows.</span></span> <span data-ttu-id="3d771-118">새 `None` 매개 변수로 인해 이전 초안 표준(예: iOS 12)을 구현한 클라이언트에 호환성 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-118">The new `None` parameter causes compatibility problems with clients that implemented the prior draft standard (for example, iOS 12).</span></span> <span data-ttu-id="3d771-119">Chrome 80에는 변경 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-119">Chrome 80 will include the changes.</span></span> <span data-ttu-id="3d771-120">Chrome 제품 출시 타임라인을 보려면 [SameSite 업데이트](https://www.chromium.org/updates/same-site)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-120">See [SameSite Updates](https://www.chromium.org/updates/same-site) for the Chrome product launch timeline.</span></span>

<span data-ttu-id="3d771-121">ASP.NET Core 3.1이 새 `SameSite` 동작을 구현하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-121">ASP.NET Core 3.1 has been updated to implement the new `SameSite` behavior.</span></span> <span data-ttu-id="3d771-122">업데이트는 `SameSiteMode.None`의 동작을 재정의하여 `SameSite=None`을 내보내고 새 값 `SameSiteMode.Unspecified`를 추가하여 `SameSite` 특성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-122">The update redefines the behavior of `SameSiteMode.None` to emit `SameSite=None` and adds a new value `SameSiteMode.Unspecified` to omit the `SameSite` attribute.</span></span> <span data-ttu-id="3d771-123">일부 구성 요소에서 OpenID Connect 상관 관계 및 nonce 쿠키와 같은 특정 시나리오와 관련된 값을 설정하지만 이제 모든 쿠키 API는 `Unspecified`를 기본값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-123">All cookie APIs now default to `Unspecified`, though some components that use cookies set values more specific to their scenarios such as the OpenID Connect correlation and nonce cookies.</span></span>

<span data-ttu-id="3d771-124">이 영역에 대한 기타 최근 변경 사항은 [HTTP: 일부 쿠키 SameSite 기본값이 없음으로 변경됨](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-124">For other recent changes in this area, see [HTTP: Some cookie SameSite defaults changed to None](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span></span> <span data-ttu-id="3d771-125">ASP.NET Core 3.0에서 대부분의 기본값이 <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType>에서 <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType>(으)로 변경되었지만, 이전 표준은 여전히 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-125">In ASP.NET Core 3.0, most defaults were changed from <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> to <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> (but still using the prior standard).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3d771-126">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3d771-126">Reason for change</span></span>

<span data-ttu-id="3d771-127">이전 텍스트에서 설명한 대로 브라우저 및 사양이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-127">Browser and specification changes as outlined in the preceding text.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3d771-128">권장 작업</span><span class="sxs-lookup"><span data-stu-id="3d771-128">Recommended action</span></span>

<span data-ttu-id="3d771-129">타사 로그인 등 원격 사이트와 상호 작용하는 앱은 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-129">Apps that interact with remote sites, such as through third-party login, need to:</span></span>

* <span data-ttu-id="3d771-130">이 시나리오를 여러 브라우저에서 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-130">Test those scenarios on multiple browsers.</span></span>
* <span data-ttu-id="3d771-131">[이전 브라우저 지원](#support-older-browsers)에서 설명된 대로 쿠키 정책 브라우저 검색 완화를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-131">Apply the cookie policy browser sniffing mitigation discussed in [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="3d771-132">테스트 및 브라우저 검색 지침은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-132">For testing and browser sniffing instructions, see the following section.</span></span>

##### <a name="determine-if-youre-affected"></a><span data-ttu-id="3d771-133">사용자가 영향을 받는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-133">Determine if you're affected</span></span>

<span data-ttu-id="3d771-134">새 동작을 옵트인할 수 있는 클라이언트 버전을 사용하여 웹앱을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-134">Test your web app using a client version that can opt into the new behavior.</span></span> <span data-ttu-id="3d771-135">Chrome, Firefox 및 Microsoft Edge Chromium에는 테스트에 사용할 수 있는 새 옵트인 기능 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-135">Chrome, Firefox, and Microsoft Edge Chromium all have new opt-in feature flags that can be used for testing.</span></span> <span data-ttu-id="3d771-136">패치, 특히 Safari를 적용한 후 앱이 이전 클라이언트 버전과 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-136">Verify that your app is compatible with older client versions after you've applied the patches, especially Safari.</span></span> <span data-ttu-id="3d771-137">자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-137">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="chrome"></a><span data-ttu-id="3d771-138">Chrome</span><span class="sxs-lookup"><span data-stu-id="3d771-138">Chrome</span></span>

<span data-ttu-id="3d771-139">Chrome 78 이상에서는 잘못된 테스트 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-139">Chrome 78 and later yield misleading test results.</span></span> <span data-ttu-id="3d771-140">이러한 버전에는 임시 해결 방법이 있으며 2분 이내 쿠키를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-140">Those versions have a temporary mitigation in place and allow cookies less than two minutes old.</span></span> <span data-ttu-id="3d771-141">적절한 테스트 플래그를 사용하도록 설정하면 Chrome 76 및 77에서 더 정확한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-141">With the appropriate test flags enabled, Chrome 76 and 77 yield more accurate results.</span></span> <span data-ttu-id="3d771-142">새 동작을 테스트하려면 `chrome://flags/#same-site-by-default-cookies`를 사용으로 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-142">To test the new behavior, toggle `chrome://flags/#same-site-by-default-cookies` to enabled.</span></span> <span data-ttu-id="3d771-143">Chrome 75 이전 버전이 새 `None` 설정에서 실패한다고 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-143">Chrome 75 and earlier are reported to fail with the new `None` setting.</span></span> <span data-ttu-id="3d771-144">자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-144">For more information, see [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="3d771-145">Google은 이전 Chrome 버전을 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-145">Google doesn't make older Chrome versions available.</span></span> <span data-ttu-id="3d771-146">그러나 테스트에 충분한 이전 버전의 Chromium을를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-146">You can, however, download older versions of Chromium, which will suffice for testing.</span></span> <span data-ttu-id="3d771-147">[Chromium 다운로드](https://www.chromium.org/getting-involved/download-chromium)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-147">Follow the instructions at [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).</span></span>

* [<span data-ttu-id="3d771-148">Chromium 76 Win64</span><span class="sxs-lookup"><span data-stu-id="3d771-148">Chromium 76 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [<span data-ttu-id="3d771-149">Chromium 74 Win64</span><span class="sxs-lookup"><span data-stu-id="3d771-149">Chromium 74 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a><span data-ttu-id="3d771-150">Safari</span><span class="sxs-lookup"><span data-stu-id="3d771-150">Safari</span></span>

<span data-ttu-id="3d771-151">Safari 12는 이전 초안을 엄격하게 구현했으며 쿠키에 새 `None` 값이 표시되는 경우 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-151">Safari 12 strictly implemented the prior draft and fails if it sees the new `None` value in cookies.</span></span> <span data-ttu-id="3d771-152">[이전 브라우저 지원](#support-older-browsers)에 표시된 브라우저 검색 코드를 통해 이를 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-152">This must be avoided via the browser sniffing code shown in [Support older browsers](#support-older-browsers).</span></span> <span data-ttu-id="3d771-153">MSAL(Microsoft Authentication Library), ADAL(Active Directory 인증 라이브러리) 또는 사용 중인 라이브러리를 사용하여 WebKit 기반 OS 스타일뿐 아니라 Safari 12 및 13을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-153">Ensure you test Safari 12 and 13 as well as WebKit-based, OS-style logins using Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL), or whichever library you're using.</span></span> <span data-ttu-id="3d771-154">문제는 기본 OS 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-154">The problem is dependent on the underlying OS version.</span></span> <span data-ttu-id="3d771-155">OSX Mojave 10.14 및 iOS 12는 새 동작에 호환성 문제가 있는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-155">OSX Mojave 10.14 and iOS 12 are known to have compatibility problems with the new behavior.</span></span> <span data-ttu-id="3d771-156">OSX Catalina 10.15 또는 iOS 13으로 업그레이드하면 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-156">Upgrading to OSX Catalina 10.15 or iOS 13 fixes the problem.</span></span> <span data-ttu-id="3d771-157">Safari에는 현재 새 사양 동작을 테스트하기 위한 옵트인 플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-157">Safari doesn't currently have an opt-in flag for testing the new specification behavior.</span></span>

##### <a name="firefox"></a><span data-ttu-id="3d771-158">Firefox</span><span class="sxs-lookup"><span data-stu-id="3d771-158">Firefox</span></span>

<span data-ttu-id="3d771-159">새 표준에 대한 Firefox 지원은 기능 플래그 `network.cookie.sameSite.laxByDefault`를 사용하여 `about:config` 페이지에서 옵트인하여 버전 68 이상에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-159">Firefox support for the new standard can be tested on version 68 and later by opting in on the `about:config` page with the feature flag `network.cookie.sameSite.laxByDefault`.</span></span> <span data-ttu-id="3d771-160">이전 버전의 Firefox에서는 호환성 문제가 보고되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-160">No compatibility issues have been reported on older versions of Firefox.</span></span>

##### <a name="microsoft-edge"></a><span data-ttu-id="3d771-161">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d771-161">Microsoft Edge</span></span>

<span data-ttu-id="3d771-162">Microsoft Edge는 이전 `SameSite` 표준을 지원하지만, 버전 44부터 새 표준에 호환성 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-162">While Microsoft Edge supports the old `SameSite` standard, as of version 44 it didn't have any compatibility problems with the new standard.</span></span>

##### <a name="microsoft-edge-chromium"></a><span data-ttu-id="3d771-163">Microsoft Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="3d771-163">Microsoft Edge Chromium</span></span>

<span data-ttu-id="3d771-164">기능 플래그는 `edge://flags/#same-site-by-default-cookies`입니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-164">The feature flag is `edge://flags/#same-site-by-default-cookies`.</span></span> <span data-ttu-id="3d771-165">Microsoft Edge Chromium 78을 사용하여 테스트할 때 호환성 문제가 관찰되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-165">No compatibility issues were observed when testing with Microsoft Edge Chromium 78.</span></span>

##### <a name="electron"></a><span data-ttu-id="3d771-166">Electron</span><span class="sxs-lookup"><span data-stu-id="3d771-166">Electron</span></span>

<span data-ttu-id="3d771-167">Electron 버전에는 이전 버전의 Chromium이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-167">Versions of Electron include older versions of Chromium.</span></span> <span data-ttu-id="3d771-168">예를 들어, Microsoft Teams에서 사용하는 Electron의 버전은 Chromium 66이며, 이는 이전 동작을 보입니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-168">For example, the version of Electron used by Microsoft Teams is Chromium 66, which exhibits the older behavior.</span></span> <span data-ttu-id="3d771-169">사용자의 제품에서 사용하는 Electron 버전으로 자체 호환성 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-169">Perform your own compatibility testing with the version of Electron your product uses.</span></span> <span data-ttu-id="3d771-170">자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d771-170">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="support-older-browsers"></a><span data-ttu-id="3d771-171">이전 브라우저 지원</span><span class="sxs-lookup"><span data-stu-id="3d771-171">Support older browsers</span></span>

<span data-ttu-id="3d771-172">2016 `SameSite` 표준에 따라 알 수 없는 값을 `SameSite=Strict` 값으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-172">The 2016 `SameSite` standard mandated that unknown values be treated as `SameSite=Strict` values.</span></span> <span data-ttu-id="3d771-173">따라서 원래 표준을 지원하는 모든 이전 브라우저는 값이 `None`인 `SameSite` 속성이 표시될 때 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-173">Consequently, any older browsers that support the original standard may break when they see a `SameSite` property with a value of `None`.</span></span> <span data-ttu-id="3d771-174">이러한 이전 브라우저를 지원하려는 경우 웹앱은 브라우저 검색을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-174">Web apps must implement browser sniffing if they intend to support these old browsers.</span></span> <span data-ttu-id="3d771-175">`User-Agent` 요청 헤더 값이 매우 불안정하고 매주 변경되기 때문에 ASP.NET Core에서 브라우저 검색을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-175">ASP.NET Core doesn't implement browser sniffing for you because `User-Agent` request header values are highly unstable and change on a weekly basis.</span></span> <span data-ttu-id="3d771-176">대신, 쿠키 정책의 확장 지점을 사용하여 `User-Agent`별 논리를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-176">Instead, an extension point in the cookie policy allows you to add `User-Agent`-specific logic.</span></span>

<span data-ttu-id="3d771-177">*Startup.cs*에서 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-177">In *Startup.cs*, add the following code:</span></span>

```csharp
private void CheckSameSite(HttpContext httpContext, CookieOptions options)
{
    if (options.SameSite == SameSiteMode.None) 
    { 
        var userAgent = httpContext.Request.Headers["User-Agent"].ToString();
        // TODO: Use your User Agent library of choice here. 
        if (/* UserAgent doesn't support new behavior */) 
        { 
            options.SameSite = SameSiteMode.Unspecified;
        }
    }
}

public void ConfigureServices(IServiceCollection services) 
{ 
    services.Configure<CookiePolicyOptions>(options => 
    { 
        options.MinimumSameSitePolicy = SameSiteMode.Unspecified;
        options.OnAppendCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
        options.OnDeleteCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
    }); 
} 

public void Configure(IApplicationBuilder app) 
{ 
    // Before UseAuthentication or anything else that writes cookies.
    app.UseCookiePolicy();

    app.UseAuthentication(); 
    // code omitted for brevity
}
```

##### <a name="opt-out-switches"></a><span data-ttu-id="3d771-178">옵트아웃 스위치</span><span class="sxs-lookup"><span data-stu-id="3d771-178">Opt-out switches</span></span>

<span data-ttu-id="3d771-179">`Microsoft.AspNetCore.SuppressSameSiteNone` 호환성 스위치를 사용하면 새 ASP.NET Core 쿠키 동작을 임시로 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-179">The `Microsoft.AspNetCore.SuppressSameSiteNone` compatibility switch enables you to temporarily opt out of the new ASP.NET Core cookie behavior.</span></span> <span data-ttu-id="3d771-180">프로젝트에서 *runtimeconfig.template.json* 파일에 다음 JSON을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-180">Add the following JSON to a *runtimeconfig.template.json* file in your project:</span></span>

```json
{ 
  "configProperties": { 
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true" 
  } 
}
```

##### <a name="other-versions"></a><span data-ttu-id="3d771-181">다른 버전</span><span class="sxs-lookup"><span data-stu-id="3d771-181">Other Versions</span></span>

<span data-ttu-id="3d771-182">관련 `SameSite` 패치가 곧 출시될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="3d771-182">Related `SameSite` patches are forthcoming for:</span></span>

* <span data-ttu-id="3d771-183">ASP.NET Core 2.1, 2.2 및 3.0</span><span class="sxs-lookup"><span data-stu-id="3d771-183">ASP.NET Core 2.1, 2.2, and 3.0</span></span>
* <span data-ttu-id="3d771-184">`Microsoft.Owin` 4.1</span><span class="sxs-lookup"><span data-stu-id="3d771-184">`Microsoft.Owin` 4.1</span></span>
* <span data-ttu-id="3d771-185">`System.Web`(.NET Framework 4.7.2 이상)</span><span class="sxs-lookup"><span data-stu-id="3d771-185">`System.Web` (for .NET Framework 4.7.2 and later)</span></span>

#### <a name="category"></a><span data-ttu-id="3d771-186">범주</span><span class="sxs-lookup"><span data-stu-id="3d771-186">Category</span></span>

<span data-ttu-id="3d771-187">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3d771-187">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3d771-188">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3d771-188">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieBuilder.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieOptions.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`
- `Overload:Microsoft.AspNetCore.Http.CookieBuilder.SameSite`
- `Overload:Microsoft.AspNetCore.Http.CookieOptions.SameSite`
- `T:Microsoft.AspNetCore.Http.SameSiteMode`
- `T:Microsoft.Net.Http.Headers.SameSiteMode`
- `Overload:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite`

-->
