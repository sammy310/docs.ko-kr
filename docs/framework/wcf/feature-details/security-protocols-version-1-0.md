---
description: '자세한 정보: 보안 프로토콜 버전 1.0'
title: 보안 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: c807f0b844fb9cb861148afa63d83826a9740c98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752732"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="342a3-103">보안 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-103">Security Protocols version 1.0</span></span>

<span data-ttu-id="342a3-104">Web Services Security 프로토콜은 모든 기존 엔터프라이즈 메시징 보안 요구 사항을 포함하는 Web Services Security 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-104">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="342a3-105">이 섹션에서는 <xref:System.ServiceModel.Channels.SecurityBindingElement> 다음 웹 서비스 보안 프로토콜에 대 한 WCF (Windows Communication Foundation) 버전 1.0 정보 (에서 구현 됨)에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-105">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="342a3-106">사양/문서</span><span class="sxs-lookup"><span data-stu-id="342a3-106">Specification/Document</span></span>|<span data-ttu-id="342a3-107">링크</span><span class="sxs-lookup"><span data-stu-id="342a3-107">Link</span></span>|  
|-|-|  
|<span data-ttu-id="342a3-108">WSS: SOAP Message Security 1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-108">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="342a3-109">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-109">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="342a3-110">WSS: X509 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-110">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="342a3-111">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-111">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="342a3-112">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-112">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="342a3-113">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-113">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="342a3-114">WSS: X.509 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-114">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="342a3-115">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-115">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="342a3-116">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-116">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="342a3-117">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="342a3-117">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="342a3-118">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="342a3-118">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="342a3-119">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="342a3-119">Application Note:</span></span><br /><br /> <span data-ttu-id="342a3-120">WS-Trust for TLS Handshake 사용</span><span class="sxs-lookup"><span data-stu-id="342a3-120">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="342a3-121">게시 예정</span><span class="sxs-lookup"><span data-stu-id="342a3-121">To be published</span></span>|  
|<span data-ttu-id="342a3-122">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="342a3-122">Application Note:</span></span><br /><br /> <span data-ttu-id="342a3-123">WS-Trust for SPNEGO 사용</span><span class="sxs-lookup"><span data-stu-id="342a3-123">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="342a3-124">게시 예정</span><span class="sxs-lookup"><span data-stu-id="342a3-124">To be published</span></span>|  
|<span data-ttu-id="342a3-125">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="342a3-125">Application Note:</span></span><br /><br /> <span data-ttu-id="342a3-126">Web Services Addressing 엔드포인트 참조 및 ID</span><span class="sxs-lookup"><span data-stu-id="342a3-126">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="342a3-127">게시 예정</span><span class="sxs-lookup"><span data-stu-id="342a3-127">To be published</span></span>|  
|<span data-ttu-id="342a3-128">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="342a3-128">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="342a3-129">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="342a3-129">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="342a3-130">OASIS WS-SX 기술 위원회에 제출 된 [오류](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) 에 의해 수정 됨</span><span class="sxs-lookup"><span data-stu-id="342a3-130">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="342a3-131">WCF, 버전 1은 웹 서비스 보안 구성의 기반으로 사용할 수 있는 17 개의 인증 모드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-131">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="342a3-132">각 모드는 다음과 같은 공통 배포 요구 사항에 대해 최적화된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-132">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="342a3-133">클라이언트와 서비스를 인증하는 데 사용되는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="342a3-133">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="342a3-134">메시지 또는 전송 보안 보호 메커니즘</span><span class="sxs-lookup"><span data-stu-id="342a3-134">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="342a3-135">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="342a3-135">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="342a3-136">인증 모드</span><span class="sxs-lookup"><span data-stu-id="342a3-136">Authentication Mode</span></span>|<span data-ttu-id="342a3-137">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="342a3-137">Client Authentication</span></span>|<span data-ttu-id="342a3-138">서버 인증</span><span class="sxs-lookup"><span data-stu-id="342a3-138">Server Authentication</span></span>|<span data-ttu-id="342a3-139">모드</span><span class="sxs-lookup"><span data-stu-id="342a3-139">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="342a3-140">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-140">UserNameOverTransport</span></span>|<span data-ttu-id="342a3-141">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="342a3-141">User name/password</span></span>|<span data-ttu-id="342a3-142">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-142">X509</span></span>|<span data-ttu-id="342a3-143">전송</span><span class="sxs-lookup"><span data-stu-id="342a3-143">Transport</span></span>|  
|<span data-ttu-id="342a3-144">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-144">CertificateOverTransport</span></span>|<span data-ttu-id="342a3-145">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-145">X509</span></span>|<span data-ttu-id="342a3-146">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-146">X509</span></span>|<span data-ttu-id="342a3-147">전송</span><span class="sxs-lookup"><span data-stu-id="342a3-147">Transport</span></span>|  
|<span data-ttu-id="342a3-148">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-148">KerberosOverTransport</span></span>|<span data-ttu-id="342a3-149">Windows</span><span class="sxs-lookup"><span data-stu-id="342a3-149">Windows</span></span>|<span data-ttu-id="342a3-150">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-150">X509</span></span>|<span data-ttu-id="342a3-151">전송</span><span class="sxs-lookup"><span data-stu-id="342a3-151">Transport</span></span>|  
|<span data-ttu-id="342a3-152">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-152">IssuedTokenOverTransport</span></span>|<span data-ttu-id="342a3-153">페더레이션</span><span class="sxs-lookup"><span data-stu-id="342a3-153">Federated</span></span>|<span data-ttu-id="342a3-154">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-154">X509</span></span>|<span data-ttu-id="342a3-155">전송</span><span class="sxs-lookup"><span data-stu-id="342a3-155">Transport</span></span>|  
|<span data-ttu-id="342a3-156">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-156">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="342a3-157">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="342a3-158">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-158">Windows Sspi Negotiated</span></span>|<span data-ttu-id="342a3-159">전송</span><span class="sxs-lookup"><span data-stu-id="342a3-159">Transport</span></span>|  
|<span data-ttu-id="342a3-160">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-160">AnonymousForCertificate</span></span>|<span data-ttu-id="342a3-161">없음</span><span class="sxs-lookup"><span data-stu-id="342a3-161">None</span></span>|<span data-ttu-id="342a3-162">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-162">X509</span></span>|<span data-ttu-id="342a3-163">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-163">Message</span></span>|  
|<span data-ttu-id="342a3-164">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-164">UserNameForCertificate</span></span>|<span data-ttu-id="342a3-165">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="342a3-165">User name/password</span></span>|<span data-ttu-id="342a3-166">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-166">X509</span></span>|<span data-ttu-id="342a3-167">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-167">Message</span></span>|  
|<span data-ttu-id="342a3-168">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-168">MutualCertificate</span></span>|<span data-ttu-id="342a3-169">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-169">X509</span></span>|<span data-ttu-id="342a3-170">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-170">X509</span></span>|<span data-ttu-id="342a3-171">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-171">Message</span></span>|  
|<span data-ttu-id="342a3-172">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="342a3-172">MutualCertificateDuplex</span></span>|<span data-ttu-id="342a3-173">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-173">X509</span></span>|<span data-ttu-id="342a3-174">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-174">X509</span></span>|<span data-ttu-id="342a3-175">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-175">Message</span></span>|  
|<span data-ttu-id="342a3-176">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-176">IssuedTokenForCertificate</span></span>|<span data-ttu-id="342a3-177">페더레이션</span><span class="sxs-lookup"><span data-stu-id="342a3-177">Federated</span></span>|<span data-ttu-id="342a3-178">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-178">X509</span></span>|<span data-ttu-id="342a3-179">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-179">Message</span></span>|  
|<span data-ttu-id="342a3-180">Kerberos</span><span class="sxs-lookup"><span data-stu-id="342a3-180">Kerberos</span></span>|<span data-ttu-id="342a3-181">Windows</span><span class="sxs-lookup"><span data-stu-id="342a3-181">Windows</span></span>|<span data-ttu-id="342a3-182">Windows</span><span class="sxs-lookup"><span data-stu-id="342a3-182">Windows</span></span>|<span data-ttu-id="342a3-183">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-183">Message</span></span>|  
|<span data-ttu-id="342a3-184">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="342a3-184">IssuedToken</span></span>|<span data-ttu-id="342a3-185">페더레이션</span><span class="sxs-lookup"><span data-stu-id="342a3-185">Federated</span></span>|<span data-ttu-id="342a3-186">페더레이션</span><span class="sxs-lookup"><span data-stu-id="342a3-186">Federated</span></span>|<span data-ttu-id="342a3-187">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-187">Message</span></span>|  
|<span data-ttu-id="342a3-188">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-188">SspiNegotiated</span></span>|<span data-ttu-id="342a3-189">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="342a3-190">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-190">Windows Sspi Negotiated</span></span>|<span data-ttu-id="342a3-191">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-191">Message</span></span>|  
|<span data-ttu-id="342a3-192">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-192">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="342a3-193">없음</span><span class="sxs-lookup"><span data-stu-id="342a3-193">None</span></span>|<span data-ttu-id="342a3-194">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-194">X509, TLS-Nego</span></span>|<span data-ttu-id="342a3-195">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-195">Message</span></span>|  
|<span data-ttu-id="342a3-196">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-196">UserNameForSslNegotiated</span></span>|<span data-ttu-id="342a3-197">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="342a3-197">User name/password</span></span>|<span data-ttu-id="342a3-198">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-198">X509, TLS-Nego</span></span>|<span data-ttu-id="342a3-199">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-199">Message</span></span>|  
|<span data-ttu-id="342a3-200">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-200">MutualSslNegotiated</span></span>|<span data-ttu-id="342a3-201">X509</span><span class="sxs-lookup"><span data-stu-id="342a3-201">X509</span></span>|<span data-ttu-id="342a3-202">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-202">X509, TLS-Nego</span></span>|<span data-ttu-id="342a3-203">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-203">Message</span></span>|  
|<span data-ttu-id="342a3-204">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-204">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="342a3-205">페더레이션</span><span class="sxs-lookup"><span data-stu-id="342a3-205">Federated</span></span>|<span data-ttu-id="342a3-206">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="342a3-206">X509, TLS-Nego</span></span>|<span data-ttu-id="342a3-207">메시지</span><span class="sxs-lookup"><span data-stu-id="342a3-207">Message</span></span>|  
  
 <span data-ttu-id="342a3-208">이러한 인증 모드를 사용하는 엔드포인트에서는 WS-SP(WS-SecurityPolicy)를 사용하여 보안 요구 사항을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-208">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="342a3-209">이 문서에서는 각 인증 모드의 보안 헤더 및 인프라 메시지 구조에 대해 설명하고 정책 및 메시지에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-209">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="342a3-210">WCF는 WS-SecureConversation를 활용 하 여 응용 프로그램 간의 다중 메시지 교환을 보호 하기 위해 보안 세션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-210">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="342a3-211">구현에 대한 자세한 내용은 아래의 "보안 세션"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-211">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="342a3-212">인증 모드 외에도 WCF는 대부분의 메시지 보안 기반 인증 모드에 적용 되는 일반적인 보호 메커니즘을 제어 하는 설정을 제공 합니다. 예를 들어 서명 순서와 암호화 작업, 알고리즘 모음, 키 파생 및 서명 확인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-212">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="342a3-213">이 문서에서는 다음과 같은 접두사와 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-213">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="342a3-214">접두사</span><span class="sxs-lookup"><span data-stu-id="342a3-214">Prefix</span></span>|<span data-ttu-id="342a3-215">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="342a3-215">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="342a3-216">초</span><span class="sxs-lookup"><span data-stu-id="342a3-216">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="342a3-217">sp</span><span class="sxs-lookup"><span data-stu-id="342a3-217">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="342a3-218">a</span><span class="sxs-lookup"><span data-stu-id="342a3-218">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="342a3-219">wsse</span><span class="sxs-lookup"><span data-stu-id="342a3-219">wsse</span></span>|<span data-ttu-id="342a3-220">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="342a3-220">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="342a3-221">wsse11</span><span class="sxs-lookup"><span data-stu-id="342a3-221">wsse11</span></span>|<span data-ttu-id="342a3-222">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="342a3-222">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="342a3-223">wsu</span><span class="sxs-lookup"><span data-stu-id="342a3-223">wsu</span></span>|<span data-ttu-id="342a3-224">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="342a3-224">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="342a3-225">ds</span><span class="sxs-lookup"><span data-stu-id="342a3-225">ds</span></span>|<span data-ttu-id="342a3-226">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="342a3-226">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="342a3-227">wst</span><span class="sxs-lookup"><span data-stu-id="342a3-227">wst</span></span>|<span data-ttu-id="342a3-228">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="342a3-228">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="342a3-229">wssc</span><span class="sxs-lookup"><span data-stu-id="342a3-229">wssc</span></span>|<span data-ttu-id="342a3-230">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="342a3-230">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="342a3-231">wsaw</span><span class="sxs-lookup"><span data-stu-id="342a3-231">wsaw</span></span>|<span data-ttu-id="342a3-232">TBD - WS-Addressing 정책 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="342a3-232">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="342a3-233">wsp</span><span class="sxs-lookup"><span data-stu-id="342a3-233">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="342a3-234">mssp</span><span class="sxs-lookup"><span data-stu-id="342a3-234">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="342a3-235">1. 토큰 프로필</span><span class="sxs-lookup"><span data-stu-id="342a3-235">1. Token Profiles</span></span>  

 <span data-ttu-id="342a3-236">Web Services Security 사양에서는 자격 증명을 보안 토큰으로서 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-236">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="342a3-237">WCF는 다음과 같은 토큰 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-237">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="342a3-238">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="342a3-238">1.1 UsernameToken</span></span>  

 <span data-ttu-id="342a3-239">WCF는 다음 제약 조건을 사용 하 여 UsernameToken10 및 UsernameToken11 프로필을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-239">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="342a3-240">UsernameToken\Password 요소의 R1101 PasswordType 특성은 생략되거나 그 값이 #PasswordText(기본값)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-240">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="342a3-241">확장성을 사용하여 #PasswordDigest를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-241">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="342a3-242">#PasswordDigest가 보안 암호 보호 메커니즘으로 잘못 인식되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-242">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="342a3-243">그러나 #PasswordDigest는 UsernameToken 암호화를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-243">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="342a3-244">#PasswordDigest의 주요 목표는 재생 공격을 방지하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-244">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="342a3-245">WCF 인증 모드에서는 메시지 서명을 사용 하 여 재생 공격 위협을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-245">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="342a3-246">B1102 WCF는 UsernameToken의 Nonce 및 Created 하위 요소를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-246">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="342a3-247">이러한 하위 요소는 재생 검색을 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-247">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="342a3-248">WCF에서는 메시지 서명을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-248">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="342a3-249">OASIS WSS SOAP Message Security UsernameToken Profile 1.1(UsernameToken11)에서는 암호로부터 키 파생 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-249">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="342a3-250">B1103 UsernameToken 암호는 키 파생에 사용할 수 없으므로 암호화 작업에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-250">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="342a3-251">설명: 암호는 일반적으로 암호화 작업에 사용하기에 너무 약합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-251">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="342a3-252">1.2 X509 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-252">1.2 X509 Token</span></span>  

 <span data-ttu-id="342a3-253">WCF는 자격 증명 형식으로 X509v3 인증서를 지원 하 고, X509TokenProfile 1.0 및 X509TokenProfile 1.1과 다음 제약 조건을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-253">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="342a3-254">R1201 BinarySecurityToken 요소의 ValueType 특성은 X509v3 인증서를 포함할 경우 #X509v3 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-254">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="342a3-255">또한 WSS X509 Token Profile 1.0 및 1.1은 #X509PKIPathv1 및 #PKCS7을 값 형식으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-255">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="342a3-256">WCF는 이러한 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-256">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="342a3-257">R1202 SKI(SubjectKeyIdentifier) 확장이 X509 인증서에 있으면 토큰에 대한 외부 참조로 wsse:KeyIdentifier를 사용해야 합니다. 이 때 ValueType 특성은 #X509SubjectKeyIdentifier이고 해당 내용에 base64 인코딩된 인증서 SKI 확장명 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-257">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="342a3-258">SKI 참조는 널리 구현되고 있으며 상호 운용성이 높은 외부 참조 형식으로 인정받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-258">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="342a3-259">R1203 X509 보안 토큰에 대한 외부 참조에는 ds:X509IssuerSerial을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-259">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="342a3-260">R1204 X509TokenProfile1.1이 사용 중인 경우 X509 보안 토큰에 대한 외부 참조에는 WS-Security 1.1을 통해 추가된 지문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-260">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="342a3-261">WCF는 X509IssuerSerial을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-261">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="342a3-262">그러나 X509IssuerSerial에는 상호 운용성 문제가 있습니다. WCF는 문자열을 사용 하 여 X509IssuerSerial 두 값을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-262">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="342a3-263">따라서 주체 이름의 구성 요소를 다시 정렬 하 고 WCF 서비스에 인증서에 대 한 참조를 보내는 경우에는 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-263">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="342a3-264">1.3 Kerberos 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-264">1.3 Kerberos Token</span></span>  

 <span data-ttu-id="342a3-265">WCF는 다음 제약 조건을 사용 하 여 Windows 인증을 위해 KerberosTokenProfile 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-265">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="342a3-266">R1301 Kerberos Token은 GSS_API 및 Kerberos 사양에 정의된 GSS 래핑된 Kerberos v4 AP_REQ 값을 사용하고, 값이 #GSS_Kerberosv5_AP_REQ인 ValueType 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-266">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="342a3-267">WCF는 완전 한 AP 요구를 사용 하는 것이 아니라 GSS 래핑된 Kerberos AP 요청을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-267">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="342a3-268">이는 최선의 보안 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-268">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="342a3-269">1.4 SAML v1.1 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-269">1.4 SAML v1.1 Token</span></span>  

 <span data-ttu-id="342a3-270">WCF는 SAML v 1.1 토큰에 대해 WSS SAML 토큰 프로필 1.0 및 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-270">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="342a3-271">또한 다른 버전의 SAML 토큰 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-271">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="342a3-272">1.5 보안 컨텍스트 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-272">1.5 Security Context Token</span></span>  

 <span data-ttu-id="342a3-273">WCF는 WS-Ws-secureconversation에 도입 된 SCT (보안 컨텍스트 토큰)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-273">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="342a3-274">SCT는 아래에 설명하는 이진 협상 프로토콜 TLS 및 SSPI를 비롯하여 SecureConversation에 설정된 보안 컨텍스트를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-274">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="342a3-275">2. 일반적인 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="342a3-275">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="342a3-276">2.1 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="342a3-276">2.1 TimeStamp</span></span>  

 <span data-ttu-id="342a3-277">타임스탬프 표시 여부는 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 클래스의 <xref:System.ServiceModel.Channels.SecurityBindingElement> 속성을 사용하여 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-277">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="342a3-278">WCF는 wsse: Created 및 wsse: Expires 필드를 사용 하 여 항상 wsse: TimeStamp를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-278">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="342a3-279">wsse:TimeStamp는 서명이 사용될 경우 항상 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-279">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="342a3-280">2.2 보호 순서</span><span class="sxs-lookup"><span data-stu-id="342a3-280">2.2 Protection Order</span></span>  

 <span data-ttu-id="342a3-281">WCF는 "암호화 전 서명" 및 "서명 전 암호화" (보안 정책 1.1) 메시지 보호 순서를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-281">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="342a3-282">WS-Security 1.1 서명 확인 메커니즘을 사용하지 않을 경우 서명 전 암호화로 보호된 메시지는 서명 대체 공격에 취약하고, 암호화된 내용에 대한 서명으로 인해 감사를 수행하기 더 어려워지므로 "암호화 전 서명"을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-282">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="342a3-283">2.3 서명 보호</span><span class="sxs-lookup"><span data-stu-id="342a3-283">2.3 Signature Protection</span></span>  

 <span data-ttu-id="342a3-284">서명 전 암호화를 사용할 경우, 특히 사용자 지정 토큰을 weak 키 자료와 함께 사용하는 경우에는 암호화된 내용이나 서명 키를 추측하기 위한 무차별 키 대입 공격을 방지해 서명을 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-284">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="342a3-285">2.4 알고리즘 모음</span><span class="sxs-lookup"><span data-stu-id="342a3-285">2.4 Algorithm Suite</span></span>  

 <span data-ttu-id="342a3-286">WCF는 보안 정책 1.1에 나열 된 모든 알고리즘 모음을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-286">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="342a3-287">2.5 키 파생</span><span class="sxs-lookup"><span data-stu-id="342a3-287">2.5 Key Derivation</span></span>  

 <span data-ttu-id="342a3-288">WCF에서는 Ws-secureconversation에 설명 된 대로 "대칭 키에 대 한 키 파생"을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-288">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="342a3-289">2.6 서명 확인</span><span class="sxs-lookup"><span data-stu-id="342a3-289">2.6 Signature Confirmation</span></span>  

 <span data-ttu-id="342a3-290">서명 확인을 사용하여 중개자의 공격으로부터 서명 집합을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-290">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="342a3-291">2.7 보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="342a3-291">2.7 Security Header Layout</span></span>  

 <span data-ttu-id="342a3-292">각 인증 모드에서는 보안 헤더에 대한 특정 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-292">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="342a3-293">보안 헤더 내의 요소는 일부 순서가 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-293">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="342a3-294">보안 헤더 자식 요소의 순서를 지정하기 위해 WS-Security 정책에서는 다음과 같은 보안 헤더 레이아웃 모드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-294">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="342a3-295">Strict</span><span class="sxs-lookup"><span data-stu-id="342a3-295">Strict</span></span>|<span data-ttu-id="342a3-296">"사용 전 선언"의 일반 원칙에 따라 보안 정책 7.7.1 단원에 설명된 번호가 매겨진 레이아웃 규칙을 따르는 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-296">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="342a3-297">Lax</span><span class="sxs-lookup"><span data-stu-id="342a3-297">Lax</span></span>|<span data-ttu-id="342a3-298">WSS: SOAP 메시지 보안에 따른 순서로 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-298">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="342a3-299">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="342a3-299">LaxTimestampFirst</span></span>|<span data-ttu-id="342a3-300">보안 헤더의 첫 번째 항목이 wsse:Timestamp여야 한다는 점을 제외하고 Lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-300">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="342a3-301">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="342a3-301">LaxTimestampLast</span></span>|<span data-ttu-id="342a3-302">보안 헤더의 마지막 항목이 wsse:Timestamp여야 한다는 점을 제외하고 lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-302">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="342a3-303">WCF는 보안 헤더 레이아웃에 대해 네 가지 모드를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-303">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="342a3-304">아래에 설명된 인증 모드에 대한 보안 헤더 구조 및 메시지 예제에서는 "Strict" 모드를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-304">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="342a3-305">2. 일반적인 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="342a3-305">2. Common Message Security Parameters</span></span>  

 <span data-ttu-id="342a3-306">이 단원에서는 클라이언트와 서비스 간에 교환되는 메시지의 보안 헤더 구조를 보여 주는 예제와 함께 각 인증 모드에 대한 예제 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-306">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="342a3-307">6.1 전송 보호</span><span class="sxs-lookup"><span data-stu-id="342a3-307">6.1 Transport Protection</span></span>  

 <span data-ttu-id="342a3-308">WCF는 보안 전송을 사용 하 여 메시지를 보호 하는 5 가지 인증 모드를 제공 합니다. UserNameOverTransport, Certificate과잉 전송, KerberosOverTransport, IssuedTokenOverTransport 및 SspiNegotiatedOverTransport입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-308">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="342a3-309">이러한 인증 모드는 SecurityPolicy에 설명된 전송 바인딩을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-309">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="342a3-310">UserNameOverTransport 인증 모드의 경우 UsernameToken이 서명된 지원 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-310">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="342a3-311">다른 인증 모드의 경우 토큰이 서명된 보증 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-311">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="342a3-312">보안 헤더 레이아웃에 대해서는 SecurityPolicy의 부록 C.1.2 및 C.1.3에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-312">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="342a3-313">다음 예제 보안 헤더에서는 지정된 인증 모드에 대한 Strict 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-313">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="342a3-314">모든 경우의 토큰에 대한 "파생 키" 속성 값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-314">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="342a3-315">전송 바인딩의 다양한 속성 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-315">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="342a3-316">타임스탬프: true</span><span class="sxs-lookup"><span data-stu-id="342a3-316">Timestamp: true</span></span>  
  
 <span data-ttu-id="342a3-317">보안 헤더 레이아웃: Strict</span><span class="sxs-lookup"><span data-stu-id="342a3-317">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="342a3-318">알고리즘 모음: Basic256</span><span class="sxs-lookup"><span data-stu-id="342a3-318">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="342a3-319">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-319">6.1.1 UsernameOverTransport</span></span>  

 <span data-ttu-id="342a3-320">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-320">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="342a3-321">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-321">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="342a3-322">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-322">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="342a3-323">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-323">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="342a3-324">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="342a3-324">Security Header Layout</span></span>  
  
 <span data-ttu-id="342a3-325">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-325">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken>  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-326">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-326">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="342a3-327">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-327">6.1.2 CertificateOverTransport</span></span>  

 <span data-ttu-id="342a3-328">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-328">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="342a3-329">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-329">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="342a3-330">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-330">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="342a3-331">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-331">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="342a3-332">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="342a3-332">Security Header Layout</span></span>  
  
 <span data-ttu-id="342a3-333">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-333">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-334">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-334">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="342a3-335">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-335">6.1.3 IssuedTokenOverTransport</span></span>  

 <span data-ttu-id="342a3-336">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS(보안 토큰 서비스)에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-336">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="342a3-337">발급된 토큰은 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-337">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="342a3-338">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-338">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="342a3-339">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-339">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="342a3-340">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-340">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="342a3-341">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="342a3-341">Security Header Layout</span></span>  
  
 <span data-ttu-id="342a3-342">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-342">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-343">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-343">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="342a3-344">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-344">6.1.4 KerberosOverTransport</span></span>  

 <span data-ttu-id="342a3-345">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-345">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="342a3-346">Kerberos 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-346">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="342a3-347">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-347">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="342a3-348">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-348">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="342a3-349">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-349">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="342a3-350">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="342a3-350">Security Header Layout</span></span>  
  
 <span data-ttu-id="342a3-351">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-351">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-352">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-352">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="342a3-353">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="342a3-353">6.1.5 SspiNegotiatedOverTransport</span></span>  

 <span data-ttu-id="342a3-354">이 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-354">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="342a3-355">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-355">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="342a3-356">결과 SCT는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-356">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="342a3-357">서비스는 전송 계층에서 X.509 인증서를 사용하여 추가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-357">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="342a3-358">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-358">The binding used is a transport binding.</span></span> <span data-ttu-id="342a3-359">"SPNEGO" (협상)에서는 WCF가 WS-TRUST와 함께 SSPI 이진 협상 프로토콜을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-359">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="342a3-360">이 단원의 보안 헤더 예제는 SPNEGO 핸드셰이크를 통해 SCT를 설정한 경우의 보안 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-360">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="342a3-361">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-361">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="342a3-362">보안 헤더 예제</span><span class="sxs-lookup"><span data-stu-id="342a3-362">Security Header Examples</span></span>  

 <span data-ttu-id="342a3-363">WS-Trust 이진 협상을 사용하여 SPNEGO 핸드셰이크를 통해 보안 컨텍스트 토큰을 설정한 경우, 애플리케이션 메시지에 다음과 같은 구조의 보안 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-363">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="342a3-364">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-364">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-365">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-365">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="342a3-366">6.2 X.509 인증서를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="342a3-366">6.2 Using X.509 Certificates for Service Authentication</span></span>  

 <span data-ttu-id="342a3-367">이 단원에서는 MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate 및 IssuedTokenForCertificate 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-367">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="342a3-368">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="342a3-368">6.2.1 MutualCertificate WSS1.0</span></span>  

 <span data-ttu-id="342a3-369">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-369">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="342a3-370">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-370">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="342a3-371">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-371">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="342a3-372">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="342a3-372">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="342a3-373">수신자 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="342a3-373">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="342a3-374">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-374">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-375">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-375">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-376">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-376">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-377">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-377">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-378">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-378">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-379">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-379">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-380">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-380">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-381">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-382">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-382">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="342a3-383">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-383">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-384">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-384">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="342a3-385">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="342a3-385">6.2.2 MutualCertificateDuplex</span></span>  

 <span data-ttu-id="342a3-386">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-386">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="342a3-387">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-387">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="342a3-388">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-388">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="342a3-389">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="342a3-389">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="342a3-390">수신자 토큰: 포함 모드가 …/IncludeToken/AlwaysToInitiator로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="342a3-390">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="342a3-391">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-391">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-392">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-392">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-393">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-393">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-394">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-394">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-395">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-395">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-396">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-396">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-397">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="342a3-397">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-398">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-398">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-399">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="342a3-399">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="342a3-400">6.2.3 X.509 서비스 인증에서 SymmetricBinding 사용</span><span class="sxs-lookup"><span data-stu-id="342a3-400">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  

 <span data-ttu-id="342a3-401">"WSS10"에서는 X509 토큰 사용 시나리오를 제한적으로 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-401">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="342a3-402">예를 들어, 서비스 X509 토큰만 사용하여 메시지에 대한 서명 및 암호화 보호를 제공할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-402">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="342a3-403">"WSS11"에서는 EncryptedKey를 대칭 토큰으로 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-403">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="342a3-404">이제 요청 메시지 보호와 응답 메시지 보호에 서비스의 X.509 인증서에 대해 암호화된 임시 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-404">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="342a3-405">아래 6.4 단원에 설명된 인증 모드에서는 이 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-405">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="342a3-406">WS-SecurityPolicy에서는 Service X509 토큰을 보호 토큰으로 사용하여 SymmetricBinding을 통해 이 패턴을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-406">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="342a3-407">AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 및 IssuedTokenForCertificate 인증 모드는 모두 다음 속성 값을 가진 비슷한 sp:SymmetricBinding 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-407">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="342a3-408">보호 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X509 인증서</span><span class="sxs-lookup"><span data-stu-id="342a3-408">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="342a3-409">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-409">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-410">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-410">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-411">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-411">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-412">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-412">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-413">위의 인증 모드는 사용하는 지원 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-413">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="342a3-414">AnonymousForCertificate의 경우 토큰이 없으며, MutualCertificate WSS 1.1의 경우 클라이언트의 X509 인증서를 보증 지원 토큰으로 사용하고, UserNameForCertificate의 경우 사용자 이름 토큰을 서명된 지원 토큰으로 사용하고, IssuedTokenForCertificate의 경우 발급된 토큰을 보증 지원 토큰으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-414">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="342a3-415">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-415">Policy</span></span>  
  
 <span data-ttu-id="342a3-416">대칭 바인딩</span><span class="sxs-lookup"><span data-stu-id="342a3-416">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="342a3-417">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-417">6.2.4 AnonymousForCertificate</span></span>  

 <span data-ttu-id="342a3-418">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-418">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="342a3-419">사용되는 바인딩은 6.4.2에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-419">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="342a3-420">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-420">Policy</span></span>  
  
 <span data-ttu-id="342a3-421">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-421">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-422">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-422">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-423">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-423">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-424">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-424">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-425">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-425">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-426">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-426">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-427">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-427">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="342a3-428">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-428">6.2.5 UserNameForCertificate</span></span>  

 <span data-ttu-id="342a3-429">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-429">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="342a3-430">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-430">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="342a3-431">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-431">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="342a3-432">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-432">Policy</span></span>  
  
 <span data-ttu-id="342a3-433">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-433">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="342a3-434">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-434">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-435">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-435">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-436">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-436">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-437">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-437">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-438">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-438">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-439">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-439">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-440">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-440">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="342a3-441">6.2.6 MutualCertificate(WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="342a3-441">6.2.6 MutualCertificate (WSS 1.1)</span></span>  

 <span data-ttu-id="342a3-442">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-442">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="342a3-443">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-443">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="342a3-444">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-444">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="342a3-445">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-445">Policy</span></span>  
  
 <span data-ttu-id="342a3-446">바인딩에 대한 자세한 내용은 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-446">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="342a3-447">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-447">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-448">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-448">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-449">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-449">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-450">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-450">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-451">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-451">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-452">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-452">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-453">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-453">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="342a3-454">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="342a3-454">6.2.7 IssuedTokenForCertificate</span></span>  

 <span data-ttu-id="342a3-455">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-455">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="342a3-456">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-456">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="342a3-457">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-457">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="342a3-458">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-458">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="342a3-459">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-459">Policy</span></span>  
  
 <span data-ttu-id="342a3-460">바인딩에 대한 자세한 내용은 위 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-460">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="342a3-461">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-461">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-462">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-462">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-463">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-463">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-464">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-464">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-465">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-465">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-466">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-466">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-467">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-467">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="342a3-468">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="342a3-468">6.3 Kerberos</span></span>  

 <span data-ttu-id="342a3-469">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-469">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="342a3-470">동일한 티켓에서 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-470">That same ticket also provides server authentication.</span></span> <span data-ttu-id="342a3-471">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-471">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="342a3-472">보호 토큰: 포함 모드가 .../IncludeToken/Once로 설정된 Kerberos 티켓</span><span class="sxs-lookup"><span data-stu-id="342a3-472">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="342a3-473">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-473">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-474">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-474">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-475">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-475">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-476">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-476">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-477">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-477">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-478">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-479">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-479">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-480">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-480">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-481">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-481">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-482">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-482">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-483">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-483">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="342a3-484">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="342a3-484">6.4 IssuedToken</span></span>  

 <span data-ttu-id="342a3-485">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-485">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="342a3-486">서비스가 클라이언트에 인증되지 않습니다. 대신 STS에서 공유 키를 발급된 토큰의 일부로 암호화하여 서비스에서만 키를 해독할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-486">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="342a3-487">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-487">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="342a3-488">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-488">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="342a3-489">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-490">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-491">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-492">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-493">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-493">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-494">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-495">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-495">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-496">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-496">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-497">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-497">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-498">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-498">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-499">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-499">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="342a3-500">6.5 SslNegotiated를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="342a3-500">6.5 Using SslNegotiated for Service Authentication</span></span>  

 <span data-ttu-id="342a3-501">이 단원에서는 보호 토큰이 WS-T(WS-Trust) RST/RSTR 메시지를 통해 TLS 프로토콜을 실행하여 그 키 값이 협상되는 WS-SC(WS-SecureConversation)별 보안 컨텍스트 토큰인 대칭 바인딩을 사용하는 인증 모드 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-501">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="342a3-502">WS-Trust를 사용하는 TLS 핸드셰이크 구현에 대한 자세한 내용은 TLSNEGO를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-502">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="342a3-503">여기의 메시지 예제에서는 연결된 보안 컨텍스트가 있는 SCT가 핸드셰이크를 통해 이미 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-503">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="342a3-504">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-504">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="342a3-505">보호 토큰: 포함 모드가 .../IncludeToken/Never로 설정된 SslContextToken</span><span class="sxs-lookup"><span data-stu-id="342a3-505">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="342a3-506">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-506">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-507">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-507">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-508">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-508">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-509">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-509">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="342a3-510">6.5.1 SslNegotiated 서비스 인증 정책</span><span class="sxs-lookup"><span data-stu-id="342a3-510">6.5.1 Policy for SslNegotiated service authentication</span></span>  

 <span data-ttu-id="342a3-511">이 단원의 모든 인증 모드에 대한 정책은 비슷하며 사용되는 특정 서명된 지원 토큰과 보증 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-511">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient'>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="342a3-512">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-512">6.5.2 AnonymousForSslNegotiated</span></span>  

 <span data-ttu-id="342a3-513">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-513">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="342a3-514">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-514">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="342a3-515">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-515">Policy</span></span>  
  
 <span data-ttu-id="342a3-516">바인딩에 대한 자세한 내용은 위 6.5.1의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-516">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-517">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-517">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-518">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-518">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-519">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-519">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-520">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-520">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-521">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-521">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-522">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-522">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="342a3-523">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-523">6.5.3 UserNameForSslNegotiated</span></span>  

 <span data-ttu-id="342a3-524">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-524">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="342a3-525">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-525">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="342a3-526">사용되는 바인딩은 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-526">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="342a3-527">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-527">Policy</span></span>  
  
 <span data-ttu-id="342a3-528">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-528">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="342a3-529">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-529">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-530">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-530">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-531">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-531">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-532">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-532">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-533">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-533">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-534">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-534">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-535">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-535">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="342a3-536">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-536">6.5.4 IssuedTokenForSslNegotiated</span></span>  

 <span data-ttu-id="342a3-537">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-537">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="342a3-538">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-538">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="342a3-539">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-539">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="342a3-540">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-540">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="342a3-541">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-541">Policy</span></span>  
  
 <span data-ttu-id="342a3-542">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-542">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="342a3-543">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-543">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-544">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-544">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-545">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-545">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-546">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-546">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-547">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-547">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-548">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-548">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-549">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-549">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="342a3-550">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-550">6.5.5 MutualSslNegotiated</span></span>  

 <span data-ttu-id="342a3-551">이 인증 모드에서 클라이언트 및 서비스는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-551">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="342a3-552">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-552">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="342a3-553">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-553">Policy</span></span>  
  
 <span data-ttu-id="342a3-554">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342a3-554">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="342a3-555">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="342a3-555">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-556">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-556">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-557">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-557">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-558">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-558">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-559">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-559">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-560">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-560">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-561">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-561">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="342a3-562">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="342a3-562">6.6 SspiNegotiated</span></span>  

 <span data-ttu-id="342a3-563">이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-563">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="342a3-564">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-564">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="342a3-565">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-565">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="342a3-566">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 SpnegoContextToken</span><span class="sxs-lookup"><span data-stu-id="342a3-566">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="342a3-567">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="342a3-567">Token Protection: False</span></span>  
  
 <span data-ttu-id="342a3-568">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="342a3-568">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="342a3-569">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="342a3-569">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="342a3-570">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="342a3-570">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="342a3-571">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-571">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-572">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-573">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-573">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-574">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-574">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-575">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-575">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-576">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-576">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-577">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-577">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="342a3-578">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="342a3-578">6.7 SecureConversation</span></span>  

 <span data-ttu-id="342a3-579">사용되는 바인딩은 보호 토큰이 WS-SC(WS-SecureConversation)별 SCT인 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-579">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="342a3-580">SCT는 그 자체가 협상 프로토콜을 사용하는 대칭 바인딩인 중첩 바인딩에 따라 WS-Trust(WS-Trust) 또는 WS-SC(WS-SecureConversation)를 사용하여 협상됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-580">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="342a3-581">협상 프로토콜은 가능하면 Kerberos를 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-581">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="342a3-582">Kerberos를 사용할 수 없는 경우 NTLM으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="342a3-582">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="342a3-583">정책</span><span class="sxs-lookup"><span data-stu-id="342a3-583">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="342a3-584">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="342a3-584">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="342a3-585">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-585">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-586">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-586">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="342a3-587">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="342a3-587">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="342a3-588">요청</span><span class="sxs-lookup"><span data-stu-id="342a3-588">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="342a3-589">응답</span><span class="sxs-lookup"><span data-stu-id="342a3-589">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
