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
# <a name="run-time-configuration-options-for-networking"></a>네트워킹을 위한 런타임 구성 옵션

## <a name="http2-protocol"></a>HTTP/2 프로토콜

- HTTP/2 프로토콜 지원을 사용할지 여부를 구성합니다.
- 기본값: 사용 안 함(`false`).
- .NET Core 3.0에서 도입되었습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` - 사용 안 함<br/>`true` - 사용 |
| **환경 변수** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- <xref:System.Net.Http.HttpClient>와 같은 하이레벨 네트워킹 API가 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>를 사용하는지 아니면 [libcurl](https://curl.haxx.se/libcurl/) 기반의 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 구현을 사용하는지를 구성합니다.
- 기본값: <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 사용(`true`).
- <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 이 설정을 프로그래밍 방식으로 구성할 수 있습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정<br/>`false` - <xref:System.Net.Http.HttpClientHandler>를 사용하도록 설정 |
| **환경 변수** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` - <xref:System.Net.Http.SocketsHttpHandler>를 사용하도록 설정<br/>`0` - <xref:System.Net.Http.HttpClientHandler>를 사용하도록 설정 |

> [!NOTE]
> .NET 5부터 `System.Net.Http.UseSocketsHttpHandler` 설정을 더 이상 사용할 수 없습니다.
