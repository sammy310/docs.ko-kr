---
description: '자세히 알아보기: 보안 확장'
title: 보안 확장
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 8dd514e16106ac5cdae072d92c7de66cefd39fe4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685727"
---
# <a name="extending-security"></a><span data-ttu-id="1da16-103">보안 확장</span><span class="sxs-lookup"><span data-stu-id="1da16-103">Extending Security</span></span>

<span data-ttu-id="1da16-104">새 클레임 형식 및 사용자 지정 토큰을 수용 하기 위해 WCF (Windows Communication Foundation)의 보안 인프라를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-104">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1da16-105">이 단원의 각 항목에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-105">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1da16-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1da16-106">In This Section</span></span>  
  
 [<span data-ttu-id="1da16-107">사용자 지정 자격 증명 및 자격 증명 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="1da16-107">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="1da16-108">사용자 지정 자격 증명의 유효성을 검사할 때 ID 모델을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-108">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="1da16-109">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="1da16-109">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="1da16-110">일반적으로 STS(보안 토큰 서비스)에서 발행된 토큰은 SAML 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-110">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="1da16-111">이 항목에서는 사용자 지정 토큰 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-111">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="1da16-112">사용자 지정 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1da16-112">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="1da16-113">사용자 지정 인증을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-113">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="1da16-114">인증을 위해 서비스 ID 재정의</span><span class="sxs-lookup"><span data-stu-id="1da16-114">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="1da16-115">인증을 위해 서비스의 ID를 재지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-115">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="1da16-116">방법: 사용자 지정 클라이언트 ID 검증 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="1da16-116">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="1da16-117">사용자 지정 엔드포인트 ID의 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-117">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="1da16-118">방법: 서명 및 암호화에 별도의 X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="1da16-118">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="1da16-119">일반적으로 메시지는 단일 인증서를 사용하여 서명되고 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-119">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="1da16-120">이 항목에서는 필요한 경우 두 가지 인증서를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-120">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="1da16-121">방법: X.509 인증서의 프라이빗 키에 대한 암호화 공급 기업 변경</span><span class="sxs-lookup"><span data-stu-id="1da16-121">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="1da16-122">X.509 인증서의 개인 키를 제공 하는 데 사용 되는 암호화 공급자를 변경 하는 방법과 공급자를 WCF (Windows Communication Foundation) 프레임 워크에 통합 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1da16-122">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1da16-123">참고</span><span class="sxs-lookup"><span data-stu-id="1da16-123">Reference</span></span>  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="1da16-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1da16-124">Related Sections</span></span>  

 [<span data-ttu-id="1da16-125">보안</span><span class="sxs-lookup"><span data-stu-id="1da16-125">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="1da16-126">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1da16-126">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="1da16-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1da16-127">See also</span></span>

- [<span data-ttu-id="1da16-128">보안 개요</span><span class="sxs-lookup"><span data-stu-id="1da16-128">Security Overview</span></span>](../feature-details/security-overview.md)
