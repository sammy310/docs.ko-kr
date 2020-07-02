---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621213"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="ae02e-101">WCF TransportDefaults에서 Ssl3 제거</span><span class="sxs-lookup"><span data-stu-id="ae02e-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="ae02e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ae02e-102">Details</span></span>

<span data-ttu-id="ae02e-103">전송 보안 및 자격 증명 유형의 인증서를 지원하는 NetTcp를 사용할 경우 SSL 3 프로토콜은 더 이상 보안 연결을 협상하는 데 사용되는 기본 프로토콜이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae02e-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="ae02e-104">대부분의 경우 TLS 1.0이 항상 NetTcp에 대한 프로토콜 목록에 포함되어 있으므로 기존 앱에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae02e-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="ae02e-105">모든 기존 클라이언트에서는 TLS 1.0 이상을 사용하여 연결을 협상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae02e-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae02e-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ae02e-106">Suggestion</span></span>

<span data-ttu-id="ae02e-107">Ssl3이 필요한 경우 다음 구성 메커니즘 중 하나를 사용하여 협상된 프로토콜 목록에 Ssl3을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae02e-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="ae02e-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="ae02e-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="ae02e-109">이름</span><span class="sxs-lookup"><span data-stu-id="ae02e-109">Name</span></span>    | <span data-ttu-id="ae02e-110">값</span><span class="sxs-lookup"><span data-stu-id="ae02e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae02e-111">Scope</span><span class="sxs-lookup"><span data-stu-id="ae02e-111">Scope</span></span>   |<span data-ttu-id="ae02e-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae02e-112">Edge</span></span>|
|<span data-ttu-id="ae02e-113">버전</span><span class="sxs-lookup"><span data-stu-id="ae02e-113">Version</span></span>|<span data-ttu-id="ae02e-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="ae02e-114">4.6.2</span></span>|
|<span data-ttu-id="ae02e-115">형식</span><span class="sxs-lookup"><span data-stu-id="ae02e-115">Type</span></span>|<span data-ttu-id="ae02e-116">런타임</span><span class="sxs-lookup"><span data-stu-id="ae02e-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae02e-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ae02e-117">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
