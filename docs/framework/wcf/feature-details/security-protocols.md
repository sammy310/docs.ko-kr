---
title: 보안 프로토콜
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], protocols
ms.assetid: 57ffcbea-807c-4e43-a41c-44b3db8ed2af
ms.openlocfilehash: d09dd6bcb8564f770df6b87751aee4cdb04cd12c
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144619"
---
# <a name="security-protocols"></a><span data-ttu-id="ab4f7-102">보안 프로토콜</span><span class="sxs-lookup"><span data-stu-id="ab4f7-102">Security Protocols</span></span>
<span data-ttu-id="ab4f7-103">Web Services Security 프로토콜은 모든 기존 엔터프라이즈 메시징 보안 요구 사항을 포함하는 Web Services Security 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="ab4f7-104">이 섹션에서는 <xref:System.ServiceModel.Channels.SecurityBindingElement> 다음 웹 서비스 보안 프로토콜에 대 한 WCF (Windows Communication Foundation) 정보 (에서 구현 됨)에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-104">This section describes the Windows Communication Foundation (WCF) details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="ab4f7-105">사양/문서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-105">Specification/Document</span></span>|<span data-ttu-id="ab4f7-106">링크</span><span class="sxs-lookup"><span data-stu-id="ab4f7-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="ab4f7-107">WSS: SOAP Message Security 1.0</span><span class="sxs-lookup"><span data-stu-id="ab4f7-107">WSS: SOAP Message Security 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|  
|<span data-ttu-id="ab4f7-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="ab4f7-108">WSS: Username Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|  
|<span data-ttu-id="ab4f7-109">WSS: X509 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="ab4f7-109">WSS: X509 Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|  
|<span data-ttu-id="ab4f7-110">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="ab4f7-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|  
|<span data-ttu-id="ab4f7-111">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="ab4f7-111">WSS: SOAP Message Security 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|  
|<span data-ttu-id="ab4f7-112">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ab4f7-112">WSS Username Token Profile 1.1</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|  
|<span data-ttu-id="ab4f7-113">WSS: X.509 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ab4f7-113">WSS: X.509 Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|  
|<span data-ttu-id="ab4f7-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ab4f7-114">WSS: Kerberos Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|  
|<span data-ttu-id="ab4f7-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ab4f7-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|  
|<span data-ttu-id="ab4f7-116">WS-Secure Conversation 1.3</span><span class="sxs-lookup"><span data-stu-id="ab4f7-116">WS-Secure Conversation 1.3</span></span>|<http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512/ws-secureconversation-1.3-os.pdf>|  
|<span data-ttu-id="ab4f7-117">WS-Trust  1.3</span><span class="sxs-lookup"><span data-stu-id="ab4f7-117">WS-Trust 1.3</span></span>|<http://docs.oasis-open.org/ws-sx/ws-trust/200512/ws-trust-1.3-os.pdf>|  
|<span data-ttu-id="ab4f7-118">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="ab4f7-118">Application Note:</span></span><br /><br /> <span data-ttu-id="ab4f7-119">WS-Trust for TLS Handshake 사용</span><span class="sxs-lookup"><span data-stu-id="ab4f7-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="ab4f7-120">게시 예정</span><span class="sxs-lookup"><span data-stu-id="ab4f7-120">To be published</span></span>|  
|<span data-ttu-id="ab4f7-121">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="ab4f7-121">Application Note:</span></span><br /><br /> <span data-ttu-id="ab4f7-122">WS-Trust for SPNEGO 사용</span><span class="sxs-lookup"><span data-stu-id="ab4f7-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="ab4f7-123">게시 예정</span><span class="sxs-lookup"><span data-stu-id="ab4f7-123">To be published</span></span>|  
|<span data-ttu-id="ab4f7-124">애플리케이션 참고:</span><span class="sxs-lookup"><span data-stu-id="ab4f7-124">Application Note:</span></span><br /><br /> <span data-ttu-id="ab4f7-125">Web Services Addressing 엔드포인트 참조 및 ID</span><span class="sxs-lookup"><span data-stu-id="ab4f7-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="ab4f7-126">게시 예정</span><span class="sxs-lookup"><span data-stu-id="ab4f7-126">To be published</span></span>|  
|<span data-ttu-id="ab4f7-127">WS-SecurityPolicy 1.2(2007/04)</span><span class="sxs-lookup"><span data-stu-id="ab4f7-127">WS-SecurityPolicy 1.2 (2007/04)</span></span>|<http://www.oasis-open.org/committees/download.php/23821/ws-securitypolicy-1.2-spec-cs.pdf>|  
  
 <span data-ttu-id="ab4f7-128">WCF, 버전 1은 웹 서비스 보안 구성의 기반으로 사용할 수 있는 17 개의 인증 모드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-128">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="ab4f7-129">각 모드는 다음과 같은 공통 배포 요구 사항에 대해 최적화된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-129">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="ab4f7-130">클라이언트와 서비스를 인증하는 데 사용되는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="ab4f7-130">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="ab4f7-131">메시지 또는 전송 보안 보호 메커니즘</span><span class="sxs-lookup"><span data-stu-id="ab4f7-131">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="ab4f7-132">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="ab4f7-132">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="ab4f7-133">인증 모드</span><span class="sxs-lookup"><span data-stu-id="ab4f7-133">Authentication Mode</span></span>|<span data-ttu-id="ab4f7-134">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="ab4f7-134">Client Authentication</span></span>|<span data-ttu-id="ab4f7-135">서버 인증</span><span class="sxs-lookup"><span data-stu-id="ab4f7-135">Server Authentication</span></span>|<span data-ttu-id="ab4f7-136">모드</span><span class="sxs-lookup"><span data-stu-id="ab4f7-136">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="ab4f7-137">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-137">UserNameOverTransport</span></span>|<span data-ttu-id="ab4f7-138">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="ab4f7-138">User name/password</span></span>|<span data-ttu-id="ab4f7-139">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-139">X509</span></span>|<span data-ttu-id="ab4f7-140">전송</span><span class="sxs-lookup"><span data-stu-id="ab4f7-140">Transport</span></span>|  
|<span data-ttu-id="ab4f7-141">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-141">CertificateOverTransport</span></span>|<span data-ttu-id="ab4f7-142">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-142">X509</span></span>|<span data-ttu-id="ab4f7-143">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-143">X509</span></span>|<span data-ttu-id="ab4f7-144">전송</span><span class="sxs-lookup"><span data-stu-id="ab4f7-144">Transport</span></span>|  
|<span data-ttu-id="ab4f7-145">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-145">KerberosOverTransport</span></span>|<span data-ttu-id="ab4f7-146">Windows</span><span class="sxs-lookup"><span data-stu-id="ab4f7-146">Windows</span></span>|<span data-ttu-id="ab4f7-147">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-147">X509</span></span>|<span data-ttu-id="ab4f7-148">전송</span><span class="sxs-lookup"><span data-stu-id="ab4f7-148">Transport</span></span>|  
|<span data-ttu-id="ab4f7-149">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-149">IssuedTokenOverTransport</span></span>|<span data-ttu-id="ab4f7-150">페더레이션</span><span class="sxs-lookup"><span data-stu-id="ab4f7-150">Federated</span></span>|<span data-ttu-id="ab4f7-151">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-151">X509</span></span>|<span data-ttu-id="ab4f7-152">전송</span><span class="sxs-lookup"><span data-stu-id="ab4f7-152">Transport</span></span>|  
|<span data-ttu-id="ab4f7-153">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-153">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="ab4f7-154">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-154">Windows Sspi Negotiated</span></span>|<span data-ttu-id="ab4f7-155">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-155">Windows Sspi Negotiated</span></span>|<span data-ttu-id="ab4f7-156">전송</span><span class="sxs-lookup"><span data-stu-id="ab4f7-156">Transport</span></span>|  
|<span data-ttu-id="ab4f7-157">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-157">AnonymousForCertificate</span></span>|<span data-ttu-id="ab4f7-158">없음</span><span class="sxs-lookup"><span data-stu-id="ab4f7-158">None</span></span>|<span data-ttu-id="ab4f7-159">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-159">X509</span></span>|<span data-ttu-id="ab4f7-160">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-160">Message</span></span>|  
|<span data-ttu-id="ab4f7-161">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-161">UserNameForCertificate</span></span>|<span data-ttu-id="ab4f7-162">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="ab4f7-162">User name/password</span></span>|<span data-ttu-id="ab4f7-163">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-163">X509</span></span>|<span data-ttu-id="ab4f7-164">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-164">Message</span></span>|  
|<span data-ttu-id="ab4f7-165">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-165">MutualCertificate</span></span>|<span data-ttu-id="ab4f7-166">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-166">X509</span></span>|<span data-ttu-id="ab4f7-167">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-167">X509</span></span>|<span data-ttu-id="ab4f7-168">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-168">Message</span></span>|  
|<span data-ttu-id="ab4f7-169">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="ab4f7-169">MutualCertificateDuplex</span></span>|<span data-ttu-id="ab4f7-170">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-170">X509</span></span>|<span data-ttu-id="ab4f7-171">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-171">X509</span></span>|<span data-ttu-id="ab4f7-172">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-172">Message</span></span>|  
|<span data-ttu-id="ab4f7-173">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-173">IssuedTokenForCertificate</span></span>|<span data-ttu-id="ab4f7-174">페더레이션</span><span class="sxs-lookup"><span data-stu-id="ab4f7-174">Federated</span></span>|<span data-ttu-id="ab4f7-175">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-175">X509</span></span>|<span data-ttu-id="ab4f7-176">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-176">Message</span></span>|  
|<span data-ttu-id="ab4f7-177">Kerberos</span><span class="sxs-lookup"><span data-stu-id="ab4f7-177">Kerberos</span></span>|<span data-ttu-id="ab4f7-178">Windows</span><span class="sxs-lookup"><span data-stu-id="ab4f7-178">Windows</span></span>|<span data-ttu-id="ab4f7-179">Windows</span><span class="sxs-lookup"><span data-stu-id="ab4f7-179">Windows</span></span>|<span data-ttu-id="ab4f7-180">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-180">Message</span></span>|  
|<span data-ttu-id="ab4f7-181">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="ab4f7-181">IssuedToken</span></span>|<span data-ttu-id="ab4f7-182">페더레이션</span><span class="sxs-lookup"><span data-stu-id="ab4f7-182">Federated</span></span>|<span data-ttu-id="ab4f7-183">페더레이션</span><span class="sxs-lookup"><span data-stu-id="ab4f7-183">Federated</span></span>|<span data-ttu-id="ab4f7-184">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-184">Message</span></span>|  
|<span data-ttu-id="ab4f7-185">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-185">SspiNegotiated</span></span>|<span data-ttu-id="ab4f7-186">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-186">Windows Sspi Negotiated</span></span>|<span data-ttu-id="ab4f7-187">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-187">Windows Sspi Negotiated</span></span>|<span data-ttu-id="ab4f7-188">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-188">Message</span></span>|  
|<span data-ttu-id="ab4f7-189">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-189">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="ab4f7-190">없음</span><span class="sxs-lookup"><span data-stu-id="ab4f7-190">None</span></span>|<span data-ttu-id="ab4f7-191">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-191">X509, TLS-Nego</span></span>|<span data-ttu-id="ab4f7-192">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-192">Message</span></span>|  
|<span data-ttu-id="ab4f7-193">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-193">UserNameForSslNegotiated</span></span>|<span data-ttu-id="ab4f7-194">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="ab4f7-194">User name/password</span></span>|<span data-ttu-id="ab4f7-195">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-195">X509, TLS-Nego</span></span>|<span data-ttu-id="ab4f7-196">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-196">Message</span></span>|  
|<span data-ttu-id="ab4f7-197">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-197">MutualSslNegotiated</span></span>|<span data-ttu-id="ab4f7-198">X509</span><span class="sxs-lookup"><span data-stu-id="ab4f7-198">X509</span></span>|<span data-ttu-id="ab4f7-199">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-199">X509, TLS-Nego</span></span>|<span data-ttu-id="ab4f7-200">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-200">Message</span></span>|  
|<span data-ttu-id="ab4f7-201">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-201">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="ab4f7-202">페더레이션</span><span class="sxs-lookup"><span data-stu-id="ab4f7-202">Federated</span></span>|<span data-ttu-id="ab4f7-203">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="ab4f7-203">X509, TLS-Nego</span></span>|<span data-ttu-id="ab4f7-204">메시지</span><span class="sxs-lookup"><span data-stu-id="ab4f7-204">Message</span></span>|  
  
 <span data-ttu-id="ab4f7-205">이러한 인증 모드를 사용하는 엔드포인트에서는 WS-SP(WS-SecurityPolicy)를 사용하여 보안 요구 사항을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-205">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="ab4f7-206">이 문서에서는 각 인증 모드의 보안 헤더 및 인프라 메시지 구조에 대해 설명하고 정책 및 메시지에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-206">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="ab4f7-207">WCF는 WS-Ws-secureconversation를 활용 하 여 응용 프로그램 간의 다중 메시지 교환을 보호 하기 위해 보안 세션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-207">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="ab4f7-208">구현에 대한 자세한 내용은 아래의 "보안 세션"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-208">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="ab4f7-209">인증 모드 외에도 WCF는 대부분의 메시지 보안 기반 인증 모드에 적용 되는 일반적인 보호 메커니즘을 제어 하는 설정을 제공 합니다. 예를 들어 서명 순서와 암호화 작업, 알고리즘 모음, 키 파생 및 서명 확인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-209">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="ab4f7-210">이 문서에서는 다음과 같은 접두사와 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-210">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="ab4f7-211">접두사</span><span class="sxs-lookup"><span data-stu-id="ab4f7-211">Prefix</span></span>|<span data-ttu-id="ab4f7-212">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ab4f7-212">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="ab4f7-213">s</span><span class="sxs-lookup"><span data-stu-id="ab4f7-213">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|  
|<span data-ttu-id="ab4f7-214">sp</span><span class="sxs-lookup"><span data-stu-id="ab4f7-214">sp</span></span>|`http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702`|  
|<span data-ttu-id="ab4f7-215">a</span><span class="sxs-lookup"><span data-stu-id="ab4f7-215">a</span></span>|`http://www.w3.org/2005/08/addressing`|  
|<span data-ttu-id="ab4f7-216">wsse</span><span class="sxs-lookup"><span data-stu-id="ab4f7-216">wsse</span></span>|<span data-ttu-id="ab4f7-217">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="ab4f7-217">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="ab4f7-218">wsse11</span><span class="sxs-lookup"><span data-stu-id="ab4f7-218">wsse11</span></span>|<span data-ttu-id="ab4f7-219">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="ab4f7-219">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="ab4f7-220">wsu</span><span class="sxs-lookup"><span data-stu-id="ab4f7-220">wsu</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd`|  
|<span data-ttu-id="ab4f7-221">ds</span><span class="sxs-lookup"><span data-stu-id="ab4f7-221">ds</span></span>|<span data-ttu-id="ab4f7-222">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="ab4f7-222">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="ab4f7-223">wst</span><span class="sxs-lookup"><span data-stu-id="ab4f7-223">wst</span></span>|<span data-ttu-id="ab4f7-224">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="ab4f7-224">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="ab4f7-225">wssc</span><span class="sxs-lookup"><span data-stu-id="ab4f7-225">wssc</span></span>|<span data-ttu-id="ab4f7-226">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="ab4f7-226">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="ab4f7-227">wsaw</span><span class="sxs-lookup"><span data-stu-id="ab4f7-227">wsaw</span></span>|`http://www.w3.org/2006/05/addressing/wsdl`|  
|<span data-ttu-id="ab4f7-228">wsp</span><span class="sxs-lookup"><span data-stu-id="ab4f7-228">wsp</span></span>|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|<span data-ttu-id="ab4f7-229">mssp</span><span class="sxs-lookup"><span data-stu-id="ab4f7-229">mssp</span></span>|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="ab4f7-230">1. 토큰 프로필</span><span class="sxs-lookup"><span data-stu-id="ab4f7-230">1. Token Profiles</span></span>  
 <span data-ttu-id="ab4f7-231">Web Services Security 사양에서는 자격 증명을 보안 토큰으로서 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-231">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="ab4f7-232">WCF는 다음과 같은 토큰 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-232">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="ab4f7-233">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="ab4f7-233">1.1 UsernameToken</span></span>  
 <span data-ttu-id="ab4f7-234">WCF는 다음 제약 조건을 사용 하 여 UsernameToken10 및 UsernameToken11 프로필을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-234">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="ab4f7-235">UsernameToken\Password 요소의 R1101 PasswordType 특성은 생략되거나 그 값이 #PasswordText(기본값)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-235">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="ab4f7-236">확장성을 사용하여 #PasswordDigest를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-236">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="ab4f7-237">#PasswordDigest가 보안 암호 보호 메커니즘으로 잘못 인식되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-237">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="ab4f7-238">그러나 #PasswordDigest는 UsernameToken 암호화를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-238">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="ab4f7-239">#PasswordDigest의 주요 목표는 재생 공격을 방지하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-239">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="ab4f7-240">WCF 인증 모드에서는 메시지 서명을 사용 하 여 재생 공격 위협을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-240">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="ab4f7-241">B1102 WCF는 UsernameToken의 Nonce 및 Created 하위 요소를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-241">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="ab4f7-242">이러한 하위 요소는 재생 검색을 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-242">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="ab4f7-243">WCF에서는 메시지 서명을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-243">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="ab4f7-244">OASIS WSS SOAP Message Security UsernameToken Profile 1.1(UsernameToken11)에서는 암호로부터 키 파생 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-244">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="ab4f7-245">B1103 UsernameToken 암호는 키 파생에 사용할 수 없으므로 암호화 작업에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-245">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="ab4f7-246">설명: 암호는 일반적으로 암호화 작업에 사용하기에 너무 약합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-246">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="ab4f7-247">1.2 X509 토큰</span><span class="sxs-lookup"><span data-stu-id="ab4f7-247">1.2 X509 Token</span></span>  
 <span data-ttu-id="ab4f7-248">WCF는 자격 증명 형식으로 X509v3 인증서를 지원 하 고, X509TokenProfile 1.0 및 X509TokenProfile 1.1과 다음 제약 조건을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-248">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="ab4f7-249">R1201 BinarySecurityToken 요소의 ValueType 특성은 X509v3 인증서를 포함할 경우 #X509v3 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-249">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="ab4f7-250">또한 WSS X509 Token Profile 1.0 및 1.1은 #X509PKIPathv1 및 #PKCS7을 값 형식으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-250">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="ab4f7-251">WCF는 이러한 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-251">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="ab4f7-252">R1202 SKI(SubjectKeyIdentifier) 확장이 X509 인증서에 있으면 토큰에 대한 외부 참조로 wsse:KeyIdentifier를 사용해야 합니다. 이 때 ValueType 특성은 #X509SubjectKeyIdentifier이고 해당 내용에 base64 인코딩된 인증서 SKI 확장명 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-252">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="ab4f7-253">SKI 참조는 널리 구현되고 있으며 상호 운용성이 높은 외부 참조 형식으로 인정받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-253">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="ab4f7-254">R1203 X509 보안 토큰에 대한 외부 참조에는 ds:X509IssuerSerial을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-254">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="ab4f7-255">R1204 X509TokenProfile1.1이 사용 중인 경우 X509 보안 토큰에 대한 외부 참조에는 WS-Security 1.1을 통해 추가된 지문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-255">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="ab4f7-256">WCF는 X509IssuerSerial을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-256">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="ab4f7-257">그러나 X509IssuerSerial에는 상호 운용성 문제가 있습니다. WCF는 문자열을 사용 하 여 X509IssuerSerial 두 값을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-257">However there are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="ab4f7-258">따라서 주체 이름의 구성 요소를 다시 정렬 하 고 WCF 서비스에 인증서에 대 한 참조를 보내는 경우에는 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-258">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="ab4f7-259">1.3 Kerberos 토큰</span><span class="sxs-lookup"><span data-stu-id="ab4f7-259">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="ab4f7-260">WCF는 다음 제약 조건을 사용 하 여 Windows 인증을 위해 KerberosTokenProfile 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-260">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="ab4f7-261">R1301 Kerberos Token은 GSS_API 및 Kerberos 사양에 정의된 GSS 래핑된 Kerberos v4 AP_REQ 값을 사용하고, 값이 #GSS_Kerberosv5_AP_REQ인 ValueType 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-261">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="ab4f7-262">WCF는 완전 한 AP 요구를 사용 하는 것이 아니라 GSS 래핑된 Kerberos AP 요청을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-262">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="ab4f7-263">이는 최선의 보안 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-263">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="ab4f7-264">1.4 SAML v1.1 토큰</span><span class="sxs-lookup"><span data-stu-id="ab4f7-264">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="ab4f7-265">WCF는 SAML v 1.1 토큰에 대해 WSS SAML 토큰 프로필 1.0 및 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-265">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="ab4f7-266">또한 다른 버전의 SAML 토큰 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-266">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="ab4f7-267">1.5 보안 컨텍스트 토큰</span><span class="sxs-lookup"><span data-stu-id="ab4f7-267">1.5 Security Context Token</span></span>  
 <span data-ttu-id="ab4f7-268">WCF는 WS-Ws-secureconversation에 도입 된 SCT (보안 컨텍스트 토큰)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-268">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="ab4f7-269">SCT는 아래에 설명하는 이진 협상 프로토콜 TLS 및 SSPI를 비롯하여 SecureConversation에 설정된 보안 컨텍스트를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-269">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="ab4f7-270">2. 일반적인 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab4f7-270">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="ab4f7-271">2.1 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="ab4f7-271">2.1 TimeStamp</span></span>  
 <span data-ttu-id="ab4f7-272">타임스탬프 표시 여부는 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 클래스의 <xref:System.ServiceModel.Channels.SecurityBindingElement> 속성을 사용하여 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-272">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="ab4f7-273">WCF는 wsse: Created 및 wsse: Expires 필드를 사용 하 여 항상 wsse: TimeStamp를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-273">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="ab4f7-274">wsse:TimeStamp는 서명이 사용될 경우 항상 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-274">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="ab4f7-275">2.2 보호 순서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-275">2.2 Protection Order</span></span>  
 <span data-ttu-id="ab4f7-276">WCF는 "암호화 전 서명" 및 "서명 전 암호화" (보안 정책 1.2) 메시지 보호 순서를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-276">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.2).</span></span> <span data-ttu-id="ab4f7-277">WS-Security 1.1 서명 확인 메커니즘을 사용하지 않을 경우 서명 전 암호화로 보호된 메시지는 서명 대체 공격에 취약하고, 암호화된 내용에 대한 서명으로 인해 감사를 수행하기 더 어려워지므로 "암호화 전 서명"을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-277">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="ab4f7-278">2.3 서명 보호</span><span class="sxs-lookup"><span data-stu-id="ab4f7-278">2.3 Signature Protection</span></span>  
 <span data-ttu-id="ab4f7-279">서명 전 암호화를 사용할 경우, 특히 사용자 지정 토큰을 weak 키 자료와 함께 사용하는 경우에는 암호화된 내용이나 서명 키를 추측하기 위한 무차별 키 대입 공격을 방지해 서명을 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-279">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="ab4f7-280">2.4 알고리즘 모음</span><span class="sxs-lookup"><span data-stu-id="ab4f7-280">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="ab4f7-281">WCF는 보안 정책 1.2에 나열 된 모든 알고리즘 모음을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-281">WCF supports all algorithm suites listed in Security Policy 1.2.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="ab4f7-282">2.5 키 파생</span><span class="sxs-lookup"><span data-stu-id="ab4f7-282">2.5 Key Derivation</span></span>  
 <span data-ttu-id="ab4f7-283">WCF에서는 Ws-secureconversation에 설명 된 대로 "대칭 키에 대 한 키 파생"을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-283">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="ab4f7-284">2.6 서명 확인</span><span class="sxs-lookup"><span data-stu-id="ab4f7-284">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="ab4f7-285">서명 확인을 사용하여 중개자의 공격으로부터 서명 집합을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-285">Signature confirmation can be used as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="ab4f7-286">2.7 보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab4f7-286">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="ab4f7-287">각 인증 모드에서는 보안 헤더에 대한 특정 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-287">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="ab4f7-288">보안 헤더 내의 요소는 일부 순서가 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-288">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="ab4f7-289">보안 헤더 자식 요소의 순서를 지정하기 위해 WS-Security 정책에서는 다음과 같은 보안 헤더 레이아웃 모드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-289">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab4f7-290">Strict</span><span class="sxs-lookup"><span data-stu-id="ab4f7-290">Strict</span></span>|<span data-ttu-id="ab4f7-291">"사용 전 선언"의 일반 원칙에 따라 보안 정책 7.7.1 단원에 설명된 번호가 매겨진 레이아웃 규칙을 따르는 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-291">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="ab4f7-292">Lax</span><span class="sxs-lookup"><span data-stu-id="ab4f7-292">Lax</span></span>|<span data-ttu-id="ab4f7-293">WSS: SOAP 메시지 보안에 따른 순서로 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-293">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="ab4f7-294">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="ab4f7-294">LaxTimestampFirst</span></span>|<span data-ttu-id="ab4f7-295">보안 헤더의 첫 번째 항목이 wsse:Timestamp여야 한다는 점을 제외하고 Lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-295">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="ab4f7-296">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="ab4f7-296">LaxTimestampLast</span></span>|<span data-ttu-id="ab4f7-297">보안 헤더의 마지막 항목이 wsse:Timestamp여야 한다는 점을 제외하고 lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-297">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="ab4f7-298">WCF는 보안 헤더 레이아웃에 대해 네 가지 모드를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-298">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="ab4f7-299">아래에 설명된 인증 모드에 대한 보안 헤더 구조 및 메시지 예제에서는 "Strict" 모드를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-299">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="3-common-message-security-parameters"></a><span data-ttu-id="ab4f7-300">3. 일반적인 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab4f7-300">3. Common Message Security Parameters</span></span>  
 <span data-ttu-id="ab4f7-301">이 단원에서는 클라이언트와 서비스 간에 교환되는 메시지의 보안 헤더 구조를 보여 주는 예제와 함께 각 인증 모드에 대한 예제 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-301">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="31-transport-protection"></a><span data-ttu-id="ab4f7-302">3.1 전송 보호</span><span class="sxs-lookup"><span data-stu-id="ab4f7-302">3.1 Transport Protection</span></span>  
 <span data-ttu-id="ab4f7-303">WCF는 보안 전송을 사용 하 여 메시지를 보호 하는 5 가지 인증 모드를 제공 합니다. UserNameOverTransport, Certificate과잉 전송, KerberosOverTransport, IssuedTokenOverTransport 및 SspiNegotiatedOverTransport입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-303">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="ab4f7-304">이러한 인증 모드는 SecurityPolicy에 설명된 전송 바인딩을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-304">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="ab4f7-305">UserNameOverTransport 인증 모드의 경우 UsernameToken이 서명된 지원 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-305">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="ab4f7-306">다른 인증 모드의 경우 토큰이 서명된 보증 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-306">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="ab4f7-307">보안 헤더 레이아웃에 대해서는 SecurityPolicy의 부록 C.1.2 및 C.1.3에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-307">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="ab4f7-308">다음 예제 보안 헤더에서는 지정된 인증 모드에 대한 Strict 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-308">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="ab4f7-309">모든 경우의 토큰에 대한 "파생 키" 속성 값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-309">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="ab4f7-310">전송 바인딩의 다양한 속성 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-310">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="ab4f7-311">타임스탬프: true</span><span class="sxs-lookup"><span data-stu-id="ab4f7-311">Timestamp: true</span></span>  
  
 <span data-ttu-id="ab4f7-312">보안 헤더 레이아웃: Strict</span><span class="sxs-lookup"><span data-stu-id="ab4f7-312">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="ab4f7-313">알고리즘 모음: Basic256</span><span class="sxs-lookup"><span data-stu-id="ab4f7-313">Algorithm Suite: Basic256</span></span>  
  
#### <a name="311-usernameovertransport"></a><span data-ttu-id="ab4f7-314">3.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-314">3.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="ab4f7-315">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-315">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="ab4f7-316">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-316">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="ab4f7-317">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-317">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="ab4f7-318">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-318">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="ab4f7-319">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab4f7-319">Security Header Layout</span></span>  
  
 <span data-ttu-id="ab4f7-320">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-320">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:UsernameToken u:Id="uuid-b96fbb3a-e646-4403-9473-2e5ffc733ff8-1"> ... </o:UsernameToken></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-321">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-321">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="312-certificateovertransport"></a><span data-ttu-id="ab4f7-322">3.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-322">3.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="ab4f7-323">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-323">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="ab4f7-324">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-324">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="ab4f7-325">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-325">The binding used is a transport binding.</span></span> <span data-ttu-id="ab4f7-326">CertificateOverTransport는 SOAP 헤더에만 서명하고 SOAP 본문에는 서명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-326">CertificateOverTransport only signs the SOAP headers, not the SOAP body.</span></span> <span data-ttu-id="ab4f7-327">이는 TransportWithMessageCredentials 보안 모드에서 사용되는 인증 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-327">This is the authentication mode used by the TransportWithMessageCredentials security mode.</span></span> <span data-ttu-id="ab4f7-328">인증이 메시지 자격 증명을 사용하여 수행되므로 SOAP 헤더에만 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-328">Only the SOAP headers are signed because authentication is done by using message credentials.</span></span>  
  
 <span data-ttu-id="ab4f7-329">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-329">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="CertificateOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="ab4f7-330">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab4f7-330">Security Header Layout</span></span>  
  
 <span data-ttu-id="ab4f7-331">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-331">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-332">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-332">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="313-issuedtokenovertransport"></a><span data-ttu-id="ab4f7-333">3.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-333">3.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="ab4f7-334">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS(보안 토큰 서비스)에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-334">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="ab4f7-335">발급된 토큰은 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-335">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="ab4f7-336">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-336">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="ab4f7-337">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-337">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="ab4f7-338">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-338">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenOverTransport_policy">
 <wsp:ExactlyOne>
  <wsp:All>
   <sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:TransportToken>
      <wsp:Policy>
       <sp:HttpsToken />
      </wsp:Policy>
     </sp:TransportToken>
     <sp:AlgorithmSuite>
      <wsp:Policy>
       <sp:Basic256 />
      </wsp:Policy>
     </sp:AlgorithmSuite>
     <sp:Layout>
      <wsp:Policy>
       <sp:Strict/>
      </wsp:Policy>
     </sp:Layout>
     <sp:IncludeTimestamp/>
    </wsp:Policy>
   </sp:TransportBinding>
   <sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient">
      <Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
       <Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address>
       <Metadata xmlns="http://www.w3.org/2005/08/addressing">
        <Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
         <wsx:MetadataSection xmlns="">
          <wsx:MetadataReference>
           <Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address>
           <Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity">
            <Dns> ...  </Dns>
           </Identity>
          </wsx:MetadataReference>
         </wsx:MetadataSection>
        </Metadata>
       </Metadata>
      </Issuer>
      <sp:RequestSecurityTokenTemplate>
       <trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType>
      </sp:RequestSecurityTokenTemplate>
      <wsp:Policy>
       <sp:RequireInternalReference/>
      </wsp:Policy>
     </sp:IssuedToken>
     <sp:SignedParts>
      <sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/>
     </sp:SignedParts>
    </wsp:Policy>
   </sp:EndorsingSupportingTokens>
   <sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/>
     <sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/>
    </wsp:Policy>
   </sp:Wss11>
   <sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:MustSupportIssuedTokens/>
     <sp:RequireClientEntropy/>
     <sp:RequireServerEntropy/>
    </wsp:Policy>
   </sp:Trust13>
   <wsaw:UsingAddressing/>
  </wsp:All>
 </wsp:ExactlyOne>
</wsp:Policy>
```  
  
 <span data-ttu-id="ab4f7-339">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab4f7-339">Security Header Layout</span></span>  
  
 <span data-ttu-id="ab4f7-340">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-340">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-67692bb6-85b7-4299-8587-3ce60086b0d2-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-fab7e1b2-8dc4-412b-bda9-b95a4f836815-16" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-341">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-341">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-fab7e1b2-8dc4-412b-bda9-b95a4f836815-21"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
#### <a name="314-kerberosovertransport"></a><span data-ttu-id="ab4f7-342">3.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-342">3.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="ab4f7-343">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-343">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="ab4f7-344">Kerberos 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-344">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="ab4f7-345">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="ab4f7-346">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-346">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="ab4f7-347">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-347">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="KerberosOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="ab4f7-348">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab4f7-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="ab4f7-349">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-349">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-350">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-350">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="315-sspinegotiatedovertransport"></a><span data-ttu-id="ab4f7-351">3.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="ab4f7-351">3.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="ab4f7-352">이 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-352">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="ab4f7-353">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-353">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="ab4f7-354">결과 SCT는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-354">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="ab4f7-355">서비스는 전송 계층에서 X.509 인증서를 사용하여 추가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-355">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-356">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-356">The binding used is a transport binding.</span></span> <span data-ttu-id="ab4f7-357">"SPNEGO" (협상)에서는 WCF가 WS-TRUST와 함께 SSPI 이진 협상 프로토콜을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-357">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="ab4f7-358">이 단원의 보안 헤더 예제는 SPNEGO 핸드셰이크를 통해 SCT를 설정한 경우의 보안 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-358">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="ab4f7-359">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-359">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiatedOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="ab4f7-360">보안 헤더 예제</span><span class="sxs-lookup"><span data-stu-id="ab4f7-360">Security Header Examples</span></span>  
 <span data-ttu-id="ab4f7-361">WS-Trust 이진 협상을 사용하여 SPNEGO 핸드셰이크를 통해 보안 컨텍스트 토큰을 설정한 경우, 애플리케이션 메시지에 다음과 같은 구조의 보안 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-361">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="ab4f7-362">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-362">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-9a29d087-5dae-4d40-bf86-5746d9d30eca-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-363">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-363">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
### <a name="32-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="ab4f7-364">3.2 서비스 인증에 x.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="ab4f7-364">3.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="ab4f7-365">이 단원에서는 MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate 및 IssuedTokenForCertificate 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-365">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="321-mutualcertificate-wss10"></a><span data-ttu-id="ab4f7-366">3.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="ab4f7-366">3.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="ab4f7-367">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-367">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="ab4f7-368">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-368">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-369">SOAP 헤더와 SOAP 본문이 둘 다 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-369">Both the SOAP headers and the SOAP body are signed.</span></span> <span data-ttu-id="ab4f7-370">대칭 키가 만들어지고 받는 사람에 대한 전송 인증서를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-370">A symmetric key is created and is encrypted with the transport certificate for the recipient.</span></span>  
  
 <span data-ttu-id="ab4f7-371">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-371">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="ab4f7-372">개시자 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-372">Initiator Token: the client’s X.509 certificate, with inclusion mode set to .../IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="ab4f7-373">수신자 토큰: 포함 모드가 .../IncludeToken/Never로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-373">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set .../IncludeToken/Never</span></span>  
  
 <span data-ttu-id="ab4f7-374">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-374">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-375">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-375">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-376">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-376">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-377">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-377">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-378">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-378">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss10 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/></wsp:Policy></sp:Wss10><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-379">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-379">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-380">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-380">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-39cb393e-9da8-4d5d-b273-540ef614569b-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-381">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-381">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"> <u:Timestamp u:Id="uuid-3d742930-70d3-4d7e-aa0a-8721128dc115-8"> ... </u:Timestamp><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_5" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-382">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-382">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss10 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/></wsp:Policy></sp:Wss10><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-383">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-383">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-384">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-384">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-73da3e21-abff-4294-a910-e75303d280cc-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-385">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-385">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-02f276b6-804f-480d-99e9-2e90fc76ab27-3"> ... </u:Timestamp><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="322-mutualcertificateduplex"></a><span data-ttu-id="ab4f7-386">3.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="ab4f7-386">3.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="ab4f7-387">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-387">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="ab4f7-388">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-388">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="ab4f7-389">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-389">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="ab4f7-390">개시자 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-390">Initiator Token: Client’s X509 Certificate, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="ab4f7-391">수신자 토큰: 포함 모드가 .../IncludeToken/AlwaysToInitiator로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-391">Recipient Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="ab4f7-392">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-392">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-393">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-393">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-394">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-394">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-395">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-395">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-396">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-396">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificateDuplex_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToInitiator"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><cdp:CompositeDuplex xmlns:cdp="http://schemas.microsoft.com/net/2006/06/duplex"/><ow:OneWay xmlns:ow="http://schemas.microsoft.com/ws/2005/05/routing/policy"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-397">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-397">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-398">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-398">Request and Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-4dec3da4-b572-4654-ba4d-4a2f84a87510-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-399">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-399">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificateDuplex_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToInitiator"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><cdp:CompositeDuplex xmlns:cdp="http://schemas.microsoft.com/net/2006/06/duplex"/><ow:OneWay xmlns:ow="http://schemas.microsoft.com/ws/2005/05/routing/policy"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-400">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-400">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-401">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-401">Request and Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b0e23feb-cd2d-4dc1-bad9-284bc45f3be3-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="323-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="ab4f7-402">3.2.3 X.509 서비스 인증에서 SymmetricBinding 사용</span><span class="sxs-lookup"><span data-stu-id="ab4f7-402">3.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="ab4f7-403">"WSS10"에서는 X509 토큰 사용 시나리오를 제한적으로 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-403">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="ab4f7-404">예를 들어, 서비스 X509 토큰만 사용하여 메시지에 대한 서명 및 암호화 보호를 제공할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-404">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="ab4f7-405">"WSS11"에서는 EncryptedKey를 대칭 토큰으로 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-405">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="ab4f7-406">이제 요청 메시지 보호와 응답 메시지 보호에 서비스의 X.509 인증서에 대해 암호화된 임시 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-406">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="ab4f7-407">아래 3.4 단원에 설명 된 인증 모드에서는이 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-407">The authentication modes described in the section 3.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="ab4f7-408">WS-SecurityPolicy에서는 Service X509 토큰을 보호 토큰으로 사용하여 SymmetricBinding을 통해 이 패턴을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-408">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="ab4f7-409">AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 및 IssuedTokenForCertificate 인증 모드는 모두 다음 속성 값을 가진 비슷한 sp:SymmetricBinding 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-409">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="ab4f7-410">보호 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X509 인증서</span><span class="sxs-lookup"><span data-stu-id="ab4f7-410">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="ab4f7-411">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-411">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-412">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-412">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-413">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-413">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-414">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-414">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-415">위의 인증 모드는 사용하는 지원 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-415">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="ab4f7-416">AnonymousForCertificate의 경우 토큰이 없으며, MutualCertificate WSS 1.1의 경우 클라이언트의 X509 인증서를 보증 지원 토큰으로 사용하고, UserNameForCertificate의 경우 사용자 이름 토큰을 서명된 지원 토큰으로 사용하고, IssuedTokenForCertificate의 경우 발급된 토큰을 보증 지원 토큰으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-416">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
#### <a name="324-anonymousforcertificate"></a><span data-ttu-id="ab4f7-417">3.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-417">3.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="ab4f7-418">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-418">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-419">사용되는 바인딩은 3.4.2에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-419">The binding used is an instance of symmetric binding as described in 3.4.2.</span></span>  
  
 <span data-ttu-id="ab4f7-420">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-420">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousforCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-421">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-422">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-422">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-4de2d2a1-6266-4a02-93e6-242a1ac2aeb3-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-4de2d2a1-6266-4a02-93e6-242a1ac2aeb3-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-423">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-423">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b06cb481-3176-4c56-af35-c38252bb6c78-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_2" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-424">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-424">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousforCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-425">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-425">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-426">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-426">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-562aac68-8cdd-45d5-bc03-df662e6ed048-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-562aac68-8cdd-45d5-bc03-df662e6ed048-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-427">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-427">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-15b48260-23da-424d-8dc4-8f4e150fb8cf-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><k:SignatureConfirmation u:Id="_2" Value="ALF+QNGmWn2k3LpWEDIzSBgTkvo=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="325-usernameforcertificate"></a><span data-ttu-id="ab4f7-428">3.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-428">3.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="ab4f7-429">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-429">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="ab4f7-430">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-430">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-431">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-431">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="ab4f7-432">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-432">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><http:BasicAuthentication xmlns:http="http://schemas.microsoft.com/ws/06/2004/policy/http"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-433">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-433">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-434">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-434">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-27196139-acb9-410f-a2c6-51d20d24278b-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-27196139-acb9-410f-a2c6-51d20d24278b-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-435">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-435">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-681226f7-126a-4806-b732-fcca097cd7a8-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-436">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-436">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><http:BasicAuthentication xmlns:http="http://schemas.microsoft.com/ws/06/2004/policy/http"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-437">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-438">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-438">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8276d8b7-74a0-4257-b8a5-e25350e7c2d4-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-8276d8b7-74a0-4257-b8a5-e25350e7c2d4-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-439">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-439">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8a7ad353-f071-49dc-90dd-5ad2e9abd40a-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="326-mutualcertificate-wss-11"></a><span data-ttu-id="ab4f7-440">3.2.6 MutualCertificate(WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="ab4f7-440">3.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="ab4f7-441">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="ab4f7-442">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-443">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="ab4f7-444">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-444">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-445">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-445">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-446">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-446">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-75305d4e-f54f-4e36-9de9-45b6d2053c80-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-75305d4e-f54f-4e36-9de9-45b6d2053c80-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_2" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><o:BinarySecurityToken> ...</o:BinarySecurityToken><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_10" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-447">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-447">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8c73fa91-f95b-40ff-b088-48118e6fadcf-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_3" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_10" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-448">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-448">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-449">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-449">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-450">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-450">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-0b940a9e-606f-43b9-b05d-a162043529bc-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-0b940a9e-606f-43b9-b05d-a162043529bc-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature Id="_2" xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-451">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-451">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-67dacc31-4a50-4866-b673-ccc03e156337-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><k:SignatureConfirmation u:Id="_2" Value="mYyksUQKkK27Fd6hmgOiqFwvudk=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><k:SignatureConfirmation u:Id="_3" Value="SreOZ4Rr2BcXjFQFvgN55ERypI/1/86hdWThE5lav0eYIxF1OCzQgZF+y7cQ82t+g3CRnLbE3c52DqMpY/HXlrdMct3m3rnpDH+fqdhNY4fE+M2v4zUMFR7uxDKWcEm9zZpmUvJCDfJRfKRaKjy5cTbccRKqSxw7HAqOYnqibA4=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="327-issuedtokenforcertificate"></a><span data-ttu-id="ab4f7-452">3.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="ab4f7-452">3.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="ab4f7-453">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-453">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="ab4f7-454">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-454">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="ab4f7-455">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-455">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-456">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-456">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="ab4f7-457">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-457">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-458">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-458">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-459">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-459">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-1d2c03e6-0b69-4483-903a-6ef9b9d286ed-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-3f0f57fa-046d-40c0-919f-d0d7aa640b9f-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-460">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-460">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-3f0f57fa-046d-40c0-919f-d0d7aa640b9f-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-461">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-461">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-462">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-462">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="ab4f7-463">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-463">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-de1c51aa-2ecc-4e70-b6bd-9dca58331fa7-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-96c5e80a-9b87-4c6f-af77-752ca65cf607-16" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-464">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-464">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-96c5e80a-9b87-4c6f-af77-752ca65cf607-21"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
## <a name="33-kerberos"></a><span data-ttu-id="ab4f7-465">3.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="ab4f7-465">3.3 Kerberos</span></span>  
 <span data-ttu-id="ab4f7-466">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-466">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="ab4f7-467">동일한 티켓에서 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-467">That same ticket also provides server authentication.</span></span> <span data-ttu-id="ab4f7-468">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-468">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="ab4f7-469">보호 토큰: 포함 모드가 .../IncludeToken/Once로 설정된 Kerberos 티켓</span><span class="sxs-lookup"><span data-stu-id="ab4f7-469">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="ab4f7-470">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-470">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-471">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-471">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-472">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-472">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-473">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-473">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-474">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-474">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="Kerberos_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:RequireDerivedKeys/><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-475">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-475">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-476">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-476">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e8f6dc3b-407d-4387-bd33-97aedfd8bf13-2"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-477">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-477">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7b03568e-66ae-49da-82ee-5d12d372876e-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-478">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-478">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="Kerberos_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:RequireDerivedKeys/><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-479">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-479">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-480">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-480">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d29247f0-f220-4e81-9a8d-a15f5ac31072-2"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-481">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-481">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9025b930-4f15-42fe-8e78-35d3a3480177-2"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="34-issuedtoken"></a><span data-ttu-id="ab4f7-482">3.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="ab4f7-482">3.4 IssuedToken</span></span>  
 <span data-ttu-id="ab4f7-483">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-483">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="ab4f7-484">서비스가 클라이언트에 인증되지 않습니다. 대신 STS에서 공유 키를 발급된 토큰의 일부로 암호화하여 서비스에서만 키를 해독할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-484">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="ab4f7-485">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-485">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="ab4f7-486">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="ab4f7-486">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="ab4f7-487">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-487">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-488">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-488">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-489">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-489">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-490">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-490">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-491">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-491">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedToken_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-492">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-492">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-493">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-493">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-61ce3989-bc38-4d67-8262-6232c9d49a26-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-7e2d2617-1c28-465a-be30-de4a78cfc0e2-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-494">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-494">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7e2d2617-1c28-465a-be30-de4a78cfc0e2-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>
```  
  
 <span data-ttu-id="ab4f7-495">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-495">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedToken_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-496">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-497">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-497">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-1dc8bdef-4202-4e08-8a5e-ab94da579dec-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-7e004f51-63a3-4069-9b03-6a1a311a3181-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-498">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-498">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7e004f51-63a3-4069-9b03-6a1a311a3181-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> </c:DerivedKeyToken> ... <c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
### <a name="35-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="ab4f7-499">3.5 서비스 인증을 위해 협상 된 SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-499">3.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="ab4f7-500">이 단원에서는 보호 토큰이 WS-T(WS-Trust) RST/RSTR 메시지를 통해 TLS 프로토콜을 실행하여 그 키 값이 협상되는 WS-SC(WS-SecureConversation)별 보안 컨텍스트 토큰인 대칭 바인딩을 사용하는 인증 모드 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="ab4f7-501">WS-Trust를 사용하는 TLS 핸드셰이크 구현에 대한 자세한 내용은 TLSNEGO를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="ab4f7-502">여기의 메시지 예제에서는 연결된 보안 컨텍스트가 있는 SCT가 핸드셰이크를 통해 이미 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="ab4f7-503">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="ab4f7-504">보호 토큰: 포함 모드가 .../IncludeToken/Never로 설정된 SslContextToken</span><span class="sxs-lookup"><span data-stu-id="ab4f7-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="ab4f7-505">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-506">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-507">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-508">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-508">Encrypt Signature: True</span></span>  
  
#### <a name="351-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="ab4f7-509">3.5.1 SslNegotiated 서비스 인증 정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-509">3.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="ab4f7-510">이 단원의 모든 인증 모드에 대한 정책은 비슷하며 사용되는 특정 서명된 지원 토큰과 보증 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
#### <a name="352-anonymousforsslnegotiated"></a><span data-ttu-id="ab4f7-511">3.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-511">3.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="ab4f7-512">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-513">사용되는 바인딩은 위 3.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-513">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="ab4f7-514">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-514">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-515">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-515">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-516">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-516">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f4b86ce2-4ba6-4c55-bac1-2e920fc6d5db-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-d21ec2b8-99f5-443c-a4c6-a4d40619187e-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-517">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-517">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d21ec2b8-99f5-443c-a4c6-a4d40619187e-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-518">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-518">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-519">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-520">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-520">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-c84b24b9-39e0-4cc3-99e2-cec088f1b9eb-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-df206ad9-1ee2-46d7-9fb4-6e4631c9762f-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-521">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-521">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-df206ad9-1ee2-46d7-9fb4-6e4631c9762f-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="353-usernameforsslnegotiated"></a><span data-ttu-id="ab4f7-522">3.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-522">3.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="ab4f7-523">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="ab4f7-524">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-525">사용되는 바인딩은 3.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-525">The binding used is an instance of symmetric binding as described in 3.5.1.</span></span>  
  
 <span data-ttu-id="ab4f7-526">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-526">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-527">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-527">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-528">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-528">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-3d1a12c3-e690-474a-a223-a346fc0329a9-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-137ea768-7d49-404b-87eb-f11d9c7154aa-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-529">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-529">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-137ea768-7d49-404b-87eb-f11d9c7154aa-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-530">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-530">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-531">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-531">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-532">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-532">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-56e931e8-20c2-457f-a83e-8fcd6b92c258-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-83d053cb-03a0-4461-9616-86475cf083c4-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-533">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-533">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-83d053cb-03a0-4461-9616-86475cf083c4-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="354-issuedtokenforsslnegotiated"></a><span data-ttu-id="ab4f7-534">3.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-534">3.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="ab4f7-535">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-535">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="ab4f7-536">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-536">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="ab4f7-537">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-537">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="ab4f7-538">사용되는 바인딩은 위 3.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-538">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="ab4f7-539">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-539">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ... </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-540">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-540">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-541">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-541">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b19fb2e7-8f0c-45c1-b62c-45d6ff6d57e7-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-199509f9-7963-42b7-b340-7598ee261d5a-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-542">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-542">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-199509f9-7963-42b7-b340-7598ee261d5a-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-543">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-543">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ... </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-544">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-544">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-545">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-545">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d75104d5-313e-440f-b112-db8aff57a5fe-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-e668caab-b7e4-4056-ac42-4015ae2a67a6-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-546">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-546">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e668caab-b7e4-4056-ac42-4015ae2a67a6-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
#### <a name="355-mutualsslnegotiated"></a><span data-ttu-id="ab4f7-547">3.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-547">3.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="ab4f7-548">이 인증 모드에서 클라이언트 및 서비스는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-548">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="ab4f7-549">사용되는 바인딩은 위 3.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-549">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="ab4f7-550">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-550">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><mssp:RequireClientCertificate/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-551">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-551">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-552">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-552">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d1e6037e-8a64-494f-9447-07d3125b81b5-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-e4b73625-3011-4f6d-a6f9-4d682e860801-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-553">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-553">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e4b73625-3011-4f6d-a6f9-4d682e860801-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-554">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-554">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><mssp:RequireClientCertificate/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-555">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-555">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-556">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-556">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-c2a6ab10-889a-4ee1-871d-05410c90fc10-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-ede0bd89-1f7e-4453-96ed-13e58c7ba8fe-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-557">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-557">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-ede0bd89-1f7e-4453-96ed-13e58c7ba8fe-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
### <a name="36-sspinegotiated"></a><span data-ttu-id="ab4f7-558">3.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="ab4f7-558">3.6 SspiNegotiated</span></span>  
 <span data-ttu-id="ab4f7-559">이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-559">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="ab4f7-560">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-560">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="ab4f7-561">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-561">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="ab4f7-562">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 SpnegoContextToken</span><span class="sxs-lookup"><span data-stu-id="ab4f7-562">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="ab4f7-563">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="ab4f7-563">Token Protection: False</span></span>  
  
 <span data-ttu-id="ab4f7-564">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-564">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="ab4f7-565">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="ab4f7-565">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="ab4f7-566">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="ab4f7-566">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="ab4f7-567">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-567">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-568">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-568">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-569">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-569">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9a954fcb-4df2-4610-9800-f542f2b5130a-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-554d8cfc-e956-43db-9abb-afcafd024347-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-570">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-570">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-554d8cfc-e956-43db-9abb-afcafd024347-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>
```  
  
 <span data-ttu-id="ab4f7-571">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-571">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-572">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-572">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-573">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-573">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f1673773-f9a7-4b43-b13b-405e7dd4a6e3-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-e0aabc81-6942-4fe6-81bc-9def184565ea-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-574">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-574">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e0aabc81-6942-4fe6-81bc-9def184565ea-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
### <a name="37-secureconversation"></a><span data-ttu-id="ab4f7-575">3.7 Ws-secureconversation</span><span class="sxs-lookup"><span data-stu-id="ab4f7-575">3.7 SecureConversation</span></span>  
 <span data-ttu-id="ab4f7-576">사용되는 바인딩은 보호 토큰이 WS-SC(WS-SecureConversation)별 SCT인 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-576">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="ab4f7-577">SCT는 그 자체가 협상 프로토콜을 사용하는 대칭 바인딩인 중첩 바인딩에 따라 WS-Trust(WS-Trust) 또는 WS-SC(WS-SecureConversation)를 사용하여 협상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-577">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="ab4f7-578">협상 프로토콜은 가능하면 Kerberos를 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-578">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="ab4f7-579">Kerberos를 사용할 수 없는 경우 NTLM으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-579">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="ab4f7-580">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-580">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SecureConversation_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SecureConversationToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:BootstrapPolicy><wsp:Policy><sp:SignedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="From" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="FaultTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="ReplyTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="MessageID" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="RelatesTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="Action" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts><sp:EncryptedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/></sp:EncryptedParts><sp:SymmetricBinding xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust10 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust10></wsp:Policy></sp:BootstrapPolicy><sp:MustNotSendAmend/></wsp:Policy></sp:SecureConversationToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="ab4f7-581">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="ab4f7-581">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="ab4f7-582">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-582">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f01c6159-f159-454d-bd97-bbcc9b8e25d3-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-582920d7-14a7-4adc-8091-e1f92d7d8055-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-583">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-583">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-582920d7-14a7-4adc-8091-e1f92d7d8055-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-584">정책</span><span class="sxs-lookup"><span data-stu-id="ab4f7-584">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SecureConversation_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SecureConversationToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:BootstrapPolicy><wsp:Policy><sp:SignedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="From" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="FaultTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="ReplyTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="MessageID" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="RelatesTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="Action" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts><sp:EncryptedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/></sp:EncryptedParts><sp:SymmetricBinding xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust10 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust10></wsp:Policy></sp:BootstrapPolicy><sp:MustNotSendAmend/></wsp:Policy></sp:SecureConversationToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="ab4f7-585">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="ab4f7-585">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="ab4f7-586">요청</span><span class="sxs-lookup"><span data-stu-id="ab4f7-586">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d57e6342-1c68-4095-a0c1-41979088a944-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-9b22407d-b914-4c41-9105-1cf8cf7c3fe5-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="ab4f7-587">응답</span><span class="sxs-lookup"><span data-stu-id="ab4f7-587">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9b22407d-b914-4c41-9105-1cf8cf7c3fe5-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```
