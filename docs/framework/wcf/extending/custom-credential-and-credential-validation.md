---
description: '자세한 정보: 사용자 지정 자격 증명 및 자격 증명 유효성 검사'
title: 사용자 지정 자격 증명 및 자격 증명 유효성 검사
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: f1ceb8cf46cca01ac31faeb9485cbeb6c8663d31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735311"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="b7a37-103">사용자 지정 자격 증명 및 자격 증명 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="b7a37-103">Custom Credential and Credential Validation</span></span>

<span data-ttu-id="b7a37-104">WCF (Windows Communication Foundation)의 보안은 서비스와 클라이언트 간의 자격 증명 교환을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-104">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="b7a37-105">Windows(Kerberos), 사용자 이름 및 암호, 인증서 등의 일반 자격 증명 형식을 사용하여 대부분의 보안 시나리오를 만족시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-105">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="b7a37-106">그러나 새 자격 증명 형식이 필요한 경우 이 단원의 항목에서 새 형식을 처리하고 유효성을 검사하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-106">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7a37-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b7a37-107">In This Section</span></span>  

 [<span data-ttu-id="b7a37-108">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="b7a37-108">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="b7a37-109">클래스에서 상속 하 여 WCF 유효성 검사를 사용자 지정 하는 방법을 설명 합니다 <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="b7a37-109">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="b7a37-110">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="b7a37-110">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="b7a37-111"><xref:System.ServiceModel.Description.ClientCredentials> <xref:System.ServiceModel.Description.ServiceCredentials> 새 자격 증명 형식을 수용 하기 위해 및 클래스를 확장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-111">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="b7a37-112">이 항목은 사용자 지정 자격 증명 형식을 만들 수 있도록 하는 일련의 항목 중 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-112">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="b7a37-113">방법: 사용자 지정 보안 토큰 공급 기업 만들기</span><span class="sxs-lookup"><span data-stu-id="b7a37-113">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="b7a37-114">보안 토큰 공급자를 만들어 새 자격 증명 형식을 처리하고 자격 증명에 대한 새 토큰을 반환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-114">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="b7a37-115">이 항목은 일련의 항목 중 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-115">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="b7a37-116">방법: 사용자 지정 보안 토큰 인증자 만들기</span><span class="sxs-lookup"><span data-stu-id="b7a37-116">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="b7a37-117">사용자 지정 인증자를 만들어 새 자격 증명 형식을 인증하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-117">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="b7a37-118">이 항목은 일련의 항목 중 세 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a37-118">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b7a37-119">참고</span><span class="sxs-lookup"><span data-stu-id="b7a37-119">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="b7a37-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b7a37-120">Related Sections</span></span>  

 [<span data-ttu-id="b7a37-121">인증</span><span class="sxs-lookup"><span data-stu-id="b7a37-121">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="b7a37-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="b7a37-122">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="b7a37-123">권한 부여</span><span class="sxs-lookup"><span data-stu-id="b7a37-123">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7a37-124">참조</span><span class="sxs-lookup"><span data-stu-id="b7a37-124">See also</span></span>

- [<span data-ttu-id="b7a37-125">보안</span><span class="sxs-lookup"><span data-stu-id="b7a37-125">Security</span></span>](../feature-details/security.md)
