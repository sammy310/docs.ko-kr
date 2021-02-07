---
description: '자세한 정보: 방법: 사용자 지정 보안 토큰 공급자 만들기'
title: '방법: 사용자 지정 보안 토큰 공급 기업 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 4e0970ff01be74d0eb9f4ae8968bd100a0dafe00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735038"
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="1e580-103">방법: 사용자 지정 보안 토큰 공급 기업 만들기</span><span class="sxs-lookup"><span data-stu-id="1e580-103">How to: Create a Custom Security Token Provider</span></span>

<span data-ttu-id="1e580-104">이 항목에서는 사용자 지정 보안 토큰 공급자를 사용하여 새 토큰 형식을 만드는 방법과 공급자를 사용자 지정 보안 토큰 관리자와 통합하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-104">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e580-105"><xref:System.IdentityModel.Tokens>에 있는 시스템 제공 토큰이 요구 사항에 맞지 않을 경우 사용자 지정 토큰 공급자를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="1e580-105">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="1e580-106">보안 토큰 공급자는 클라이언트 또는 서비스 자격 증명의 정보를 기반으로 보안 토큰 표현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-106">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="1e580-107">WCF (Windows Communication Foundation) 보안에서 사용자 지정 보안 토큰 공급자를 사용 하려면 사용자 지정 자격 증명과 보안 토큰 관리자 구현을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-107">To use the custom security token provider in Windows Communication Foundation (WCF) security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="1e580-108">사용자 지정 자격 증명 및 보안 토큰 관리자에 대 한 자세한 내용은 [연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기](walkthrough-creating-custom-client-and-service-credentials.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e580-108">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="1e580-109">사용자 지정 보안 토큰 공급자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1e580-109">To create a custom security token provider</span></span>  
  
1. <span data-ttu-id="1e580-110"><xref:System.IdentityModel.Selectors.SecurityTokenProvider> 클래스에서 파생된 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2. <span data-ttu-id="1e580-111"><xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="1e580-112">이 메서드는 보안 토큰의 인스턴스를 만들고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="1e580-113">다음 예제에서는 `MySecurityTokenProvider`라는 클래스를 만들고, <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> 메서드를 재정의하여 <xref:System.IdentityModel.Tokens.X509SecurityToken> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="1e580-114">클래스 생성자에 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 클래스의 인스턴스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="1e580-115">사용자 지정 보안 토큰 공급자를 사용자 지정 보안 토큰 관리자와 통합하려면</span><span class="sxs-lookup"><span data-stu-id="1e580-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1. <span data-ttu-id="1e580-116"><xref:System.IdentityModel.Selectors.SecurityTokenManager> 클래스에서 파생된 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="1e580-117">아래 예제는 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스에서 파생된 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2. <span data-ttu-id="1e580-118">아직 재정의되지 않은 경우 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="1e580-119"><xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>메서드는 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> WCF 보안 프레임 워크에 의해 메서드에 전달 된 매개 변수에 적합 한 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the WCF security framework.</span></span> <span data-ttu-id="1e580-120">적절한 보안 토큰 매개 변수를 사용하여 메서드를 호출할 때 이전 절차에서 만든 사용자 지정 보안 토큰 공급자 구현을 반환하도록 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="1e580-121">보안 토큰 관리자에 대 한 자세한 내용은 [연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기](walkthrough-creating-custom-client-and-service-credentials.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e580-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3. <span data-ttu-id="1e580-122">메서드에 논리를 추가하여 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> 매개 변수를 기반으로 사용자 지정 보안 토큰 공급자를 반환할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="1e580-123">다음 예제에서는 토큰 요구 사항에 맞을 경우 사용자 지정 보안 토큰 공급자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="1e580-124">요구 사항에는 X.509 보안 토큰 및 토큰이 메시지 출력에 사용되는 메시지 방향이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="1e580-125">다른 모든 경우에서 코드는 기본 클래스를 호출하여 다른 보안 토큰 요구 사항에 대한 시스템 제공 동작을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="1e580-126">예제</span><span class="sxs-lookup"><span data-stu-id="1e580-126">Example</span></span>  

 <span data-ttu-id="1e580-127">다음 예제에서는 해당 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 구현과 함께 전체 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e580-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="1e580-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e580-128">See also</span></span>

- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [<span data-ttu-id="1e580-129">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="1e580-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)
- [<span data-ttu-id="1e580-130">방법: 사용자 지정 보안 토큰 인증자 만들기</span><span class="sxs-lookup"><span data-stu-id="1e580-130">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)
