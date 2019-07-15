---
ms.openlocfilehash: 3b7b50700541649a785fa9bbe3ecc56c2697fbfc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859190"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="3efd0-101">WCF 메시지 보안이 이제 TLS1.1 및 TLS1.2를 사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="3efd0-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3efd0-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3efd0-102">Details</span></span>|<span data-ttu-id="3efd0-103">.NET Framework 4.7부터 고객은 애플리케이션 구성 설정을 통해 SSL3.0 및 TLS1.0 외에도 WCF 메시지 보안에 TLS1.1 또는 TLS1.2를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3efd0-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="3efd0-104">제안</span><span class="sxs-lookup"><span data-stu-id="3efd0-104">Suggestion</span></span>|<span data-ttu-id="3efd0-105">.NET Framework 4.7에서는 WCF 메시지 보안의 TLS1.1 및 TLS1.2에 대한 지원은 기본적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3efd0-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="3efd0-106">app.config 또는 web.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 행을 추가하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3efd0-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="3efd0-107">범위</span><span class="sxs-lookup"><span data-stu-id="3efd0-107">Scope</span></span>|<span data-ttu-id="3efd0-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3efd0-108">Edge</span></span>|
|<span data-ttu-id="3efd0-109">버전</span><span class="sxs-lookup"><span data-stu-id="3efd0-109">Version</span></span>|<span data-ttu-id="3efd0-110">4.7</span><span class="sxs-lookup"><span data-stu-id="3efd0-110">4.7</span></span>|
|<span data-ttu-id="3efd0-111">형식</span><span class="sxs-lookup"><span data-stu-id="3efd0-111">Type</span></span>|<span data-ttu-id="3efd0-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="3efd0-112">Retargeting</span></span>|

