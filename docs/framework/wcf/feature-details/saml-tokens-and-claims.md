---
title: SAML 토큰 및 클레임
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
ms.openlocfilehash: 04517e5089f55c2d2b08a492439026d33ed9069d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339842"
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="d8b29-102">SAML 토큰 및 클레임</span><span class="sxs-lookup"><span data-stu-id="d8b29-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="d8b29-103">SAML security Assertions Markup Language () *토큰* 클레임의 XML 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="d8b29-104">Windows Communication Foundation (WCF) 페더레이션된 보안 시나리오에서 사용 하 여 SAML 토큰에는 기본적으로 *발급 된 토큰*합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-104">By default, SAML tokens Windows Communication Foundation (WCF) uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="d8b29-105">SAML 토큰은 하나의 엔터티에서 다른 엔터티에 대해 만든 클레임 집합인 문을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="d8b29-106">예를 들어, 페더레이션 보안 시나리오의 경우 시스템의 사용자에 대한 보안 토큰 서비스에서 문을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="d8b29-107">보안 토큰 서비스에서는 토큰에 포함된 문의 정확성을 나타내기 위해 SAML 토큰을 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="d8b29-108">또한 SAML 토큰은 암호화 키 자료와 연결되어 있으며, 이 때 SAML 토큰의 사용자는 해당 키 자료를 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="d8b29-109">이 증명은 신뢰하는 상대에게 SAML 토큰이 실제로 해당 사용자에게 발행되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="d8b29-110">예를 들어, 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-110">For example, in a typical scenario:</span></span>  
  
1. <span data-ttu-id="d8b29-111">클라이언트는 보안 토큰 서비스에서 SAML 토큰을 요청하고 Windows 자격 증명을 사용하여 해당 보안 토큰 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2. <span data-ttu-id="d8b29-112">보안 토큰 서비스는 SAML 토큰을 클라이언트에 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="d8b29-113">SAML 토큰은 보안 토큰 서비스와 연결된 인증서를 통해 서명되며, 대상 서비스에 대해 암호화된 증명 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3. <span data-ttu-id="d8b29-114">클라이언트의 복사본을 수신 합니다 *증명 키*합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="d8b29-115">클라이언트 응용 프로그램에 SAML 토큰 제공 (합니다 *신뢰 당사자*) 하 고 해당 증명 키를 사용 하 여 메시지를 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4. <span data-ttu-id="d8b29-116">SAML 토큰을 통한 서명은 신뢰하는 상대에게 보안 토큰 서비스에서 토큰을 발행했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="d8b29-117">증명 키를 사용하여 만든 메시지 서명은 신뢰하는 상대에게 토큰이 클라이언트에게 발행되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="d8b29-118">클레임에서 SamlAttribute로</span><span class="sxs-lookup"><span data-stu-id="d8b29-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="d8b29-119">Wcf에서 SAML 토큰의 문은으로 모델링 됩니다 <xref:System.IdentityModel.Tokens.SamlAttribute> 개체를 직접 채울 수 있습니다 <xref:System.IdentityModel.Claims.Claim> 제공 하는 개체를 <xref:System.IdentityModel.Claims.Claim> 개체에는 <xref:System.IdentityModel.Claims.Claim.Right%2A> 속성을 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 및 <xref:System.IdentityModel.Claims.Claim.Resource%2A> 속성은 형식 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-119">In WCF, statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="d8b29-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d8b29-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  <span data-ttu-id="d8b29-121">SAML 토큰이 메시지에 serialize될 때 보안 토큰 서비스에서 해당 토큰을 발행하거나 클라이언트에서 인증의 일부로 해당 토큰을 서비스에 제공하는 경우, 최대 메시지 크기 할당량은 SAML 토큰 및 다른 메시지 부분을 수용할 수 있도록 충분히 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="d8b29-122">일반적으로 기본 메시지 크기 할당량이면 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="d8b29-123">그러나 SAML 토큰에 수백 개의 클레임이 포함되어 있어 SAML 토큰이 큰 경우에는 serialize된 토큰을 수용할 수 있도록 할당량을 늘려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> <span data-ttu-id="d8b29-124">자세한 내용은 [데이터에 대 한 보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-124">For more information, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="d8b29-125">SamlAttribute에서 클레임으로</span><span class="sxs-lookup"><span data-stu-id="d8b29-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="d8b29-126">메시지에서 SAML 토큰을 받으면 SAML 토큰의 여러 문이 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>에 배치되는 <xref:System.IdentityModel.Policy.AuthorizationContext> 개체로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="d8b29-127">각 SAML 문의 클레임은 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>의 <xref:System.IdentityModel.Policy.AuthorizationContext> 속성에서 반환하며, 사용자 인증 및 권한 부여 여부를 결정하기 위해 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b29-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b29-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8b29-128">See also</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="d8b29-129">페더레이션</span><span class="sxs-lookup"><span data-stu-id="d8b29-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="d8b29-130">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="d8b29-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d8b29-131">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="d8b29-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="d8b29-132">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="d8b29-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="d8b29-133">클레임 및 토큰</span><span class="sxs-lookup"><span data-stu-id="d8b29-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
- [<span data-ttu-id="d8b29-134">클레임 만들기 및 리소스 값</span><span class="sxs-lookup"><span data-stu-id="d8b29-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)
- [<span data-ttu-id="d8b29-135">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="d8b29-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
