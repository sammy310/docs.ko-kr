---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394191"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>캐싱: CompactOnMemoryPressure 속성이 제거됨

ASP.NET Core 3.0 릴리스에서는 [사용되지 않는 MemoryCacheOptions API](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)를 제거했습니다.

#### <a name="change-description"></a>변경 내용 설명

이 변경 내용은 [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221)에 대한 후속 작업입니다. 자세한 내용은 [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`MemoryCacheOptions.CompactOnMemoryPressure` 속성을 사용할 수 있었습니다.

#### <a name="new-behavior"></a>새 동작

`MemoryCacheOptions.CompactOnMemoryPressure` 속성이 제거되었습니다.

#### <a name="reason-for-change"></a>변경 이유

자동으로 캐시를 압축하면 문제가 발생합니다. 예기치 않은 동작을 방지하려면 필요한 경우에만 캐시를 압축해야 합니다.

#### <a name="recommended-action"></a>권장 작업

캐시를 압축하려면 `MemoryCache`를 다운캐스트하고 필요한 경우 `Compact`를 호출합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
