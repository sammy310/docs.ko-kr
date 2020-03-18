---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859190"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="12144-101">WCF 메시지 보안이 이제 TLS1.1 및 TLS1.2를 사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="12144-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="12144-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="12144-102">Details</span></span>|<span data-ttu-id="12144-103">.NET Framework 4.7부터 고객은 애플리케이션 구성 설정을 통해 SSL3.0 및 TLS1.0 외에도 WCF 메시지 보안에 TLS1.1 또는 TLS1.2를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12144-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="12144-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="12144-104">Suggestion</span></span>|<span data-ttu-id="12144-105">.NET Framework 4.7에서는 WCF 메시지 보안의 TLS1.1 및 TLS1.2에 대한 지원은 기본적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12144-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="12144-106">app.config 또는 web.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 행을 추가하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12144-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="12144-107">범위</span><span class="sxs-lookup"><span data-stu-id="12144-107">Scope</span></span>|<span data-ttu-id="12144-108">가장자리</span><span class="sxs-lookup"><span data-stu-id="12144-108">Edge</span></span>|
|<span data-ttu-id="12144-109">Version</span><span class="sxs-lookup"><span data-stu-id="12144-109">Version</span></span>|<span data-ttu-id="12144-110">4.7</span><span class="sxs-lookup"><span data-stu-id="12144-110">4.7</span></span>|
|<span data-ttu-id="12144-111">형식</span><span class="sxs-lookup"><span data-stu-id="12144-111">Type</span></span>|<span data-ttu-id="12144-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="12144-112">Retargeting</span></span>|
