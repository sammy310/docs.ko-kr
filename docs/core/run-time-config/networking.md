---
title: 네트워크 구성 설정
description: .NET Core 앱의 네트워킹을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761943"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="5dba5-103">네트워킹을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="5dba5-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="5dba5-104">HTTP/2 프로토콜</span><span class="sxs-lookup"><span data-stu-id="5dba5-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="5dba5-105">HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="5dba5-106">이 설정을 생략하면 HTTP/2 프로토콜에 대한 지원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="5dba5-107">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="5dba5-108">.NET Core 3.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="5dba5-109">설정 이름</span><span class="sxs-lookup"><span data-stu-id="5dba5-109">Setting name</span></span> | <span data-ttu-id="5dba5-110">값</span><span class="sxs-lookup"><span data-stu-id="5dba5-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5dba5-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5dba5-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="5dba5-112">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5dba5-112">`false` - disabled</span></span><br/><span data-ttu-id="5dba5-113">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="5dba5-113">`true` - enabled</span></span> |
| <span data-ttu-id="5dba5-114">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="5dba5-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="5dba5-115">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5dba5-115">`0` - disabled</span></span><br/><span data-ttu-id="5dba5-116">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="5dba5-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="5dba5-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="5dba5-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="5dba5-118"><xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 또는 이전 HTTP 프로토콜 스택(Windows의 경우 <xref:System.Net.Http.WinHttpHandler> 및 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)의 맨 위에 구현되는 내부 클래스인 `CurlHandler`)을 사용할지 아닌지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="5dba5-119"><xref:System.Net.Http.HttpClientHandler> 클래스를 직접 인스턴스화하는 대신 상위 네트워킹 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="5dba5-120">이 설정은 <xref:System.Net.Http.HttpClient> 및 [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118))를 포함하여 상위 네트워킹 API에서 사용되는 HTTP 프로토콜 스택 종류에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="5dba5-121">이 설정을 생략하면 <xref:System.Net.Http.HttpClientHandler>가 <xref:System.Net.Http.SocketsHttpHandler>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="5dba5-122">이는 값을 `true`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="5dba5-123"><xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5dba5-124">설정 이름</span><span class="sxs-lookup"><span data-stu-id="5dba5-124">Setting name</span></span> | <span data-ttu-id="5dba5-125">값</span><span class="sxs-lookup"><span data-stu-id="5dba5-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5dba5-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5dba5-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="5dba5-127">`true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5dba5-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="5dba5-128">`false` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="5dba5-129">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="5dba5-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="5dba5-130">`1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5dba5-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="5dba5-131">`0` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="5dba5-132">.NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5dba5-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
