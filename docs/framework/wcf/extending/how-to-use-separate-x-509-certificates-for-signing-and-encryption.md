---
description: '자세히 알아보기: 방법: 서명 및 암호화에 별도의 x.509 인증서 사용'
title: '방법: 서명 및 암호화에 별도의 X.509 인증서 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
ms.openlocfilehash: a1cb72265d9fa2742718b88bd574efe4cc9a4918
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644244"
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a><span data-ttu-id="a8554-103">방법: 서명 및 암호화에 별도의 X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="a8554-103">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>

<span data-ttu-id="a8554-104">이 항목에서는 클라이언트와 서비스 모두에서 메시지 서명 및 암호화에 서로 다른 인증서를 사용 하도록 WCF (Windows Communication Foundation)를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-104">This topic shows how to configure Windows Communication Foundation (WCF) to use different certificates for message signing and encryption on both the client and service.</span></span>

<span data-ttu-id="a8554-105">서명 및 암호화에 별도의 인증서를 사용 하려면 WCF에서 여러 클라이언트 또는 서비스 인증서를 설정 하는 API를 제공 하지 않기 때문에 사용자 지정 클라이언트 또는 서비스 자격 증명 (또는 둘 다)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-105">To enable separate certificates to be used for signing and encryption, a custom client or service credentials (or both) must be created because WCF does not provide an API to set multiple client or service certificates.</span></span> <span data-ttu-id="a8554-106">또한 여러 개의 인증서 정보를 활용하고 지정된 키 사용과 메시지 방향에 적합한 보안 토큰 공급자를 만들기 위해 보안 토큰 관리자도 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-106">Additionally, a security token manager must be provided to leverage the multiple certificates' information and to create an appropriate security token provider for specified key usage and message direction.</span></span>

<span data-ttu-id="a8554-107">다음 다이어그램에서는 사용되는 주 클래스, 상속하는 클래스(위쪽 화살표로 표시), 특정 메서드 및 속성의 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-107">The following diagram shows the main classes used, the classes they inherit from (shown by an upward-pointing arrow), and the return types of certain methods and properties.</span></span>

- <span data-ttu-id="a8554-108">`MyClientCredentials`는 <xref:System.ServiceModel.Description.ClientCredentials>의 사용자 지정 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-108">`MyClientCredentials` is a custom implementation of <xref:System.ServiceModel.Description.ClientCredentials>.</span></span>

  - <span data-ttu-id="a8554-109">다이어그램에 표시된 속성은 모두 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-109">Its properties shown in the diagram all return instances of <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span></span>

  - <span data-ttu-id="a8554-110">메서드 는 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-110">Its method <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> returns an instance of `MyClientCredentialsSecurityTokenManager`.</span></span>

- <span data-ttu-id="a8554-111">`MyClientCredentialsSecurityTokenManager`는 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>의 사용자 지정 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-111">`MyClientCredentialsSecurityTokenManager` is a custom implementation of <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.</span></span>

  - <span data-ttu-id="a8554-112">메서드 는 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-112">Its method <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> returns an instance of <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.</span></span>

<span data-ttu-id="a8554-113">![클라이언트 자격 증명을 사용하는 방법을 보여 주는 차트](./media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span><span class="sxs-lookup"><span data-stu-id="a8554-113">![Chart showing how client credentials are used](./media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span></span>

<span data-ttu-id="a8554-114">사용자 지정 자격 증명에 대 한 자세한 내용은 [연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기](walkthrough-creating-custom-client-and-service-credentials.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8554-114">For more information about custom credentials, see [Walkthrough: Creating Custom Client and Service Credentials](walkthrough-creating-custom-client-and-service-credentials.md).</span></span>

<span data-ttu-id="a8554-115">또한 사용자 지정 ID 검증 도구를 만들고 사용자 지정 바인딩의 보안 바인딩 요소에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-115">In addition, you must create a custom identity verifier, and link it to a security binding element in a custom binding.</span></span> <span data-ttu-id="a8554-116">그리고 기본 자격 증명 대신 사용자 지정 자격 증명을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-116">You must also use the custom credentials instead of the default credentials.</span></span>

<span data-ttu-id="a8554-117">다음 다이어그램에서는 사용자 지정 바인딩에 관련된 클래스 및 사용자 지정 ID 검증 도구를 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-117">The following diagram shows the classes involved in the custom binding, and how the custom identity verifier is linked.</span></span> <span data-ttu-id="a8554-118">여러 바인딩 요소가 관련되어 있으며 이들 요소는 모두 <xref:System.ServiceModel.Channels.BindingElement>에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-118">There are several binding elements involved, all of which inherit from <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="a8554-119">에는  속성이 있습니다. 이 속성은 가 사용자 지정되는 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-119">The <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> has the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> property, which returns an instance of <xref:System.ServiceModel.Security.IdentityVerifier>, from which `MyIdentityVerifier` is customized.</span></span>

<span data-ttu-id="a8554-120">![사용자 지정 바인딩 요소를 보여 주는 차트](./media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span><span class="sxs-lookup"><span data-stu-id="a8554-120">![Chart showing a custom binding element](./media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span></span>

<span data-ttu-id="a8554-121">사용자 지정 id 검증 도구를 만드는 방법에 대 한 자세한 내용은 방법: [방법: 사용자 지정 클라이언트 Id 검증 도구 만들기](how-to-create-a-custom-client-identity-verifier.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8554-121">For more information about creating a custom identity verifier, see How to: [How to: Create a Custom Client Identity Verifier](how-to-create-a-custom-client-identity-verifier.md).</span></span>

### <a name="to-use-separate-certificates-for-signing-and-encryption"></a><span data-ttu-id="a8554-122">서명 및 암호화에 별도의 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a8554-122">To use separate certificates for signing and encryption</span></span>

1. <span data-ttu-id="a8554-123"><xref:System.ServiceModel.Description.ClientCredentials> 클래스에서 상속되는 새로운 클라이언트 자격 증명 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-123">Define a new client credentials class that inherits from the <xref:System.ServiceModel.Description.ClientCredentials> class.</span></span> <span data-ttu-id="a8554-124">여러 인증서 지정을 허용하는 네 가지 새 속성인 , , 및 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-124">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="a8554-125">또한 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 메서드를 재정의하여 다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-125">Also override the <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>

     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]

2. <span data-ttu-id="a8554-126"><xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스에서 상속되는 새로운 클라이언트 보안 토큰 관리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-126">Define a new client security token manager that inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="a8554-127">올바른 보안 토큰 공급자를 만들기 위해 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-127">Override the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider.</span></span> <span data-ttu-id="a8554-128">메시지 방향과 키 사용은 `requirement` 매개 변수(<xref:System.IdentityModel.Selectors.SecurityTokenRequirement>)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-128">The `requirement` parameter (a <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) provides the message direction and key usage.</span></span>

     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]

3. <span data-ttu-id="a8554-129"><xref:System.ServiceModel.Description.ServiceCredentials> 클래스에서 상속되는 새로운 서비스 자격 증명 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-129">Define a new service credentials class that inherits from the <xref:System.ServiceModel.Description.ServiceCredentials> class.</span></span> <span data-ttu-id="a8554-130">여러 인증서 지정을 허용하는 네 가지 새 속성인 , , 및 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-130">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="a8554-131">또한 <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> 메서드를 재정의하여 다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-131">Also override the <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>

     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]

4. <span data-ttu-id="a8554-132"><xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스에서 상속되는 새로운 서비스 보안 토큰 관리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-132">Define a new service security token manager that inherits from the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="a8554-133">전달된 메시지 방향과 키 사용에 적합한 보안 토큰 공급자를 만들기 위해 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-133">Override the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider given the passed-in message direction and key usage.</span></span>

     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]

### <a name="to-use-multiple-certificates-on-the-client"></a><span data-ttu-id="a8554-134">클라이언트에 여러 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a8554-134">To use multiple certificates on the client</span></span>

1. <span data-ttu-id="a8554-135">사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-135">Create a custom binding.</span></span> <span data-ttu-id="a8554-136">보안 바인딩 요소는 요청 및 응답에 서로 다른 보안 토큰 공급자를 사용할 수 있도록 이중 모드로 작동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-136">The security binding element must operate in duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="a8554-137">이를 위한 한 가지 방법은 다음 코드에서와 같이 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>를 사용하거나 이중 가능 전송을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-137">One way to do this is to use a duplex-capable transport or to use the <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="a8554-138">다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.Security.IdentityVerifier>를 보안 바인딩 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-138">Link the customized <xref:System.ServiceModel.Security.IdentityVerifier> which is defined in the next step to the security binding element.</span></span> <span data-ttu-id="a8554-139">기본 클라이언트 자격 증명을 이전에 만든 사용자 지정된 클라이언트 자격 증명으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-139">Replace the default client credentials with the customized client credentials previously created.</span></span>

     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]

2. <span data-ttu-id="a8554-140">사용자 지정 <xref:System.ServiceModel.Security.IdentityVerifier>를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-140">Define a custom <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="a8554-141">요청을 암호화하고 응답을 서명하는 데 서로 다른 인증서가 사용되므로 서비스에는 여러 개의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-141">The service has multiple identities because different certificates are used to encrypt the request and to sign the response.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8554-142">다음 샘플에 제공된 사용자 지정 ID 검증 도구는 엔드포인트 ID 확인을 수행하지 않는 데모용이므로,</span><span class="sxs-lookup"><span data-stu-id="a8554-142">In the following sample, the provided custom identity verifier does not perform any endpoint identity checking for demonstration purposes.</span></span> <span data-ttu-id="a8554-143">프로덕션 코드에 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-143">This is not recommended practice for production code.</span></span>

     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]

### <a name="to-use-multiple-certificates-on-the-service"></a><span data-ttu-id="a8554-144">서비스에 여러 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a8554-144">To use multiple certificates on the service</span></span>

1. <span data-ttu-id="a8554-145">사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-145">Create a custom binding.</span></span> <span data-ttu-id="a8554-146">보안 바인딩 요소는 요청 및 응답에 서로 다른 보안 토큰 공급자를 사용할 수 있도록 이중 모드로 작동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-146">The security binding element must operate in a duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="a8554-147">클라이언트와 마찬가지로, 다음 코드에서와 같이 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>를 사용하거나 이중 가능 전송을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-147">As with the client, use a duplex-capable transport or use <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="a8554-148">기본 서비스 자격 증명을 이전에 만든 사용자 지정된 서비스 자격 증명으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a8554-148">Replace the default service credentials with the customized service credentials previously created.</span></span>

     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]

## <a name="see-also"></a><span data-ttu-id="a8554-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8554-149">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="a8554-150">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="a8554-150">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)
