---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617167"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode 및 WebUtility.HtmlDecode가 BMP를 올바르게 라운드트립

#### <a name="details"></a>설명

.NET Framework 4.5를 대상으로 하는 애플리케이션의 경우 BMP(기본적인 다국어 문자표) 외의 문자는 <xref:System.Net.WebUtility.HtmlDecode(System.String)> 메서드에 전달될 때 올바르게 라운드트립합니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경은 현재 애플리케이션에 영향을 주지 않지만, 원래의 동작을 복원하려면 `<httpRuntime>` 요소의 `targetFramework` 특성을 “4.5” 이외의 문자열로 설정합니다. `unicodeEncodingConformance` 구성 요소의 `unicodeDecodingConformance` 및 `<webUtility>` 특성을 설정하여 대상 버전의 .NET Framework에 관계없이 이 동작을 제어할 수도 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.5         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
