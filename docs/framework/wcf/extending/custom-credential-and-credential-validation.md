---
title: 사용자 지정 자격 증명 및 자격 증명 유효성 검사
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 3b1ff700010f471a4d9be117f363083b6cbed493
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696446"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="9f03f-102">사용자 지정 자격 증명 및 자격 증명 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9f03f-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="9f03f-103">보안에서 Windows Communication Foundation (WCF) 서비스와 클라이언트 간의 자격 증명 교환을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="9f03f-104">Windows(Kerberos), 사용자 이름 및 암호, 인증서 등의 일반 자격 증명 형식을 사용하여 대부분의 보안 시나리오를 만족시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="9f03f-105">그러나 새 자격 증명 형식이 필요한 경우 이 단원의 항목에서 새 형식을 처리하고 유효성을 검사하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f03f-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9f03f-106">In This Section</span></span>  
 [<span data-ttu-id="9f03f-107">방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="9f03f-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="9f03f-108">상속 하 여 WCF 유효성 검사를 사용자 지정 하는 방법에 설명 합니다 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="9f03f-109">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="9f03f-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="9f03f-110">확장 하는 방법에 설명 합니다 <xref:System.ServiceModel.Description.ClientCredentials> 및 <xref:System.ServiceModel.Description.ServiceCredentials> 자격 증명 유형에 맞게 새 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="9f03f-111">이 항목은 사용자 지정 자격 증명 형식을 만들 수 있도록 하는 일련의 항목 중 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="9f03f-112">방법: 사용자 지정 보안 토큰 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="9f03f-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="9f03f-113">보안 토큰 공급자를 만들어 새 자격 증명 형식을 처리하고 자격 증명에 대한 새 토큰을 반환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="9f03f-114">이 항목은 일련의 항목 중 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="9f03f-115">방법: 사용자 지정 보안 토큰 인증자 만들기</span><span class="sxs-lookup"><span data-stu-id="9f03f-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="9f03f-116">사용자 지정 인증자를 만들어 새 자격 증명 형식을 인증하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="9f03f-117">이 항목은 일련의 항목 중 세 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="9f03f-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9f03f-118">참조</span><span class="sxs-lookup"><span data-stu-id="9f03f-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="9f03f-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9f03f-119">Related Sections</span></span>  
 [<span data-ttu-id="9f03f-120">인증</span><span class="sxs-lookup"><span data-stu-id="9f03f-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="9f03f-121">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="9f03f-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="9f03f-122">권한 부여</span><span class="sxs-lookup"><span data-stu-id="9f03f-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f03f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f03f-123">See also</span></span>

- [<span data-ttu-id="9f03f-124">보안</span><span class="sxs-lookup"><span data-stu-id="9f03f-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
