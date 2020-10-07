---
ms.openlocfilehash: d61a3b3dd855d783d7bff7cb74e5b84969e60860
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608052"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="c307a-101">ASP.NET 다중 파트 처리가 잘못되면 양식 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c307a-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="c307a-102">설명</span><span class="sxs-lookup"><span data-stu-id="c307a-102">Details</span></span>

<span data-ttu-id="c307a-103">.NET Framework 4.7.2 이하 버전을 대상으로 하는 애플리케이션에서 ASP.NET이 다중 파트 경계 값을 잘못 구문 분석하면 요청을 수행하는 중에 양식 데이터를 사용할 수 없게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c307a-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.NET might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="c307a-104">.NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션은 다중 파트 데이터를 올바르게 구문 분석하므로 요청을 실행하는 동안 양식 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c307a-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c307a-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c307a-105">Suggestion</span></span>

<span data-ttu-id="c307a-106">.NET Framework 4.8에서 실행되는 애플리케이션부터 <code>targetFrameworkVersion</code> 요소를 사용하여 .NET Framework 4.8 이상을 대상으로 지정하면 기본 동작이 스트립 구분 기호로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c307a-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="c307a-107">이전 프레임워크 버전을 대상으로 하거나 <code>targetFrameworkVersion</code>를 사용하지 않을 때 일부 값에 대한 후행 구분 기호가 여전히 반환됩니다. 이 동작은 <code>appSetting</code>를 사용하여 명시적으로 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c307a-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="c307a-108">이름</span><span class="sxs-lookup"><span data-stu-id="c307a-108">Name</span></span>    | <span data-ttu-id="c307a-109">값</span><span class="sxs-lookup"><span data-stu-id="c307a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c307a-110">Scope</span><span class="sxs-lookup"><span data-stu-id="c307a-110">Scope</span></span>   |<span data-ttu-id="c307a-111">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c307a-111">Unknown</span></span>|
|<span data-ttu-id="c307a-112">버전</span><span class="sxs-lookup"><span data-stu-id="c307a-112">Version</span></span>|<span data-ttu-id="c307a-113">4.8</span><span class="sxs-lookup"><span data-stu-id="c307a-113">4.8</span></span>|
|<span data-ttu-id="c307a-114">형식</span><span class="sxs-lookup"><span data-stu-id="c307a-114">Type</span></span>|<span data-ttu-id="c307a-115">런타임</span><span class="sxs-lookup"><span data-stu-id="c307a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c307a-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c307a-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
