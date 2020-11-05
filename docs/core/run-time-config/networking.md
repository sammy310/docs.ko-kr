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
# <a name="run-time-configuration-options-for-networking"></a>네트워킹을 위한 런타임 구성 옵션

## <a name="http2-protocol"></a>HTTP/2 프로토콜

- HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.

- .NET Core 3.0에서 도입되었습니다.

- .NET Core 3.0만 해당: 이 설정을 생략하면 HTTP/2 프로토콜에 대한 지원을 사용할 수 없습니다. 이는 값을 `false`로 설정하는 것과 같습니다.

- .NET Core 3.1 및 .NET 5 이상: 이 설정을 생략하면 HTTP/2 프로토콜에 대한 지원을 사용할 수 있습니다. 이는 값을 `true`로 설정하는 것과 같습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` - 사용 안 함<br/>`true` - 사용 |
| **환경 변수** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 또는 이전 HTTP 프로토콜 스택(Windows의 경우 <xref:System.Net.Http.WinHttpHandler> 및 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)의 맨 위에 구현되는 내부 클래스인 `CurlHandler`)을 사용할지 아닌지를 구성합니다.

  > [!NOTE]
  > <xref:System.Net.Http.HttpClientHandler> 클래스를 직접 인스턴스화하는 대신 상위 네트워킹 API를 사용할 수 있습니다. 이 설정은 <xref:System.Net.Http.HttpClient> 및 [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118))를 포함하여 상위 네트워킹 API에서 사용되는 HTTP 프로토콜 스택 종류에도 영향을 줍니다.

- 이 설정을 생략하면 <xref:System.Net.Http.HttpClientHandler>가 <xref:System.Net.Http.SocketsHttpHandler>를 사용합니다. 이는 값을 `true`로 설정하는 것과 같습니다.

- <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정<br/>`false` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다. |
| **환경 변수** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정<br/>`0` - Windows의 경우 <xref:System.Net.Http.WinHttpHandler>를 사용하고 Linux의 경우 [libcurl](https://curl.haxx.se/libcurl/)을 사용할 수 있습니다. |

> [!NOTE]
> .NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.

## <a name="latin1-headers-net-core-31-only"></a>Latin1 헤더(.NET Core 3.1만 해당)

- 이 스위치를 사용하면 HTTP 헤더 유효성 검사를 완화할 수 있으므로 <xref:System.Net.Http.SocketsHttpHandler>가 헤더에서 ISO-8859-1(Latin-1)로 인코딩된 문자를 보낼 수 있습니다.

- 이 설정을 생략하면 ASCII가 아닌 문자를 보내려고 하면 <xref:System.Net.Http.HttpRequestException>이 발생합니다. 이는 값을 `false`로 설정하는 것과 같습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | `false` - 사용 안 함<br/>`true` - 사용 |
| **환경 변수** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | `0` - 사용 안 함<br/>`1` - 사용 |

> [!NOTE]
> 이 옵션은 이전 또는 이후 버전이 아니라 버전 3.1.9 이후 .NET Core 3.1에서만 사용할 수 있습니다. .NET 5에서는 <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>를 사용하는 것이 좋습니다.
