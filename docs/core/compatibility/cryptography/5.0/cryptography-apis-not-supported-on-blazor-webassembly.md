---
title: '호환성이 손상되는 변경: Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API'
description: 암호화 API가 브라우저에서 실행될 때 예외를 throw하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759651"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API

<xref:System.Security.Cryptography> API는 브라우저에서 실행될 때 런타임에 <xref:System.PlatformNotSupportedException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 대부분의 <xref:System.Security.Cryptography> API를 Blazor WebAssembly 앱에 사용할 수 없었습니다. .NET 5.0부터 Blazor WebAssembly 앱이 전체 .NET 5 API 노출 영역을 대상으로 하지만, 브라우저 샌드박스 제약 조건으로 인해 일부 .NET 5 API는 지원되지 않습니다. .NET 5.0 이상 버전에서 지원되지 않는 <xref:System.Security.Cryptography> API는 WebAssembly에서 실행될 때 <xref:System.PlatformNotSupportedException>을 throw합니다.

> [!TIP]
> [플랫폼 호환성 분석기](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md)는 브라우저 플랫폼을 지원하는 프로젝트를 빌드할 때 영향을 받는 API에 대한 모든 호출에 플래그를 지정합니다. 이 분석기는 .NET 5.0 이상 앱에서 기본적으로 실행됩니다.

## <a name="reason-for-change"></a>변경 이유

Microsoft는 Blazor WebAssembly 구성에서 OpenSSL을 종속성으로 제공할 수 없습니다. 브라우저의 `SubtleCrypto` API와 통합하여 이 문제를 해결하려고 했지만, 안타깝게도 상당한 API 변경이 필요하여 통합이 어려웠습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

지금은 제안할 수 있는 유용한 해결 방법이 없습니다.

## <a name="affected-apis"></a>영향을 받는 API

다음을 제외한 모든 <xref:System.Security.Cryptography?displayProperty=fullName> API:

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
