---
ms.openlocfilehash: 8964cd2f69e95e4078001997ad5a5d126ce42d7b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497286"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="31b7b-101">KeyedCollection에 대한 데이터 바인딩 개선</span><span class="sxs-lookup"><span data-stu-id="31b7b-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="31b7b-102">설명</span><span class="sxs-lookup"><span data-stu-id="31b7b-102">Details</span></span>

<span data-ttu-id="31b7b-103">원본 개체가 동일한 서명(예: KeyedCollection&lt;int,TItem&gt;)이 있는 사용자 지정 인덱서를 선언할 때 IList 인덱서가 잘못 사용된 <xref:System.Windows.Data.Binding>을 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7b-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="31b7b-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="31b7b-104">Suggestion</span></span>

<span data-ttu-id="31b7b-105">이전 버전을 대상으로 하는 애플리케이션에서 이 변경의 이점을 활용하려면 .NET Framework 4.8 이상에서 실행해야 하며, 앱 구성 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음과 같은 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하여 변경 내용을 옵트인하고 <code>false</code>로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7b-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="31b7b-106">이름</span><span class="sxs-lookup"><span data-stu-id="31b7b-106">Name</span></span>    | <span data-ttu-id="31b7b-107">값</span><span class="sxs-lookup"><span data-stu-id="31b7b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="31b7b-108">Scope</span><span class="sxs-lookup"><span data-stu-id="31b7b-108">Scope</span></span>   |<span data-ttu-id="31b7b-109">주요함</span><span class="sxs-lookup"><span data-stu-id="31b7b-109">Major</span></span>|
|<span data-ttu-id="31b7b-110">버전</span><span class="sxs-lookup"><span data-stu-id="31b7b-110">Version</span></span>|<span data-ttu-id="31b7b-111">4.8</span><span class="sxs-lookup"><span data-stu-id="31b7b-111">4.8</span></span>|
|<span data-ttu-id="31b7b-112">형식</span><span class="sxs-lookup"><span data-stu-id="31b7b-112">Type</span></span>|<span data-ttu-id="31b7b-113">런타임</span><span class="sxs-lookup"><span data-stu-id="31b7b-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="31b7b-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="31b7b-114">Affected APIs</span></span>

<span data-ttu-id="31b7b-115">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7b-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
