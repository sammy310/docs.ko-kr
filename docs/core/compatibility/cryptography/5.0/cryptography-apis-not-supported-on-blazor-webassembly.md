---
title: '호환성이 손상되는 변경: Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API'
description: 암호화 API가 브라우저에서 실행될 때 예외를 throw하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/16/2020
ms.openlocfilehash: ecbdda4c04642af6b1737e888491eb6565ba7479
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256883"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="da10a-103">Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API</span><span class="sxs-lookup"><span data-stu-id="da10a-103">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="da10a-104"><xref:System.Security.Cryptography> API는 브라우저에서 실행될 때 런타임에 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-104"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

## <a name="change-description"></a><span data-ttu-id="da10a-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="da10a-105">Change description</span></span>

<span data-ttu-id="da10a-106">이전 .NET 버전에서는 대부분의 <xref:System.Security.Cryptography> API를 Blazor WebAssembly 앱에 사용할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-106">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="da10a-107">.NET 5부터 Blazor WebAssembly 앱이 전체 .NET 5 API 노출 영역을 대상으로 하지만, 브라우저 샌드박스 제약 조건으로 인해 일부 .NET 5 API는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-107">Starting in .NET 5, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="da10a-108">.NET 5 이상 버전에서 지원되지 않는 <xref:System.Security.Cryptography> API는 WebAssembly에서 실행될 때 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-108">In .NET 5 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="da10a-109">[플랫폼 호환성 분석기](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md)는 브라우저 플랫폼을 지원하는 프로젝트를 빌드할 때 영향을 받는 API에 대한 모든 호출에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-109">The [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="da10a-110">이 분석기는 .NET 5 이상 앱에서 기본적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-110">This analyzer runs by default in .NET 5 and later apps.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="da10a-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="da10a-111">Reason for change</span></span>

<span data-ttu-id="da10a-112">Microsoft는 Blazor WebAssembly 구성에서 OpenSSL을 종속성으로 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-112">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="da10a-113">브라우저의 `SubtleCrypto` API와 통합하여 이 문제를 해결하려고 했지만,</span><span class="sxs-lookup"><span data-stu-id="da10a-113">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="da10a-114">안타깝게도 상당한 API 변경이 필요하여 통합이 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-114">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="da10a-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="da10a-115">Version introduced</span></span>

<span data-ttu-id="da10a-116">5.0</span><span class="sxs-lookup"><span data-stu-id="da10a-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="da10a-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="da10a-117">Recommended action</span></span>

<span data-ttu-id="da10a-118">지금은 제안할 수 있는 유용한 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da10a-118">There are no good workarounds to suggest at this time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="da10a-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="da10a-119">Affected APIs</span></span>

<span data-ttu-id="da10a-120">다음을 제외한 모든 <xref:System.Security.Cryptography?displayProperty=fullName> API:</span><span class="sxs-lookup"><span data-stu-id="da10a-120">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
