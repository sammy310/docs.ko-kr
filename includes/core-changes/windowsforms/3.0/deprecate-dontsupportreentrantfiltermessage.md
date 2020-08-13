---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556213"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음

.NET Framework 4.6.1에서 도입된 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 호환성 스위치는 .NET Core 및 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.6.1부터는 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현으로 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메시지를 호출할 때 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 호환성 스위치가 가능한 <xref:System.IndexOutOfRangeException> 예외를 해결합니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하십시오.

.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 스위치가 지원되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

스위치를 제거합니다. 이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
