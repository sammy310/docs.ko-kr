---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857243"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="d1508-101">WCF PipeConnection.GetHashAlgorithm은 이제 SHA256을 사용</span><span class="sxs-lookup"><span data-stu-id="d1508-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d1508-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d1508-102">Details</span></span>|<span data-ttu-id="d1508-103">.NET Framework 4.7.1부터 Windows Communication Foundation은 명명 된 파이프에 대한 임의 이름을 생성하기 위해 SHA256 해시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1508-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="d1508-104">.NET Framework 4.7 및 이전 버전에서는 SHA1 해시를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1508-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="d1508-105">제안</span><span class="sxs-lookup"><span data-stu-id="d1508-105">Suggestion</span></span>|<span data-ttu-id="d1508-106">.NET Framework 4.7.1 이상에서 이러한 변경 내용과의 호환성 문제가 발생하면 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1508-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d1508-107">범위</span><span class="sxs-lookup"><span data-stu-id="d1508-107">Scope</span></span>|<span data-ttu-id="d1508-108">부</span><span class="sxs-lookup"><span data-stu-id="d1508-108">Minor</span></span>|
|<span data-ttu-id="d1508-109">버전</span><span class="sxs-lookup"><span data-stu-id="d1508-109">Version</span></span>|<span data-ttu-id="d1508-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d1508-110">4.7.1</span></span>|
|<span data-ttu-id="d1508-111">형식</span><span class="sxs-lookup"><span data-stu-id="d1508-111">Type</span></span>|<span data-ttu-id="d1508-112">런타임</span><span class="sxs-lookup"><span data-stu-id="d1508-112">Runtime</span></span>|

