---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615713"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap은 PNG 프레임이 있는 아이콘을 Bitmap 개체로 성공적으로 변환합니다.

#### <a name="details"></a>세부 정보

.NET Framework 4.6을 대상으로 하는 앱부터는 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 PNG 프레임이 있는 아이콘을 Bitmap 개체로 올바르게 변환합니다.<p/>.NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 Icon 개체에 PNG 프레임이 있는 경우 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 <xref:System.ArgumentOutOfRangeException> 예외를 throw합니다.<p/>이 변경은 Icon 개체에 PNG 프레임이 있을 때 throw되는 <xref:System.ArgumentOutOfRangeException>에 대해 특수 처리를 구현하고 .NET Framework 4.6을 대상으로 다시 컴파일되는 앱에 영향을 줍니다. .NET Framework 4.6에서 실행되는 경우 변환이 성공하고 <xref:System.ArgumentOutOfRangeException> 이 더 이상 throw되지 않습니다. 따라서 예외 처리기가 더 이상 호출되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 동작이 필요 없는 경우 app.config 파일의 `<runtime>` 섹션에 다음 요소를 추가하여 이전 동작을 유지할 수 있습니다.

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

App.config 파일에 이미 `AppContextSwitchOverrides` 요소가 포함되어 있는 경우 새 값은 다음과 같이 값 특성과 병합되어야 합니다.

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
