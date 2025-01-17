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
# <a name="winhttphandler-removed-from-net-runtime"></a>.NET 런타임에서 WinHttpHandler 제거됨

`WinHttpHandler` 클래스가 *System.Net.Http.dll* 어셈블리에서 제거되었습니다. 이제 OOB(대역 외) [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 <xref:System.Net.Http.WinHttpHandler> 클래스를 핵심 .NET 라이브러리의 일부로 사용할 수 있습니다. .NET 5부터 <xref:System.Net.Http.WinHttpHandler> 클래스는 별도로 설치되는 [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.

## <a name="recommended-action"></a>권장 조치

[System.Net.Http.WinHttpHandler NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)를 설치합니다. 또는 WinHTTP 관련 기능이 필요하지 않은 경우 <xref:System.Net.Http.SocketsHttpHandler>를 대신 사용합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
