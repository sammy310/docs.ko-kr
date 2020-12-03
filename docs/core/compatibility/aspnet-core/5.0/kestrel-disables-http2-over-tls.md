---
title: '호환성이 손상되는 변경: Kestrel: 호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2 사용 안 함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Kestrel: 호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2 사용 안 함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759882"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a><span data-ttu-id="d75c4-103">Kestrel: 호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d75c4-103">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>

<span data-ttu-id="d75c4-104">Windows에서 TLS(전송 계층 보안)를 통한 HTTP/2를 사용하도록 설정하려면 다음 두 가지 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-104">To enable HTTP/2 over Transport Layer Security (TLS) on Windows, two requirements need to be met:</span></span>

- <span data-ttu-id="d75c4-105">ALPN(Application-Layer Protocol Negotiation) 지원 - Windows 8.1 및 Windows Server 2012 R2부터 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-105">Application-Layer Protocol Negotiation (ALPN) support, which is available starting with Windows 8.1 and Windows Server 2012 R2.</span></span>
- <span data-ttu-id="d75c4-106">HTTP/2와 호환되는 암호 세트 - Windows 10 및 Windows Server 2016부터 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-106">A set of ciphers compatible with HTTP/2, which is available starting with Windows 10 and Windows Server 2016.</span></span>

<span data-ttu-id="d75c4-107">따라서 TLS를 통한 HTTP/2가 구성된 경우 Kestrel의 동작이 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-107">As such, Kestrel's behavior when HTTP/2 over TLS is configured has changed to:</span></span>

- <span data-ttu-id="d75c4-108">[ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols)가 `Http1AndHttp2`로 설정된 경우 `Http1`로 다운그레이드하고 `Information` 수준에 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-108">Downgrade to `Http1` and log a message at the `Information` level when [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) is set to `Http1AndHttp2`.</span></span> <span data-ttu-id="d75c4-109">`Http1AndHttp2`는 `ListenOptions.HttpProtocols`에 대한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-109">`Http1AndHttp2` is the default value for `ListenOptions.HttpProtocols`.</span></span>
- <span data-ttu-id="d75c4-110">`ListenOptions.HttpProtocols`가 `Http2`로 설정된 경우 `NotSupportedException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-110">Throw a `NotSupportedException` when `ListenOptions.HttpProtocols` is set to `Http2`.</span></span>

<span data-ttu-id="d75c4-111">자세한 내용은 이슈 [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d75c4-111">For discussion, see issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d75c4-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d75c4-112">Version introduced</span></span>

<span data-ttu-id="d75c4-113">ASP.NET Core 5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="d75c4-113">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d75c4-114">이전 동작</span><span class="sxs-lookup"><span data-stu-id="d75c4-114">Old behavior</span></span>

<span data-ttu-id="d75c4-115">다음 표에서는 TLS를 통한 HTTP/2가 구성된 경우의 동작을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-115">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="d75c4-116">프로토콜</span><span class="sxs-lookup"><span data-stu-id="d75c4-116">Protocols</span></span> | <span data-ttu-id="d75c4-117">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="d75c4-117">Windows 7,</span></span><br /><span data-ttu-id="d75c4-118">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d75c4-118">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="d75c4-119">이하</span><span class="sxs-lookup"><span data-stu-id="d75c4-119">or earlier</span></span> | <span data-ttu-id="d75c4-120">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="d75c4-120">Windows 8,</span></span><br /><span data-ttu-id="d75c4-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d75c4-121">Windows Server 2012</span></span> | <span data-ttu-id="d75c4-122">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="d75c4-122">Windows 8.1,</span></span><br /><span data-ttu-id="d75c4-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d75c4-123">Windows Server 2012 R2</span></span> | <span data-ttu-id="d75c4-124">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="d75c4-124">Windows 10,</span></span><br /><span data-ttu-id="d75c4-125">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d75c4-125">Windows Server 2016,</span></span><br /><span data-ttu-id="d75c4-126">이상</span><span class="sxs-lookup"><span data-stu-id="d75c4-126">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="d75c4-127">`NotSupportedException` throw</span><span class="sxs-lookup"><span data-stu-id="d75c4-127">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="d75c4-128">TLS 핸드셰이크 중 오류 발생</span><span class="sxs-lookup"><span data-stu-id="d75c4-128">Error during TLS handshake</span></span>     | <span data-ttu-id="d75c4-129">TLS 핸드셰이크 중 오류 발생 &ast;</span><span class="sxs-lookup"><span data-stu-id="d75c4-129">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="d75c4-130">오류 없음</span><span class="sxs-lookup"><span data-stu-id="d75c4-130">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="d75c4-131">`Http1`로 다운그레이드</span><span class="sxs-lookup"><span data-stu-id="d75c4-131">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="d75c4-132">`Http1`로 다운그레이드</span><span class="sxs-lookup"><span data-stu-id="d75c4-132">Downgrade to `Http1`</span></span>     | <span data-ttu-id="d75c4-133">TLS 핸드셰이크 중 오류 발생 &ast;</span><span class="sxs-lookup"><span data-stu-id="d75c4-133">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="d75c4-134">오류 없음</span><span class="sxs-lookup"><span data-stu-id="d75c4-134">No error</span></span> |

<span data-ttu-id="d75c4-135">&ast; 이러한 시나리오를 사용하려면 호환되는 암호 도구 모음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-135">&ast; Configure compatible cipher suites to enable these scenarios.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d75c4-136">새 동작</span><span class="sxs-lookup"><span data-stu-id="d75c4-136">New behavior</span></span>

<span data-ttu-id="d75c4-137">다음 표에서는 TLS를 통한 HTTP/2가 구성된 경우의 동작을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-137">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="d75c4-138">프로토콜</span><span class="sxs-lookup"><span data-stu-id="d75c4-138">Protocols</span></span> | <span data-ttu-id="d75c4-139">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="d75c4-139">Windows 7,</span></span><br /><span data-ttu-id="d75c4-140">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d75c4-140">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="d75c4-141">이하</span><span class="sxs-lookup"><span data-stu-id="d75c4-141">or earlier</span></span> | <span data-ttu-id="d75c4-142">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="d75c4-142">Windows 8,</span></span><br /><span data-ttu-id="d75c4-143">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d75c4-143">Windows Server 2012</span></span> | <span data-ttu-id="d75c4-144">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="d75c4-144">Windows 8.1,</span></span><br /><span data-ttu-id="d75c4-145">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d75c4-145">Windows Server 2012 R2</span></span> | <span data-ttu-id="d75c4-146">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="d75c4-146">Windows 10,</span></span><br /><span data-ttu-id="d75c4-147">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d75c4-147">Windows Server 2016,</span></span><br /><span data-ttu-id="d75c4-148">이상</span><span class="sxs-lookup"><span data-stu-id="d75c4-148">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="d75c4-149">`NotSupportedException` throw</span><span class="sxs-lookup"><span data-stu-id="d75c4-149">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="d75c4-150">`NotSupportedException` throw</span><span class="sxs-lookup"><span data-stu-id="d75c4-150">Throw `NotSupportedException`</span></span>     | <span data-ttu-id="d75c4-151">`NotSupportedException` throw &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="d75c4-151">Throw `NotSupportedException` &ast;&ast;</span></span>     | <span data-ttu-id="d75c4-152">오류 없음</span><span class="sxs-lookup"><span data-stu-id="d75c4-152">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="d75c4-153">`Http1`로 다운그레이드</span><span class="sxs-lookup"><span data-stu-id="d75c4-153">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="d75c4-154">`Http1`로 다운그레이드</span><span class="sxs-lookup"><span data-stu-id="d75c4-154">Downgrade to `Http1`</span></span>     | <span data-ttu-id="d75c4-155">`Http1`로 다운그레이드 &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="d75c4-155">Downgrade to `Http1` &ast;&ast;</span></span>     | <span data-ttu-id="d75c4-156">오류 없음</span><span class="sxs-lookup"><span data-stu-id="d75c4-156">No error</span></span> |

<span data-ttu-id="d75c4-157">&ast;&ast; 이러한 시나리오를 사용하려면 호환되는 암호 도구 모음을 구성하고 앱 컨텍스트 스위치 `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-157">&ast;&ast; Configure compatible cipher suites and set the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` to `true` to enable these scenarios.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d75c4-158">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d75c4-158">Reason for change</span></span>

<span data-ttu-id="d75c4-159">이 변경은 이전 Windows 버전에서 TLS를 통한 HTTP/2의 호환성 오류가 최대한 빨리 명확히 표시되도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-159">This change ensures compatibility errors for HTTP/2 over TLS on older Windows versions are surfaced as early and as clearly as possible.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d75c4-160">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d75c4-160">Recommended action</span></span>

<span data-ttu-id="d75c4-161">호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2가 사용하지 않도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-161">Ensure HTTP/2 over TLS is disabled on incompatible Windows versions.</span></span> <span data-ttu-id="d75c4-162">Windows 8.1 및 Windows Server 2012 R2는 기본적으로 필요한 암호가 없으므로 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-162">Windows 8.1 and Windows Server 2012 R2 are incompatible since they lack the necessary ciphers by default.</span></span> <span data-ttu-id="d75c4-163">그러나 HTTP/2 호환 암호를 사용하도록 컴퓨터 구성 설정을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-163">However, it's possible to update the Computer Configuration settings to use HTTP/2 compatible ciphers.</span></span> <span data-ttu-id="d75c4-164">자세한 내용은 [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1)(Windows 8.1의 TLS 암호 도구 모음)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d75c4-164">For more information, see [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span></span> <span data-ttu-id="d75c4-165">구성한 경우 앱 컨텍스트 스위치 `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`를 설정하여 Kestrel에서 TLS를 통한 HTTP/2를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-165">Once configured, HTTP/2 over TLS on Kestrel must be enabled by setting the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`.</span></span> <span data-ttu-id="d75c4-166">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d75c4-166">For example:</span></span>

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

<span data-ttu-id="d75c4-167">기본 지원은 변경되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-167">No underlying support has changed.</span></span> <span data-ttu-id="d75c4-168">예를 들어 TLS를 통한 HTTP/2는 이전에도 Windows 8 또는 Windows Server 2012에서 작동하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-168">For example, HTTP/2 over TLS has never worked on Windows 8 or Windows Server 2012.</span></span> <span data-ttu-id="d75c4-169">이 변경으로 이러한 지원되지 않는 시나리오에서 오류가 표시되는 방법이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75c4-169">This change modifies how errors in these unsupported scenarios are presented.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d75c4-170">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d75c4-170">Affected APIs</span></span>

<span data-ttu-id="d75c4-171">없음</span><span class="sxs-lookup"><span data-stu-id="d75c4-171">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
