---
title: 네트워크 구성 설정
description: .NET Core 앱의 네트워킹을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188304"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="4b92e-103">네트워킹을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="4b92e-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="4b92e-104">HTTP/2 프로토콜</span><span class="sxs-lookup"><span data-stu-id="4b92e-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="4b92e-105">HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="4b92e-106">.NET Core 3.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-106">Introduced in .NET Core 3.0.</span></span>

- <span data-ttu-id="4b92e-107">.NET Core 3.0만 해당: 이 설정을 생략하면 HTTP/2 프로토콜에 대한 지원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-107">.NET Core 3.0 only: If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="4b92e-108">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-108">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="4b92e-109">.NET Core 3.1 및 .NET 5 이상: 이 설정을 생략하면 HTTP/2 프로토콜에 대한 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-109">.NET Core 3.1 and .NET 5+: If you omit this setting, support for the HTTP/2 protocol is enabled.</span></span> <span data-ttu-id="4b92e-110">이는 값을 `true`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-110">This is equivalent to setting the value to `true`.</span></span>

| | <span data-ttu-id="4b92e-111">설정 이름</span><span class="sxs-lookup"><span data-stu-id="4b92e-111">Setting name</span></span> | <span data-ttu-id="4b92e-112">값</span><span class="sxs-lookup"><span data-stu-id="4b92e-112">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4b92e-113">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b92e-113">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="4b92e-114">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4b92e-114">`false` - disabled</span></span><br/><span data-ttu-id="4b92e-115">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="4b92e-115">`true` - enabled</span></span> |
| <span data-ttu-id="4b92e-116">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="4b92e-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="4b92e-117">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4b92e-117">`0` - disabled</span></span><br/><span data-ttu-id="4b92e-118">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="4b92e-118">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="4b92e-119">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="4b92e-119">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="4b92e-120"><xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 또는 이전 HTTP 프로토콜 스택(Windows의 경우 <xref:System.Net.Http.WinHttpHandler> 및 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)의 맨 위에 구현되는 내부 클래스인 `CurlHandler`)을 사용할지 아닌지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-120">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="4b92e-121"><xref:System.Net.Http.HttpClientHandler> 클래스를 직접 인스턴스화하는 대신 상위 네트워킹 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-121">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="4b92e-122">이 설정은 <xref:System.Net.Http.HttpClient> 및 [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118))를 포함하여 상위 네트워킹 API에서 사용되는 HTTP 프로토콜 스택 종류에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-122">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="4b92e-123">이 설정을 생략하면 <xref:System.Net.Http.HttpClientHandler>가 <xref:System.Net.Http.SocketsHttpHandler>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-123">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="4b92e-124">이는 값을 `true`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-124">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="4b92e-125"><xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-125">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="4b92e-126">설정 이름</span><span class="sxs-lookup"><span data-stu-id="4b92e-126">Setting name</span></span> | <span data-ttu-id="4b92e-127">값</span><span class="sxs-lookup"><span data-stu-id="4b92e-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4b92e-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b92e-128">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="4b92e-129">`true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4b92e-129">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="4b92e-130">`false` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-130">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="4b92e-131">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="4b92e-131">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="4b92e-132">`1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4b92e-132">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="4b92e-133">`0` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-133">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="4b92e-134">.NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-134">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>

## <a name="latin1-headers-net-core-31-only"></a><span data-ttu-id="4b92e-135">Latin1 헤더(.NET Core 3.1만 해당)</span><span class="sxs-lookup"><span data-stu-id="4b92e-135">Latin1 headers (.NET Core 3.1 only)</span></span>

- <span data-ttu-id="4b92e-136">이 스위치를 사용하면 HTTP 헤더 유효성 검사를 완화할 수 있으므로 <xref:System.Net.Http.SocketsHttpHandler>가 헤더에서 ISO-8859-1(Latin-1)로 인코딩된 문자를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-136">This switch allows relaxing the HTTP header validation, enabling <xref:System.Net.Http.SocketsHttpHandler> to send ISO-8859-1 (Latin-1) encoded characters in headers.</span></span>

- <span data-ttu-id="4b92e-137">이 설정을 생략하면 ASCII가 아닌 문자를 보내려고 하면 <xref:System.Net.Http.HttpRequestException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-137">If you omit this setting, an attempt to send a non-ASCII character will result in <xref:System.Net.Http.HttpRequestException>.</span></span> <span data-ttu-id="4b92e-138">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-138">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="4b92e-139">설정 이름</span><span class="sxs-lookup"><span data-stu-id="4b92e-139">Setting name</span></span> | <span data-ttu-id="4b92e-140">값</span><span class="sxs-lookup"><span data-stu-id="4b92e-140">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4b92e-141">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b92e-141">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | <span data-ttu-id="4b92e-142">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4b92e-142">`false` - disabled</span></span><br/><span data-ttu-id="4b92e-143">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="4b92e-143">`true` - enabled</span></span> |
| <span data-ttu-id="4b92e-144">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="4b92e-144">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | <span data-ttu-id="4b92e-145">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4b92e-145">`0` - disabled</span></span><br/><span data-ttu-id="4b92e-146">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="4b92e-146">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="4b92e-147">이 옵션은 이전 또는 이후 버전이 아니라 버전 3.1.9 이후 .NET Core 3.1에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-147">This option is only available in .NET Core 3.1 since version 3.1.9, and not in previous or later versions.</span></span> <span data-ttu-id="4b92e-148">.NET 5에서는 <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b92e-148">In .NET 5 we recommend using <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span></span>
