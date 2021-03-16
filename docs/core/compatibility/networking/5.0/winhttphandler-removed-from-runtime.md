---
title: '호환성이 손상되는 변경: .NET 런타임에서 WinHttpHandler 제거됨'
description: .NET 런타임에서 WinHttpHandler가 제거된 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 95abcfb4d7670be035bd640dbb85458406c1b0e0
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256415"
---
# <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="64068-103">.NET 런타임에서 WinHttpHandler 제거됨</span><span class="sxs-lookup"><span data-stu-id="64068-103">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="64068-104">`WinHttpHandler` 클래스가 *System.Net.Http.dll* 어셈블리에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64068-104">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="64068-105">이제 OOB(대역 외) [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="64068-105">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="64068-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="64068-106">Version introduced</span></span>

<span data-ttu-id="64068-107">5.0</span><span class="sxs-lookup"><span data-stu-id="64068-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="64068-108">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="64068-108">Change description</span></span>

<span data-ttu-id="64068-109">이전 .NET 버전에서는 <xref:System.Net.Http.WinHttpHandler> 클래스를 핵심 .NET 라이브러리의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64068-109">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="64068-110">.NET 5부터 <xref:System.Net.Http.WinHttpHandler> 클래스는 별도로 설치되는 [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="64068-110">Starting in .NET 5, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="64068-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="64068-111">Recommended action</span></span>

<span data-ttu-id="64068-112">[System.Net.Http.WinHttpHandler NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="64068-112">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="64068-113">또는 WinHTTP 관련 기능이 필요하지 않은 경우 <xref:System.Net.Http.SocketsHttpHandler>를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64068-113">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="64068-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="64068-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
