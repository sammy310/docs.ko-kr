---
ms.openlocfilehash: 19359422f79f8240676b0057c7391f6b06f961ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147551"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException이 다른 어셈블리로 이동됨

<xref:System.ComponentModel.InvalidAsynchronousStateException> 클래스가 이동되었습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 2.2 및 이전 버전에서는 <xref:System.ComponentModel.InvalidAsynchronousStateException> 클래스가 *System.ComponentModel.TypeConverter* 어셈블리에 있습니다.

.NET Core 3.0부터는 *System.ComponentModel.Primitives* 어셈블리에 있습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

이 변경은 <xref:System.ComponentModel.InvalidAsynchronousStateException>등의 메서드나 형식이 특정 어셈블리에 있다고 가정하는 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 오버로드를 호출하여 리플렉션을 통해 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>을 로드하는 애플리케이션에만 영향을 줍니다. 이 경우에는 메서드 호출에서 참조된 어셈블리를 형식의 새 어셈블리 위치에 맞게 업데이트해야 합니다.

#### <a name="category"></a>범주

CoreFx

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Affected APIs

- Not detectable via API analysis

-->
