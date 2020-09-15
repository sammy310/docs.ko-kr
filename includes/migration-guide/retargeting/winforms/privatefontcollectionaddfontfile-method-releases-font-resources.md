---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614904"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>PrivateFontCollection.AddFontFile 메서드가 글꼴 리소스를 릴리스함

#### <a name="details"></a>설명

.NET Framework 4.7.1 및 이전 버전에서 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> 메서드를 사용하여 이 컬렉션에 추가된 <xref:System.Drawing.Font> 개체에 대해 <xref:System.Drawing.Text.PrivateFontCollection>를 삭제한 후 <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> 클래스는 GDI+글꼴 리소스를 릴리스하지 않습니다. .NET Framework 4.7.2 이상에서 <xref:System.Drawing.Text.FontCollection.Dispose%2A>은 파일로 컬렉션에 추가된 GDI+글꼴을 릴리스합니다.

#### <a name="suggestion"></a>제안 해결 방법

**이러한 변경을 옵트인 또는 옵트아웃하는 방법**: 애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다. 애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.

- 컴파일되어 .NET Framework 4.7.2를 대상으로 지정합니다. 이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.
- .NET Framework 4.7.1 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

.NET Framework 4.7.2 이상을 대상으로 하고 레거시 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 글꼴 리소스를 릴리스하지 않도록 옵트인할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
