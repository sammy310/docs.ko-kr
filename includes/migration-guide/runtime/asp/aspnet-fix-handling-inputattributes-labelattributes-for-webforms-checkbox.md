---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802671"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>WebForms CheckBox 컨트롤에 대한 InputAttributes 및 LabelAttributes의 ASP.NET Fix 처리

|   |   |
|---|---|
|세부 정보|.NET Framework 4.7.2 이하 버전을 대상으로 하는 애플리케이션의 경우, WebForms <xref:System.Web.UI.WebControls.CheckBox> 컨트롤에 프로그래밍 방식으로 추가된 <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> 및 <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>는 포스트백 후에 손실됩니다. .NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션의 경우, 포스트백 후 그대로 유지됩니다.|
|제안 해결 방법|포스트백에서 특성을 복원하는 올바른 동작을 위해 <code>targetFrameworkVersion</code>를 4.8 이상으로 설정합니다. 예들 들어 다음과 같습니다.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>더 낮게 설정하거나 전혀 설정되지 않으면 이전의 잘못된 동작이 유지됩니다.|
|범위|알 수 없음|
|Version|4.8|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
