---
ms.openlocfilehash: 072ed716910e2e1f1f98dbddc56d5bd097b75acc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555914"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine은 사용되지 않습니다

<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수는 .NET Core 3.0부터 [\[사용되지 않음\]](xref:System.ObsoleteAttribute)으로 표시됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.0부터 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수에 [Obsolete](xref:System.ObsoleteAttribute) 특성이 적용되었습니다. 이 상수를 사용하면 컴파일러 경고가 생성됩니다. .NET Framework 및 .NET Core의 이전 릴리스에서는 사용되지 않음으로 표시되지 않았습니다.

이 변경은 다중 플랫폼 개발 언어로 Visual Basic을 지원하기 위해 적용된 것입니다. <xref:Microsoft.VisualBasic.Constants.vbNewLine> 상수는 Windows의 줄 바꿈 문자 시퀀스인 `\r\n`과 동일합니다. Unix 기반 시스템에서 줄 바꿈 문자는 `\n`입니다.

#### <a name="recommended-action"></a>권장 조치

<xref:Microsoft.VisualBasic.Constants.vbNewLine>의 [Obsolete](xref:System.ObsoleteAttribute) 특성 메시지에는 다음 권장 사항이 포함됩니다.

캐리지 리턴 및 줄 바꿈의 경우 <xref:Microsoft.VisualBasic.Constants.vbCrLf>를 사용합니다. 현재 플랫폼의 줄 바꿈의 경우 <xref:System.Environment.NewLine?displayProperty=nameWithType>를 사용합니다.

#### <a name="category"></a>범주

Visual Basic

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
