---
title: SAML 토큰 및 클레임
description: WFC가 SAML 토큰을 사용 하 여 한 엔터티에서 다른 엔터티에 대해 만들어진 클레임 집합을 전달 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: c054e594af69def96879852a5145675b3123614a
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244948"
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="21ec6-103">SAML 토큰 및 클레임</span><span class="sxs-lookup"><span data-stu-id="21ec6-103">SAML Tokens and Claims</span></span>
<span data-ttu-id="21ec6-104">SAML (Security 어설션이 Markup Language) *토큰* 은 클레임의 XML 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-104">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="21ec6-105">기본적으로 페더레이션 보안 시나리오에서 WCF (Windows Communication Foundation)가 사용 하는 SAML 토큰은 *발급 된 토큰*입니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-105">By default, SAML tokens Windows Communication Foundation (WCF) uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="21ec6-106">SAML 토큰은 하나의 엔터티에서 다른 엔터티에 대해 만든 클레임 집합인 문을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-106">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="21ec6-107">예를 들어, 페더레이션 보안 시나리오의 경우 시스템의 사용자에 대한 보안 토큰 서비스에서 문을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-107">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="21ec6-108">보안 토큰 서비스에서는 토큰에 포함된 문의 정확성을 나타내기 위해 SAML 토큰을 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-108">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="21ec6-109">또한 SAML 토큰은 암호화 키 자료와 연결되어 있으며, 이 때 SAML 토큰의 사용자는 해당 키 자료를 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-109">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="21ec6-110">이 증명은 신뢰하는 상대에게 SAML 토큰이 실제로 해당 사용자에게 발행되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-110">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="21ec6-111">예를 들어, 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-111">For example, in a typical scenario:</span></span>  
  
1. <span data-ttu-id="21ec6-112">클라이언트는 보안 토큰 서비스에서 SAML 토큰을 요청하고 Windows 자격 증명을 사용하여 해당 보안 토큰 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-112">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2. <span data-ttu-id="21ec6-113">보안 토큰 서비스는 SAML 토큰을 클라이언트에 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-113">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="21ec6-114">SAML 토큰은 보안 토큰 서비스와 연결된 인증서를 통해 서명되며, 대상 서비스에 대해 암호화된 증명 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-114">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3. <span data-ttu-id="21ec6-115">클라이언트는 *증명 키*의 복사본도 받습니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-115">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="21ec6-116">클라이언트는 응용 프로그램 서비스 ( *신뢰*당사자)에 SAML 토큰을 제공 하 고 해당 증명 키로 메시지에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-116">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4. <span data-ttu-id="21ec6-117">SAML 토큰을 통한 서명은 신뢰하는 상대에게 보안 토큰 서비스에서 토큰을 발행했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-117">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="21ec6-118">증명 키를 사용하여 만든 메시지 서명은 신뢰하는 상대에게 토큰이 클라이언트에게 발행되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-118">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="21ec6-119">클레임에서 SamlAttribute로</span><span class="sxs-lookup"><span data-stu-id="21ec6-119">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="21ec6-120">WCF에서 SAML 토큰의 문은 개체 <xref:System.IdentityModel.Tokens.SamlAttribute> 에서 직접 채워질 수 있는 개체로 모델링 됩니다. 개체의 <xref:System.IdentityModel.Claims.Claim> <xref:System.IdentityModel.Claims.Claim> <xref:System.IdentityModel.Claims.Claim.Right%2A> 속성이이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 고 <xref:System.IdentityModel.Claims.Claim.Resource%2A> 속성은 형식입니다 <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="21ec6-120">In WCF, statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="21ec6-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="21ec6-121">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
> <span data-ttu-id="21ec6-122">SAML 토큰이 메시지에 serialize될 때 보안 토큰 서비스에서 해당 토큰을 발행하거나 클라이언트에서 인증의 일부로 해당 토큰을 서비스에 제공하는 경우, 최대 메시지 크기 할당량은 SAML 토큰 및 다른 메시지 부분을 수용할 수 있도록 충분히 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-122">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="21ec6-123">일반적으로 기본 메시지 크기 할당량이면 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-123">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="21ec6-124">그러나 SAML 토큰에 수백 개의 클레임이 포함되어 있어 SAML 토큰이 큰 경우에는 serialize된 토큰을 수용할 수 있도록 할당량을 늘려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-124">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> <span data-ttu-id="21ec6-125">자세한 내용은 [데이터의 보안 고려 사항](security-considerations-for-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21ec6-125">For more information, see [Security Considerations for Data](security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="21ec6-126">SamlAttribute에서 클레임으로</span><span class="sxs-lookup"><span data-stu-id="21ec6-126">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="21ec6-127">메시지에서 SAML 토큰을 받으면 SAML 토큰의 여러 문이 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>에 배치되는 <xref:System.IdentityModel.Policy.AuthorizationContext> 개체로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-127">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="21ec6-128">각 SAML 문의 클레임은 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>의 <xref:System.IdentityModel.Policy.AuthorizationContext> 속성에서 반환하며, 사용자 인증 및 권한 부여 여부를 결정하기 위해 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ec6-128">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ec6-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21ec6-129">See also</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="21ec6-130">페더레이션</span><span class="sxs-lookup"><span data-stu-id="21ec6-130">Federation</span></span>](federation.md)
- [<span data-ttu-id="21ec6-131">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="21ec6-131">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="21ec6-132">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="21ec6-132">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="21ec6-133">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="21ec6-133">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="21ec6-134">클레임 및 토큰</span><span class="sxs-lookup"><span data-stu-id="21ec6-134">Claims and Tokens</span></span>](claims-and-tokens.md)
- [<span data-ttu-id="21ec6-135">클레임 만들기 및 리소스 값</span><span class="sxs-lookup"><span data-stu-id="21ec6-135">Claim Creation and Resource Values</span></span>](claim-creation-and-resource-values.md)
- [<span data-ttu-id="21ec6-136">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="21ec6-136">How to: Create a Custom Claim</span></span>](../extending/how-to-create-a-custom-claim.md)
