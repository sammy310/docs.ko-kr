---
description: '자세한 정보: 방법: 보안 토큰 서비스 만들기'
title: '방법: 보안 토큰 서비스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
ms.openlocfilehash: a3bfe6f97eeccdb31d3b8f4ef6c05a3c15257e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734453"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="a6234-103">방법: 보안 토큰 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="a6234-103">How to: Create a Security Token Service</span></span>

<span data-ttu-id="a6234-104">보안 토큰 서비스에서는 WS-Trust 사양에 정의된 프로토콜을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-104">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="a6234-105">이 프로토콜은 보안 토큰의 발행, 갱신, 취소 및 유효성 검사를 위한 메시지 형식 및 메시지 교환 패턴을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-105">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="a6234-106">지정된 보안 토큰 서비스에서는 하나 이상의 이러한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-106">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="a6234-107">이 항목에서는 가장 일반적인 시나리오인 토큰 발급 구현에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-107">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="a6234-108">토큰 발급</span><span class="sxs-lookup"><span data-stu-id="a6234-108">Issuing Tokens</span></span>  

 <span data-ttu-id="a6234-109">WS-Trust는 `RequestSecurityToken` XSD(XML 스키마 정의 언어) 스키마 요소에 따라 메시지 형식을 정의하고, 토큰 발행을 수행하기 위한 `RequestSecurityTokenResponse` XSD 스키마 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-109">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="a6234-110">또한 연결된 동작 URI(Uniform Resource Identifier)도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-110">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="a6234-111">메시지와 연결 된 동작 URI는 `RequestSecurityToken` `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-111">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="a6234-112">메시지와 연결 된 동작 URI는 `RequestSecurityTokenResponse`   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-112">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="a6234-113">요청 메시지 구조</span><span class="sxs-lookup"><span data-stu-id="a6234-113">Request Message Structure</span></span>  

 <span data-ttu-id="a6234-114">일반적으로 발행 요청 메시지 구조는 다음과 같은 항목으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-114">The issue request message structure typically consists of the following items:</span></span>  
  
- <span data-ttu-id="a6234-115">값이 인 요청 형식 URI입니다 `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue` .</span><span class="sxs-lookup"><span data-stu-id="a6234-115">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
- <span data-ttu-id="a6234-116">토큰 형식 URI.</span><span class="sxs-lookup"><span data-stu-id="a6234-116">A token type URI.</span></span> <span data-ttu-id="a6234-117">SAML (Security 어설션이 Markup Language) 1.1 토큰의 경우이 URI의 값은 `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-117">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
- <span data-ttu-id="a6234-118">발행된 토큰과 연결될 키의 비트 수를 나타내는 키 크기 값</span><span class="sxs-lookup"><span data-stu-id="a6234-118">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
- <span data-ttu-id="a6234-119">키 형식 URI.</span><span class="sxs-lookup"><span data-stu-id="a6234-119">A key type URI.</span></span> <span data-ttu-id="a6234-120">대칭 키의 경우이 URI의 값은 `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-120">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="a6234-121">또한 다음과 같은 몇 가지 다른 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-121">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="a6234-122">클라이언트에서 제공하는 키 자료</span><span class="sxs-lookup"><span data-stu-id="a6234-122">Key material provided by the client.</span></span>  
  
- <span data-ttu-id="a6234-123">발행된 토큰이 함께 사용될 대상 서비스를 나타내는 범위 정보</span><span class="sxs-lookup"><span data-stu-id="a6234-123">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="a6234-124">보안 토큰 서비스에서는 발행 응답 메시지를 만들 때 발행 요청 메시지의 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-124">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="a6234-125">응답 메시지 구조</span><span class="sxs-lookup"><span data-stu-id="a6234-125">Response Message Structure</span></span>  

 <span data-ttu-id="a6234-126">일반적으로 발행 응답 메시지 구조는 다음과 같은 항목으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-126">The issue response message structure typically consists of the following items;</span></span>  
  
- <span data-ttu-id="a6234-127">발행된 보안 토큰(예: SAML 1.1 어설션)</span><span class="sxs-lookup"><span data-stu-id="a6234-127">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
- <span data-ttu-id="a6234-128">보안 토큰에 연결된 증명 토큰.</span><span class="sxs-lookup"><span data-stu-id="a6234-128">A proof token associated with the security token.</span></span> <span data-ttu-id="a6234-129">대칭 키의 경우 이 토큰이 키 자료의 암호화된 형식인 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-129">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
- <span data-ttu-id="a6234-130">발행된 보안 토큰에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="a6234-130">References to the issued security token.</span></span> <span data-ttu-id="a6234-131">일반적으로 보안 토큰 서비스에서는 발행된 토큰이 클라이언트가 보낸 다음 메시지에 나타나는 경우 사용할 수 있는 참조 및 해당 토큰이 다음 메시지에 나타나지 않는 경우 사용할 수 있는 다른 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-131">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="a6234-132">또한 다음과 같은 몇 가지 다른 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-132">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="a6234-133">보안 토큰 서비스에서 제공한 키 자료</span><span class="sxs-lookup"><span data-stu-id="a6234-133">Key material provided by the security token service.</span></span>  
  
- <span data-ttu-id="a6234-134">공유 키를 컴퓨팅하는 데 필요한 알고리즘</span><span class="sxs-lookup"><span data-stu-id="a6234-134">The algorithm needed to compute the shared key.</span></span>  
  
- <span data-ttu-id="a6234-135">발행된 토큰에 대한 수명 정보</span><span class="sxs-lookup"><span data-stu-id="a6234-135">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="a6234-136">요청 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="a6234-136">Processing Request Messages</span></span>  

 <span data-ttu-id="a6234-137">보안 토큰 서비스에서는 여러 요청 메시지를 조사하고 이 메시지에서 요청을 만족하는 토큰을 발행할 수 있음을 확인하여 발행 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-137">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="a6234-138">보안 토큰 서비스는 발행할 토큰을 만들기 전에 다음 사항을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-138">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
- <span data-ttu-id="a6234-139">요청이 발행할 토큰에 대한 요청이 맞는지 여부</span><span class="sxs-lookup"><span data-stu-id="a6234-139">The request really is a request for a token to be issued.</span></span>  
  
- <span data-ttu-id="a6234-140">보안 토큰 서비스에서 요청된 토큰 형식을 지원하는지 여부</span><span class="sxs-lookup"><span data-stu-id="a6234-140">The security token service supports the requested token type.</span></span>  
  
- <span data-ttu-id="a6234-141">요청자가 요청을 할 수 있는 권한이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="a6234-141">The requester is authorized to make the request.</span></span>  
  
- <span data-ttu-id="a6234-142">보안 토큰 서비스가 키 자료에 대한 요청자의 기대치를 충족할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="a6234-142">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="a6234-143">토큰을 만드는 데 있어 중요한 두 가지 사항은 토큰을 서명할 때 사용할 키와 공유 키를 암호화할 때 사용할 키를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-143">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="a6234-144">클라이언트가 대상 서비스에 토큰을 제공하는 경우 해당 서비스가 신뢰하는 보안 토큰 서비스에서 토큰을 발행했음을 확인할 수 있도록 토큰에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-144">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="a6234-145">키 자료는 대상 서비스에서 해당 키 자료를 해독할 수 있는 방식으로 암호화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-145">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="a6234-146">SAML 어설션에 서명하려면 <xref:System.IdentityModel.Tokens.SigningCredentials> 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-146">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="a6234-147">이 클래스의 생성자는 다음 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-147">The constructor for this class takes the following:</span></span>  
  
- <span data-ttu-id="a6234-148">SAML 어설션에 서명하는 데 사용할 키에 대한 <xref:System.IdentityModel.Tokens.SecurityKey></span><span class="sxs-lookup"><span data-stu-id="a6234-148">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
- <span data-ttu-id="a6234-149">사용할 서명 알고리즘을 식별하는 문자열</span><span class="sxs-lookup"><span data-stu-id="a6234-149">A string identifying the signature algorithm to use.</span></span>  
  
- <span data-ttu-id="a6234-150">사용할 다이제스트 알고리즘을 식별하는 문자열</span><span class="sxs-lookup"><span data-stu-id="a6234-150">A string identifying the digest algorithm to use.</span></span>  
  
- <span data-ttu-id="a6234-151">필요한 경우 어설션을 서명하는 데 사용할 키를 식별하는 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier></span><span class="sxs-lookup"><span data-stu-id="a6234-151">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="a6234-152">공유 키를 암호화하려면 키 자료가 필요하며, 대상 서비스에서 공유 키를 해독하는 데 사용할 수 있는 키를 사용하여 공유 키를 암호화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-152">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="a6234-153">일반적으로 대상 서비스의 공개 키가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-153">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="a6234-154">또한 암호화된 키에 대한 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-154">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="a6234-155">이 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>는 `SamlSubject`를 만드는 데 `SamlToken`의 일부로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-155">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="a6234-156">자세한 내용은 [페더레이션 샘플](../samples/federation-sample.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6234-156">For more information, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="a6234-157">응답 메시지 만들기</span><span class="sxs-lookup"><span data-stu-id="a6234-157">Creating Response Messages</span></span>  

 <span data-ttu-id="a6234-158">보안 토큰 서비스에서 발행 요청을 처리하고 증명 키와 함께 발행될 토큰을 만들면 적어도 요청된 토큰, 증명 토큰 및 발행된 토큰 참조를 포함하여 응답 메시지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-158">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="a6234-159">일반적으로 발행된 토큰은 다음 예제에서처럼 <xref:System.IdentityModel.Tokens.SamlSecurityToken>에서 만들어진 <xref:System.IdentityModel.Tokens.SamlAssertion>입니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-159">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="a6234-160">보안 토큰 서비스에서 공유 키 자료를 제공하는 경우에는 <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>을 만들어 증명 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-160">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="a6234-161">클라이언트와 보안 토큰 서비스가 모두 공유 키에 대 한 키 자료를 제공할 때 증명 토큰을 생성 하는 방법에 대 한 자세한 내용은 [페더레이션 샘플](../samples/federation-sample.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6234-161">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="a6234-162"><xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> 클래스의 인스턴스를 만들어 발행된 토큰 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-162">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="a6234-163">이러한 여러 값은 클라이언트에 반환되는 응답 메시지로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6234-163">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6234-164">예제</span><span class="sxs-lookup"><span data-stu-id="a6234-164">Example</span></span>  

 <span data-ttu-id="a6234-165">보안 토큰 서비스에 대 한 전체 코드는 [페더레이션 샘플](../samples/federation-sample.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6234-165">For full code for a security token service, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6234-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6234-166">See also</span></span>

- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [<span data-ttu-id="a6234-167">Federation 샘플</span><span class="sxs-lookup"><span data-stu-id="a6234-167">Federation Sample</span></span>](../samples/federation-sample.md)
