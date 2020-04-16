---
title: 트랜잭션 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: a775ca395e01e7ecbc676ba3ec97d19ae10b4f49
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464026"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="676fc-102">트랜잭션 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="676fc-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="676fc-103">WCF(Windows 통신 재단) 버전 1은 WS-원자 트랜잭션 및 WS 조정 프로토콜의 버전 1.0을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="676fc-104">버전 1.1에 대한 자세한 내용은 [트랜잭션 프로토콜을](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="676fc-104">For more information about version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="676fc-105">사양/문서</span><span class="sxs-lookup"><span data-stu-id="676fc-105">Specification/Document</span></span>|<span data-ttu-id="676fc-106">링크</span><span class="sxs-lookup"><span data-stu-id="676fc-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="676fc-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="676fc-107">WS-Coordination</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="676fc-108">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="676fc-108">WS-AtomicTransaction</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="676fc-109">이러한 프로토콜 사양에서의 상호 운용성은 애플리케이션 간 및 트랜잭션 관리자 간 이렇게 두 가지 수준에서 필요합니다(다음 그림 참조)</span><span class="sxs-lookup"><span data-stu-id="676fc-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="676fc-110">사양은 두 가지 수준의 상호 운용성을 위한 메시지 형식 및 메시지 교환을 상세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="676fc-111">애플리케이션 간의 교환을 위한 보안, 안정성 및 인코딩은 일반적인 애플리케이션 교환을 위해 수행되는 것과 같은 방식으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="676fc-112">그러나 트랜잭션 관리자 간의 상호 운용성을 위해서는 특정한 바인딩에 대한 동의가 필요합니다. 이러한 부분은 일반적으로 사용자가 구성하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="676fc-113">이 항목에서는 WS-AT(WS-Atomic Transaction) 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="676fc-114">이 문서에서 설명하는 방식은 IBM, IONA, Sun Microsystems 등에서 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="676fc-115">다음 그림에서는 트랜잭션 관리자 1과 트랜잭션 관리자 2의 두 트랜잭션 관리자와 응용 프로그램 1 및 응용 프로그램 2 간의 상호 운용성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![트랜잭션 관리자 간의 상호 작용을 보여 주는 스크린샷입니다.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="676fc-117">한 명의 개시자(I)와 한 명의 참가자(P)가 있는 일반적인 WS-Coordination/WS-Atomic Transaction 시나리오를 예로 들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="676fc-118">개시자와 참가자는 둘 다 트랜잭션 관리자(각각 ITM과 PTM)를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="676fc-119">이 항목에서는 2단계 커밋을 2PC라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="676fc-120">1. 만들기조정컨텍스트</span><span class="sxs-lookup"><span data-stu-id="676fc-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="676fc-121">12. 응용 프로그램 메시지 응답</span><span class="sxs-lookup"><span data-stu-id="676fc-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="676fc-122">2. 만들기조정컨텍스트응답</span><span class="sxs-lookup"><span data-stu-id="676fc-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="676fc-123">13. 커밋 (완료)</span><span class="sxs-lookup"><span data-stu-id="676fc-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="676fc-124">3. 등록 (완료)</span><span class="sxs-lookup"><span data-stu-id="676fc-124">3. Register (Completion)</span></span>|<span data-ttu-id="676fc-125">14. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="676fc-126">4. 레지스터응답</span><span class="sxs-lookup"><span data-stu-id="676fc-126">4. RegisterResponse</span></span>|<span data-ttu-id="676fc-127">15. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="676fc-128">5. 응용 프로그램 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-128">5. Application Message</span></span>|<span data-ttu-id="676fc-129">16. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="676fc-130">6. 컨텍스트를 사용하여 조정컨텍스트 생성</span><span class="sxs-lookup"><span data-stu-id="676fc-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="676fc-131">17. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="676fc-132">7. 등록 (내구성)</span><span class="sxs-lookup"><span data-stu-id="676fc-132">7. Register (Durable)</span></span>|<span data-ttu-id="676fc-133">18. 커밋 (완료)</span><span class="sxs-lookup"><span data-stu-id="676fc-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="676fc-134">8. 레지스터응답</span><span class="sxs-lookup"><span data-stu-id="676fc-134">8. RegisterResponse</span></span>|<span data-ttu-id="676fc-135">19. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="676fc-136">9. 만들기조정컨텍스트응답</span><span class="sxs-lookup"><span data-stu-id="676fc-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="676fc-137">20. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="676fc-138">10. 등록 (내구성)</span><span class="sxs-lookup"><span data-stu-id="676fc-138">10. Register (Durable)</span></span>|<span data-ttu-id="676fc-139">21. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="676fc-140">11. 레지스터응답</span><span class="sxs-lookup"><span data-stu-id="676fc-140">11. RegisterResponse</span></span>|<span data-ttu-id="676fc-141">22. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="676fc-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="676fc-142">이 문서에서는 WS-AtomicTransaction 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="676fc-143">이 문서에서 설명하는 방식은 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="676fc-144">그림과 표에서는 보안의 관점에서 메시지에 대한 4가지 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="676fc-145">활성화 메시지(CreateCoordinationContext 및 CreateCoordinationContextResponse)</span><span class="sxs-lookup"><span data-stu-id="676fc-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="676fc-146">등록 메시지(Register 및 RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="676fc-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="676fc-147">프로토콜 메시지(준비, 롤백, 커밋, 중단 등)</span><span class="sxs-lookup"><span data-stu-id="676fc-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="676fc-148">애플리케이션 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-148">Application messages.</span></span>  
  
 <span data-ttu-id="676fc-149">처음 세 개의 메시지 클래스는 트랜잭션 관리자 메시지로 간주되며, 해당 바인딩 구성은 이 항목의 뒷부분에 있는 &quot;애플리케이션 메시지 교환&quot;에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="676fc-150">네 번째 메시지는 애플리케이션 간 메시지이며, 이 항목의 뒷부분에 있는 &quot;메시지 예제&quot; 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="676fc-151">이 섹션에서는 WCF에서 이러한 각 클래스에 사용되는 프로토콜 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="676fc-152">다음 XML 네임스페이스 및 관련 접두사는 이 문서 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="676fc-153">접두사</span><span class="sxs-lookup"><span data-stu-id="676fc-153">Prefix</span></span>|<span data-ttu-id="676fc-154">네임스페이스 URI</span><span class="sxs-lookup"><span data-stu-id="676fc-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="676fc-155">s11</span><span class="sxs-lookup"><span data-stu-id="676fc-155">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="676fc-156">wsa</span><span class="sxs-lookup"><span data-stu-id="676fc-156">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="676fc-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="676fc-157">wscoor</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|<span data-ttu-id="676fc-158">wsat</span><span class="sxs-lookup"><span data-stu-id="676fc-158">wsat</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|<span data-ttu-id="676fc-159">t</span><span class="sxs-lookup"><span data-stu-id="676fc-159">t</span></span>|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|<span data-ttu-id="676fc-160">o</span><span class="sxs-lookup"><span data-stu-id="676fc-160">o</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="676fc-161">xsd</span><span class="sxs-lookup"><span data-stu-id="676fc-161">xsd</span></span>|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="676fc-162">트랜잭션 관리자 바인딩</span><span class="sxs-lookup"><span data-stu-id="676fc-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="676fc-163">R1001: 트랜잭션 관리자는 WS-Atomic Transaction 및 WS-Coordination 메시지 교환을 위해 SOAP 1.1과 WS-Addressing 2004/08을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="676fc-164">애플리케이션 메시지는 이러한 바인딩에 제한되지 않으며, 이에 대해서는 나중에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="676fc-165">트랜잭션 관리자 HTTPS 바인딩</span><span class="sxs-lookup"><span data-stu-id="676fc-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="676fc-166">트랜잭션 관리자 HTTPS 바인딩은 전송 보안에만 전적으로 의존하여 보안을 수행하며, 트랜잭션 트리에 있는 각 발신자-수신자 쌍 간의 신뢰를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="676fc-167">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="676fc-168">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="676fc-169">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="676fc-170">R1111: 연결을 통해 표시되는 X.509 인증서에는 원래 컴퓨터의 FQDN(정규화된 도메인 이름)과 일치하는 주체 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="676fc-171">B1112: DNS는 X.509 주체 이름을 확인한 시스템에서 각 발신자-수신자 쌍 간에 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="676fc-172">바인딩 구성 활성화 및 등록</span><span class="sxs-lookup"><span data-stu-id="676fc-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="676fc-173">WCF는 HTTPS에 대한 상관 관계와 요청/회신 이중 바인딩이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="676fc-174">요청/회신 메시지 교환 패턴의 상관 관계 및 설명에 대한 자세한 내용은 8단원 WS-Atomic Transaction을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="676fc-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="676fc-175">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="676fc-176">WCF는 HTTPS를 통해 단방향(데이터그램) 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="676fc-177">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="676fc-178">B2131: 구현은 `wsa:ReferenceParameters` WCF의 2PC 메시지와 상관 관계를 달성하기 위해 WS 주소 지정에 설명된 대로 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="676fc-179">트랜잭션 관리자가 혼합된 보안 바인딩</span><span class="sxs-lookup"><span data-stu-id="676fc-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="676fc-180">이 바인딩은 ID 를 수립하기 위해 WS-Coordination 발급 토큰 모델과 결합된 전송 보안을 사용하는 대체(혼합 모드) 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="676fc-181">두 바인딩 간에 다른 요소는 활성화와 등록뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="676fc-182">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="676fc-183">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="676fc-184">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="676fc-185">활성화 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="676fc-186">활성화 메시지는 일반적으로 애플리케이션과 해당 로컬 트랜잭션 관리자 간에 발생하기 때문에 대개 상호 운용성에 관여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="676fc-187">B1221: WCF는 활성화 메시지에 대해 이중 HTTPS [바인딩(메시징 프로토콜에 설명)을](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="676fc-188">요청 및 회신 메시지는 WS-Addressing 2004/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="676fc-189">8단원 WS-Atomic Transaction 사양에서는 상관 관계 및 메시지 교환 패턴에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="676fc-190">R1222: 코디네이터는 `CreateCoordinationContext`를 수신하는 즉시 연관된 비밀 `SecurityContextToken`로 `STx`을 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="676fc-191">이 토큰은 WS-Trust 사양을 따르는 `t:IssuedTokens` 헤더의 내부로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="676fc-192">R1223: 기존 코디네이션 컨텍스트 내에서 활성화가 수행되면 기존 컨텍스트와 연관된 `t:IssuedTokens`과 함께 `SecurityContextToken` 헤더가 `CreateCoordinationContext` 메시지에서 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="676fc-193">나가는 `wscoor:CreateCoordinationContextResponse` `t:IssuedTokens` 메시지에 연결하기 위해 새 헤더를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="676fc-194">등록 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="676fc-195">B1231: WCF는 이중 HTTPS 바인딩을 [사용합니다(메시징 프로토콜에](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)설명).</span><span class="sxs-lookup"><span data-stu-id="676fc-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="676fc-196">요청 및 회신 메시지는 WS-Addressing 2004/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="676fc-197">8단원 WS-AtomicTransaction에서는 메시지 교환 패턴의 상관 관계 및 설명에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="676fc-198">R1232: 나가는 `wscoor:Register` 메시지는 보안 `IssuedTokenOverTransport` 프로토콜에 설명된 인증 모드를 사용해야 [합니다.](../../../../docs/framework/wcf/feature-details/security-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="676fc-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="676fc-199">발행된 `wsse:Timestamp` 요소를 사용하여 `SecurityContextToken STx` 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="676fc-200">이 서명은 특정 트랜잭션과 연관된 토큰을 소유했음을 나타내며, 트랜잭션에 등록된 참가자를 인증하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="676fc-201">RegistrationResponse 메시지는 HTTPS를 통해 다시 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="676fc-202">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="676fc-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="676fc-203">WCF는 HTTPS를 통해 단방향(데이터그램) 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="676fc-204">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="676fc-205">B2131: 구현은 `wsa:ReferenceParameters` WCF의 2PC 메시지와 상관 관계를 달성하기 위해 WS 주소 지정에 설명된 대로 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="676fc-206">애플리케이션 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="676fc-206">Application Message Exchange</span></span>  
 <span data-ttu-id="676fc-207">바인딩이 다음 보안 요구 사항을 만족하는 경우, 애플리케이션에서는 애플리케이션 간 메시지에 대해 특정 바인딩을 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="676fc-208">R2001: 애플리케이션 간 메시지는 메시지의 헤더에서 `t:IssuedTokens`와 함께 `CoordinationContext` 헤더를 이동시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="676fc-209">R2002: `t:IssuedToken`의 무결성 및 기밀성이 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="676fc-210">`CoordinationContext` 헤더에는 `wscoor:Identifier`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="676fc-211">정의는 절대 `xsd:AnyURI` URI와 상대 URI를 모두 사용할 수 `wscoor:Identifiers`있지만 WCF는 절대 URI인 경우에만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="676fc-212">의 `wscoor:Identifier` 가 `wscoor:CoordinationContext` 상대URI인 경우 트랜잭션 WCF 서비스에서 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="676fc-213">메시지 예제</span><span class="sxs-lookup"><span data-stu-id="676fc-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="676fc-214">CreateCoordinationContext 요청/응답 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="676fc-215">다음 메시지는 요청/응답 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="676fc-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="676fc-216">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</wsu:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</wsu:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="676fc-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="676fc-217">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="676fc-218">등록 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-218">Registration Messages</span></span>  
 <span data-ttu-id="676fc-219">다음 메시지는 등록 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="676fc-220">등록</span><span class="sxs-lookup"><span data-stu-id="676fc-220">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="676fc-221">응답 등록</span><span class="sxs-lookup"><span data-stu-id="676fc-221">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="676fc-222">2단계 커밋 프로토콜 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="676fc-223">다음 메시지는 2PC(2단계 커밋) 프로토콜과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="676fc-224">Commit</span><span class="sxs-lookup"><span data-stu-id="676fc-224">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="676fc-225">애플리케이션 메시지</span><span class="sxs-lookup"><span data-stu-id="676fc-225">Application Messages</span></span>  
 <span data-ttu-id="676fc-226">다음 메시지는 애플리케이션 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="676fc-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="676fc-227">애플리케이션 메시지-요청</span><span class="sxs-lookup"><span data-stu-id="676fc-227">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken
          wssu:Id="IA_Certificate"
          ValueType="...#X509v3"
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader>  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader>
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->
    <e:EncryptedData Id="encrypted_body"
           Type="http://www.w3.org/2001/04/xmlenc#Content"
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
