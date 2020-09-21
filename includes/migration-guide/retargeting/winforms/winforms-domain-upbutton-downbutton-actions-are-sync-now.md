---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606400"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>WinForm의 도메인 UpButton 및 DownButton 작업이 지금 동기화됨

#### <a name="details"></a>설명

.NET Framework 4.7.1 및 이전 버전에서 <xref:System.Windows.Forms.DomainUpDown> 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업은 컨트롤 텍스트가 존재하고 개발자에게 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 사용하기 전에 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 사용하도록 요구하는 경우 무시됩니다. .NET Framework 4.7.2부터 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업 모두 이 시나리오에서 독립적으로 작동하고 동기화 상태로 유지됩니다.

#### <a name="suggestion"></a>제안 해결 방법

애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다. 애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.

- 컴파일되어 .NET Framework 4.7.2를 대상으로 지정합니다. 이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.
- 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하고 이를 `false`로 설정하여 레거시 스크롤 동작을 옵트아웃합니다.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
