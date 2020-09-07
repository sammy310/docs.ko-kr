---
ms.openlocfilehash: 200c22a1b83149d833a083365ebb65d0e80bc31a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497114"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="383dc-101">addressHeader 요소가 null인 경우 이제 WCF AddressHeaderCollection이 ArgumentException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="383dc-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="383dc-102">설명</span><span class="sxs-lookup"><span data-stu-id="383dc-102">Details</span></span>

<span data-ttu-id="383dc-103">.NET Framework 4.7.1부터 요소 중 하나가 <code>null</code>이면 <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> 생성자가 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="383dc-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="383dc-104">.NET Framework 4.7 및 이전 버전에서 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="383dc-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="383dc-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="383dc-105">Suggestion</span></span>

<span data-ttu-id="383dc-106">.NET Framework 4.7.1 또는 이후 버전에서 이러한 변경으로 인해 호환성 문제가 발생하는 경우 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="383dc-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="383dc-107">Name</span><span class="sxs-lookup"><span data-stu-id="383dc-107">Name</span></span>    | <span data-ttu-id="383dc-108">값</span><span class="sxs-lookup"><span data-stu-id="383dc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="383dc-109">Scope</span><span class="sxs-lookup"><span data-stu-id="383dc-109">Scope</span></span>   |<span data-ttu-id="383dc-110">부</span><span class="sxs-lookup"><span data-stu-id="383dc-110">Minor</span></span>|
|<span data-ttu-id="383dc-111">버전</span><span class="sxs-lookup"><span data-stu-id="383dc-111">Version</span></span>|<span data-ttu-id="383dc-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="383dc-112">4.7.1</span></span>|
|<span data-ttu-id="383dc-113">형식</span><span class="sxs-lookup"><span data-stu-id="383dc-113">Type</span></span>|<span data-ttu-id="383dc-114">런타임</span><span class="sxs-lookup"><span data-stu-id="383dc-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="383dc-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="383dc-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
