---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117112"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine은 사용되지 않습니다

<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수는 .NET Framework에서 [Obsolete](xref:System.ObsoleteAttribute)로 표시되지만 이 특성은 이전에 .NET Core 3.0 라이브러리에서 누락되었습니다.

#### <a name="version-introduced"></a>도입된 버전

.NET Core 3.0 미리 보기 8

#### <a name="details"></a>세부 정보

.NET Core 3.0 미리 보기 8부터 [Obsolete](xref:System.ObsoleteAttribute) 특성은 .NET Framework에서 `vbNewLine`을 준수하기 위해 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수에 적용되었습니다. `vbNewLine` 상수를 사용하면 컴파일러 경고가 생성됩니다. 

이전 버전의 .NET Core에서는 `vbNewLine`이 컴파일러 경고를 생성하지 않았습니다.

#### <a name="recommended-action"></a>권장 작업

`vbNewLine`의 [Obsolete](xref:System.ObsoleteAttribute) 특성 메시지에는 다음 권장 사항이 포함됩니다.

> 캐리지 리턴 및 줄 바꿈의 경우 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)를 사용합니다. 현재 플랫폼의 줄 바꿈의 경우 <xref:System.Environment.NewLine?displayProperty=nameWithType>를 사용합니다.

#### <a name="category"></a>범주

Visual Basic

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

