---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614722"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream은 압축 풀기에 네이티브 API를 사용합니다.

#### <a name="details"></a>설명

.NET Framework 4.7.2부터 `T:System.IO.Compression.DeflateStream` 클래스에서 압축 풀기의 구현은 기본적으로 네이티브 Windows API를 사용하는 것으로 변경되었습니다. 일반적으로 이로 인해 성능이 크게 향상됩니다. .NET Framework 버전 4.7.2 이상을 대상으로 하는 모든 .NET 애플리케이션은 네이티브 구현을 사용합니다. 이 변경 내용으로 인해 다음을 포함하여 동작에 일부 차이점이 발생할 수 있습니다.

- 예외 메시지는 달라질 수 있습니다. 그러나 throw된 예외의 형식은 유지됩니다.
- 작업을 완료하는 데 메모리가 충분하지 않은 것과 같은 일부 특수한 상황은 다르게 처리될 수 있습니다.
- gzip 헤더를 구문 분석하는 데 알려진 차이점이 있습니다(참고: 압축 풀기에 대한 `GZipStream` 설정만 영향을 받음).
- 잘못된 헤더를 구분 분석하는 경우 예외는 서로 다른 시간에 throw될 수 있습니다.
- 네이티브 구현은 gzip 헤더 내부의 일부 예약된 플래그에 대한 값(즉, [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer))이 사양에 따라 설정되도록 적용합니다. 이로 인해 이전에 잘못된 값이 무시되었던 예외를 throw할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

네이티브 API를 사용하는 압축 풀기가 앱의 동작에 부정적으로 영향을 준 경우 app.config 파일의 `runtime` 섹션에 `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` 스위치를 추가하고 `true`로 설정하여 이 기능을 옵트아웃할 수 있습니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
