---
title: 네트워크 구성 설정
description: .NET Core 앱의 네트워킹을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989105"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="02161-103">네트워킹을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="02161-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="02161-104">HTTP/2 프로토콜</span><span class="sxs-lookup"><span data-stu-id="02161-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="02161-105">HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="02161-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="02161-106">기본값: 사용 안 함(`false`).</span><span class="sxs-lookup"><span data-stu-id="02161-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="02161-107">.NET Core 3.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="02161-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="02161-108">Setting name</span></span> | <span data-ttu-id="02161-109">값</span><span class="sxs-lookup"><span data-stu-id="02161-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="02161-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="02161-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="02161-111">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="02161-111">`false` - disabled</span></span><br/><span data-ttu-id="02161-112">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="02161-112">`true` - enabled</span></span> |
| <span data-ttu-id="02161-113">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="02161-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="02161-114">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="02161-114">`0` - disabled</span></span><br/><span data-ttu-id="02161-115">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="02161-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="02161-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="02161-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="02161-117"><xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 또는 이전 HTTP 프로토콜 스택(Windows의 경우 <xref:System.Net.Http.WinHttpHandler> 및 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)의 맨 위에 구현되는 내부 클래스인 `CurlHandler`)을 사용할지 아닌지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="02161-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="02161-118"><xref:System.Net.Http.HttpClientHandler> 클래스를 직접 인스턴스화하는 대신 상위 네트워킹 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="02161-119">이 설정은 <xref:System.Net.Http.HttpClient> 및 [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118))를 포함하여 상위 네트워킹 API에서 사용되는 HTTP 프로토콜 스택 종류에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02161-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="02161-120">기본값: <xref:System.Net.Http.SocketsHttpHandler> 사용(`true`).</span><span class="sxs-lookup"><span data-stu-id="02161-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="02161-121"><xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="02161-122">설정 이름</span><span class="sxs-lookup"><span data-stu-id="02161-122">Setting name</span></span> | <span data-ttu-id="02161-123">값</span><span class="sxs-lookup"><span data-stu-id="02161-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="02161-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="02161-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="02161-125">`true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="02161-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="02161-126">`false` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="02161-127">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="02161-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="02161-128">`1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="02161-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="02161-129">`0` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="02161-130">.NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02161-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
