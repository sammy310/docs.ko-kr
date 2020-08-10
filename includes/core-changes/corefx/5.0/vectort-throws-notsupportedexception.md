---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302718"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T>가 지원되지 않는 형식에 대해 항상 NotSupportedException을 throw

<xref:System.Numerics.Vector%601?displayProperty=nameWithType>는 이제 지원되지 않는 형식 매개 변수에 대해 항상 <xref:System.NotSupportedException>을 throw합니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 `T`가 [지원되지 않는 형식](#unsupported-types)인 경우 <xref:System.Numerics.Vector%601>의 멤버가 항상 <xref:System.NotSupportedException>을 throw하지는 않았습니다. 하드웨어 가속을 지원하는 코드 경로 때문에 예외가 throw되지 않는 경우가 있었습니다. 예를 들어 ARM32 같이 하드웨어 가속이 없는 플랫폼에서는 `Vector<bool> + Vector<bool>`가 예외를 throw하는 대신 `default`를 반환했습니다. 지원되지 않는 형식의 경우 <xref:System.Numerics.Vector%601> 멤버는 다양한 플랫폼 및 하드웨어 구성에서 일관되지 않은 동작을 보였습니다.

.NET 5.0부터 <xref:System.Numerics.Vector%601> 멤버는 `T`가 지원되는 형식이 아닌 경우 모든 하드웨어 구성에서 항상 <xref:System.NotSupportedException>을 throw합니다.

##### <a name="unsupported-types"></a>지원되지 않는 형식

<xref:System.Numerics.Vector%601>의 형식 매개 변수에 대해 지원되는 형식은 다음과 같습니다.

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

그러나 지원되는 형식이 변경된 적은 없지만 향후에 변경될 수도 있습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

<xref:System.Numerics.Vector%601>의 형식 매개 변수에 지원되지 않는 형식을 사용하지 마세요.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Numerics.Vector%601?displayProperty=fullName> 및 모든 해당 멤버

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
