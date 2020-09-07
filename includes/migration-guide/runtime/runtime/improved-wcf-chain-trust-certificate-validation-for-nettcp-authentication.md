---
ms.openlocfilehash: c8f017084fc1ec1eca636ef0178a40559e15b2c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497608"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a><span data-ttu-id="238e3-101">Net.Tcp 인증서 인증에 대한 개선된 WCF 체인 신뢰 인증서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="238e3-101">Improved WCF chain trust certificate validation for Net.Tcp certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="238e3-102">설명</span><span class="sxs-lookup"><span data-stu-id="238e3-102">Details</span></span>

<span data-ttu-id="238e3-103">.NET framework 4.7.2는 WCF 전송 보안으로 인증서 인증을 사용할 때 체인 신뢰 인증서 유효성 검사를 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-103">.NET Framework 4.7.2 improves chain trust certificate validation when using certificate authentication with transport security with WCF.</span></span> <span data-ttu-id="238e3-104">이 개선 사항으로 서버를 인증하는 데 사용되는 클라이언트 인증서는 클라이언트 인증을 위해 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-104">With this improvement, client certificates that are used to authenticate to a server must be configured for client authentication.</span></span>  <span data-ttu-id="238e3-105">마찬가지로 서버를 인증하기 위한 서버 인증서는 서버 인증을 위해 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-105">Similarly server certificates that are for the authenticating a server must be configured for server authentication.</span></span> <span data-ttu-id="238e3-106">이러한 변경으로 인해 루트 인증서가 사용할 수 없게 설정된 경우 인증서 체인 유효성 검사는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-106">With this change, if the root certificate is disabled, the certificate chain validation fails.</span></span> <span data-ttu-id="238e3-107">동일한 변경이 Windows 보안 롤업을 통해 .NET Framework 3.5 이상 버전에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-107">The same change was also made to .NET Framework 3.5 and later versions via Windows security roll-up.</span></span> <span data-ttu-id="238e3-108">자세한 정보는 [여기](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7)에서 찾을 수 있습니다. 이 변경은 기본적으로 활성화되어 있으며 구성 설정을 통해 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-108">You can find more information [here](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7).This change is on by default and can be turned off by a configuration setting.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="238e3-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="238e3-109">Suggestion</span></span>

<ul><li><span data-ttu-id="238e3-110">서버 및 클라이언트 인증에 EKU OID가 필수인지 유효성 검사를 합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-110">Validate if your server and client certification has the required EKU OID.</span></span> <span data-ttu-id="238e3-111">필수가 아니라면 사용자 인증을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-111">If not, update your certification.</span></span></li><li><span data-ttu-id="238e3-112">루트 인증서가 잘못됐는지 유효성 검사를 합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-112">Validate if your root certificate is invalid.</span></span> <span data-ttu-id="238e3-113">잘못됐다면 루트 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-113">If so, update the root certificate.</span></span></li><li><span data-ttu-id="238e3-114">변경을 옵트아웃하는 방법: 인증서를 업데이트할 수 없는 경우 다음 구성 설정으로 호환성이 손상되는 변경을 일시적으로 해결할 수 있습니다. 그러나 변경을 옵트아웃하면 해당 시스템이 보안 문제에 취약하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-114">How to opt out of the change: If you can't update the certificate, you can work around the breaking change temporarily with the following configration setting,  However, opting out of the change will leave your system vulnerable to the security issue.</span></span></li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="238e3-115">이름</span><span class="sxs-lookup"><span data-stu-id="238e3-115">Name</span></span>    | <span data-ttu-id="238e3-116">값</span><span class="sxs-lookup"><span data-stu-id="238e3-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="238e3-117">Scope</span><span class="sxs-lookup"><span data-stu-id="238e3-117">Scope</span></span>   |<span data-ttu-id="238e3-118">부</span><span class="sxs-lookup"><span data-stu-id="238e3-118">Minor</span></span>|
|<span data-ttu-id="238e3-119">버전</span><span class="sxs-lookup"><span data-stu-id="238e3-119">Version</span></span>|<span data-ttu-id="238e3-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="238e3-120">4.7.2</span></span>|
|<span data-ttu-id="238e3-121">형식</span><span class="sxs-lookup"><span data-stu-id="238e3-121">Type</span></span>|<span data-ttu-id="238e3-122">런타임</span><span class="sxs-lookup"><span data-stu-id="238e3-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="238e3-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="238e3-123">Affected APIs</span></span>

<span data-ttu-id="238e3-124">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="238e3-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
