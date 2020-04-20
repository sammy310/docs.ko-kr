---
ms.openlocfilehash: fa2a856911c7dcf81a39b7682a62a86c35328037
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274760"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="08c19-101">addressHeader 요소가 null인 경우 이제 WCF AddressHeaderCollection이 ArgumentException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="08c19-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

|   |   |
|---|---|
|<span data-ttu-id="08c19-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="08c19-102">Details</span></span>|<span data-ttu-id="08c19-103">.NET Framework 4.7.1부터 요소 중 하나가 <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>이면 <xref:System.ArgumentException> 생성자가 <code>null</code>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="08c19-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="08c19-104">.NET Framework 4.7 및 이전 버전에서 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08c19-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>|
|<span data-ttu-id="08c19-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="08c19-105">Suggestion</span></span>|<span data-ttu-id="08c19-106">.NET Framework 4.7.1 또는 이후 버전에서 이러한 변경으로 인해 호환성 문제가 발생하는 경우 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c19-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="08c19-107">범위</span><span class="sxs-lookup"><span data-stu-id="08c19-107">Scope</span></span>|<span data-ttu-id="08c19-108">사소함</span><span class="sxs-lookup"><span data-stu-id="08c19-108">Minor</span></span>|
|<span data-ttu-id="08c19-109">Version</span><span class="sxs-lookup"><span data-stu-id="08c19-109">Version</span></span>|<span data-ttu-id="08c19-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="08c19-110">4.7.1</span></span>|
|<span data-ttu-id="08c19-111">형식</span><span class="sxs-lookup"><span data-stu-id="08c19-111">Type</span></span>|<span data-ttu-id="08c19-112">런타임</span><span class="sxs-lookup"><span data-stu-id="08c19-112">Runtime</span></span>|
|<span data-ttu-id="08c19-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="08c19-113">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
