---
ms.openlocfilehash: d1562cb76f37b6cc2aeb6fe2f7c17c393e169e84
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158482"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException이 다른 어셈블리로 이동됨

<xref:System.ComponentModel.InvalidAsynchronousStateException> 클래스가 이동되었습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 2.2 및 이전 버전에서는 <xref:System.ComponentModel.InvalidAsynchronousStateException> 클래스가 *System.ComponentModel.TypeConverter* 어셈블리에 있습니다.

.NET Core 3.0부터는 *System.ComponentModel.Primitives* 어셈블리에 있습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

이 변경은 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>등의 메서드나 형식이 특정 어셈블리에 있다고 가정하는 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 오버로드를 호출하여 리플렉션을 통해 <xref:System.ComponentModel.InvalidAsynchronousStateException>을 로드하는 애플리케이션에만 영향을 줍니다. 이 경우에는 메서드 호출에서 참조된 어셈블리를 업데이트하여 형식의 새 어셈블리 위치를 반영합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Affected APIs

- Not detectable via API analysis

-->
