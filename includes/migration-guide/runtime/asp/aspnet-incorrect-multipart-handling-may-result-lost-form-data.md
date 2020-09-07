---
ms.openlocfilehash: ed669364efe9dd8f57d831a3764dd3fc68cd5e05
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496335"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>ASP.NET 다중 파트 처리가 잘못되면 양식 데이터가 손실될 수 있습니다.

#### <a name="details"></a>설명

.NET Framework 4.7.2 이하 버전을 대상으로 하는 애플리케이션에서 ASP.Net이 다중 파트 경계 값을 잘못 구문 분석하면 요청을 수행하는 중에 양식 데이터를 사용할 수 없게 될 수 있습니다. .NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션은 다중 파트 데이터를 올바르게 구문 분석하므로 요청을 실행하는 동안 양식 값을 사용할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.8에서 실행되는 애플리케이션부터 <code>targetFrameworkVersion</code> 요소를 사용하여 .NET Framework 4.8 이상을 대상으로 지정하면 기본 동작이 스트립 구분 기호로 변경됩니다. 이전 프레임워크 버전을 대상으로 하거나 <code>targetFrameworkVersion</code>를 사용하지 않을 때 일부 값에 대한 후행 구분 기호가 여전히 반환됩니다. 이 동작은 <code>appSetting</code>를 사용하여 명시적으로 제어할 수도 있습니다.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   |알 수 없음|
|버전|4.8|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
