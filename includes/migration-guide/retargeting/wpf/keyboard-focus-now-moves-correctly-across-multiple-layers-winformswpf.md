---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614946"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>키보드 포커스는 이제 WinForms/WPF 호스팅의 여러 계층에서 제대로 이동합니다.

#### <a name="details"></a>설명

차례로 WPF 컨트롤을 호스트하는 WinForms 컨트롤을 호스팅하는 WPF 애플리케이션을 고려합니다. 사용자는 해당 계층의 첫 번째 또는 마지막 컨트롤이 WPF `System.Windows.Forms.Integration.ElementHost`이면 WinForms 계층에서 이동할 수 없습니다. 이 변경 내용은 이 문제를 해결하고, 사용자는 이제 WinForms 계층에서 이동할 수 있습니다. WinForms 계층을 이스케이프하지 않는 포커스를 사용하는 자동화된 애플리케이션은 더 이상 예상대로 작동하지 않을 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET 4.7.2 이전의 프레임워크 버전을 대상으로 하는 동안 이 변경 내용을 활용하려는 개발자는 변경 내용을 활성화하기 위해 false로 AppContext 플래그의 다음 집합을 설정할 수 있습니다.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

WPF 애플리케이션은 최신 개선 사항을 가져오도록 모든 초기 접근성 개선 사항으로 옵트인해야 합니다. 즉, `Switch.UseLegacyAccessibilityFeatures` 및 `Switch.UseLegacyAccessibilityFeatures.2` 스위치 모두는 .NET 4.7.2 이상을 대상으로 하는 동안 이전 기능을 필요로 하는 A 개발자가 변경 내용을 활성화하지 못하도록 다음 AppContext 플래그를 true로 설정할 수 있도록 설정해야 합니다.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |
