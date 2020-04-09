---
title: 네트워크 구성 설정
description: .NET Core 앱의 네트워킹을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635420"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="67e8b-103">네트워킹을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="67e8b-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="67e8b-104">HTTP/2 프로토콜</span><span class="sxs-lookup"><span data-stu-id="67e8b-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="67e8b-105">HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="67e8b-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="67e8b-106">기본값: 사용 안 함(`false`).</span><span class="sxs-lookup"><span data-stu-id="67e8b-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="67e8b-107">.NET Core 3.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67e8b-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="67e8b-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="67e8b-108">Setting name</span></span> | <span data-ttu-id="67e8b-109">값</span><span class="sxs-lookup"><span data-stu-id="67e8b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="67e8b-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="67e8b-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="67e8b-111">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="67e8b-111">`false` - disabled</span></span><br/><span data-ttu-id="67e8b-112">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="67e8b-112">`true` - enabled</span></span> |
| <span data-ttu-id="67e8b-113">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="67e8b-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="67e8b-114">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="67e8b-114">`0` - disabled</span></span><br/><span data-ttu-id="67e8b-115">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="67e8b-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="67e8b-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="67e8b-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="67e8b-117"><xref:System.Net.Http.HttpClient>와 같은 하이레벨 네트워킹 API가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>를 사용하는지 아니면 [libcurl](https://curl.haxx.se/libcurl/) 기반의 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 구현을 사용하는지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="67e8b-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="67e8b-118">기본값: <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 사용(`true`).</span><span class="sxs-lookup"><span data-stu-id="67e8b-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="67e8b-119"><xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e8b-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="67e8b-120">설정 이름</span><span class="sxs-lookup"><span data-stu-id="67e8b-120">Setting name</span></span> | <span data-ttu-id="67e8b-121">값</span><span class="sxs-lookup"><span data-stu-id="67e8b-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="67e8b-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="67e8b-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="67e8b-123">`true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="67e8b-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="67e8b-124">`false` - <xref:System.Net.Http.HttpClientHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="67e8b-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="67e8b-125">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="67e8b-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="67e8b-126">`1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="67e8b-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="67e8b-127">`0` - <xref:System.Net.Http.HttpClientHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="67e8b-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |

> [!NOTE]
> <span data-ttu-id="67e8b-128">.NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67e8b-128">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
