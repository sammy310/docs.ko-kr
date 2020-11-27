---
title: 트랜잭션 프로토콜
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 08ce12109d89e9087ced06be409435ac8c5b9d08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261542"
---
# <a name="transaction-protocols"></a><span data-ttu-id="26751-102">트랜잭션 프로토콜</span><span class="sxs-lookup"><span data-stu-id="26751-102">Transaction Protocols</span></span>

<span data-ttu-id="26751-103">WCF (Windows Communication Foundation)는 WS-Atomic 트랜잭션과 WS-Coordination 프로토콜을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="26751-104">사양/문서</span><span class="sxs-lookup"><span data-stu-id="26751-104">Specification/Document</span></span>|<span data-ttu-id="26751-105">버전</span><span class="sxs-lookup"><span data-stu-id="26751-105">Version</span></span>|<span data-ttu-id="26751-106">링크</span><span class="sxs-lookup"><span data-stu-id="26751-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="26751-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="26751-107">WS-Coordination</span></span>|<span data-ttu-id="26751-108">1.0</span><span class="sxs-lookup"><span data-stu-id="26751-108">1.0</span></span><br /><br /> <span data-ttu-id="26751-109">1.1</span><span class="sxs-lookup"><span data-stu-id="26751-109">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="26751-110">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="26751-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="26751-111">1.0</span><span class="sxs-lookup"><span data-stu-id="26751-111">1.0</span></span><br /><br /> <span data-ttu-id="26751-112">1.1</span><span class="sxs-lookup"><span data-stu-id="26751-112">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
  
 <span data-ttu-id="26751-113">이러한 프로토콜 사양에서의 상호 운용성은 애플리케이션 간 및 트랜잭션 관리자 간 이렇게 두 가지 수준에서 필요합니다(다음 그림 참조)</span><span class="sxs-lookup"><span data-stu-id="26751-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="26751-114">사양은 두 가지 수준의 상호 운용성을 위한 메시지 형식 및 메시지 교환을 상세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="26751-115">애플리케이션 간의 교환을 위한 보안, 안정성 및 인코딩은 일반적인 애플리케이션 교환을 위해 수행되는 것과 같은 방식으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="26751-116">그러나 트랜잭션 관리자 간의 상호 운용성을 위해서는 특정한 바인딩에 대한 동의가 필요합니다. 이러한 부분은 일반적으로 사용자가 구성하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="26751-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="26751-117">이 항목에서는 WS-AT(WS-Atomic Transaction) 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="26751-118">이 문서에서 설명하는 방식은 IBM, IONA, Sun Microsystems 등에서 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26751-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="26751-119">다음 그림은 두 개의 트랜잭션 관리자, 트랜잭션 관리자 1과 트랜잭션 관리자 2, 응용 프로그램 1과 응용 프로그램 2의 상호 운용성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26751-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![트랜잭션 관리자 간의 상호 작용을 보여 주는 스크린샷](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="26751-121">한 명의 개시자(I)와 한 명의 참가자(P)가 있는 일반적인 WS-Coordination/WS-Atomic Transaction 시나리오를 예로 들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="26751-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="26751-122">개시자와 참가자는 둘 다 트랜잭션 관리자(각각 ITM과 PTM)를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="26751-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="26751-123">이 항목에서는 2단계 커밋을 2PC라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26751-124">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="26751-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="26751-125">12. 응용 프로그램 메시지 응답</span><span class="sxs-lookup"><span data-stu-id="26751-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="26751-126">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="26751-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="26751-127">13. 커밋 (완료)</span><span class="sxs-lookup"><span data-stu-id="26751-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="26751-128">3. Register (완료)</span><span class="sxs-lookup"><span data-stu-id="26751-128">3. Register (Completion)</span></span>|<span data-ttu-id="26751-129">14. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="26751-130">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="26751-130">4. RegisterResponse</span></span>|<span data-ttu-id="26751-131">15. 준비 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="26751-132">5. 응용 프로그램 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-132">5. Application Message</span></span>|<span data-ttu-id="26751-133">16. 준비 됨 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="26751-134">6. 컨텍스트가 있는 CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="26751-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="26751-135">17. 준비 됨 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="26751-136">7. Register (내구성)</span><span class="sxs-lookup"><span data-stu-id="26751-136">7. Register (Durable)</span></span>|<span data-ttu-id="26751-137">18. 커밋됨 (완료)</span><span class="sxs-lookup"><span data-stu-id="26751-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="26751-138">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="26751-138">8. RegisterResponse</span></span>|<span data-ttu-id="26751-139">19. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="26751-140">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="26751-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="26751-141">20. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="26751-142">10. Register (내구성)</span><span class="sxs-lookup"><span data-stu-id="26751-142">10. Register (Durable)</span></span>|<span data-ttu-id="26751-143">21. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="26751-144">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="26751-144">11. RegisterResponse</span></span>|<span data-ttu-id="26751-145">22. 커밋 (2PC)</span><span class="sxs-lookup"><span data-stu-id="26751-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="26751-146">이 문서에서는 WS-AtomicTransaction 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="26751-147">이 문서에서 설명하는 방식은 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26751-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="26751-148">그림과 표에서는 보안의 관점에서 메시지에 대한 4가지 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26751-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="26751-149">활성화 메시지(CreateCoordinationContext 및 CreateCoordinationContextResponse)</span><span class="sxs-lookup"><span data-stu-id="26751-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="26751-150">등록 메시지(Register 및 RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="26751-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="26751-151">프로토콜 메시지(준비, 롤백, 커밋, 중단 등)</span><span class="sxs-lookup"><span data-stu-id="26751-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="26751-152">애플리케이션 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-152">Application messages.</span></span>  
  
 <span data-ttu-id="26751-153">처음 세 개의 메시지 클래스는 트랜잭션 관리자 메시지로 간주되며, 해당 바인딩 구성은 이 항목의 뒷부분에 있는 &quot;애플리케이션 메시지 교환&quot;에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="26751-154">네 번째 메시지는 애플리케이션 간 메시지이며, 이 항목의 뒷부분에 있는 &quot;메시지 예제&quot; 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="26751-155">이 섹션에서는 WCF에서 이러한 각 클래스에 사용 되는 프로토콜 바인딩을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="26751-156">다음 XML 네임스페이스 및 관련 접두사는 이 문서 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="26751-157">접두사</span><span class="sxs-lookup"><span data-stu-id="26751-157">Prefix</span></span>|<span data-ttu-id="26751-158">Version</span><span class="sxs-lookup"><span data-stu-id="26751-158">Version</span></span>|<span data-ttu-id="26751-159">네임스페이스 URI</span><span class="sxs-lookup"><span data-stu-id="26751-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="26751-160">s11</span><span class="sxs-lookup"><span data-stu-id="26751-160">s11</span></span>||<https://schemas.xmlsoap.org/soap/envelope/>|  
|<span data-ttu-id="26751-161">wsa</span><span class="sxs-lookup"><span data-stu-id="26751-161">wsa</span></span>|<span data-ttu-id="26751-162">1.0 이전</span><span class="sxs-lookup"><span data-stu-id="26751-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="26751-163">1.0</span><span class="sxs-lookup"><span data-stu-id="26751-163">1.0</span></span>|`http://www.w3.org/2004/08/addressing`<br /><br /> <https://www.w3.org/2005/08/addressing/>|  
|<span data-ttu-id="26751-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="26751-164">wscoor</span></span>|<span data-ttu-id="26751-165">1.0</span><span class="sxs-lookup"><span data-stu-id="26751-165">1.0</span></span><br /><br /> <span data-ttu-id="26751-166">1.1</span><span class="sxs-lookup"><span data-stu-id="26751-166">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="26751-167">wsat</span><span class="sxs-lookup"><span data-stu-id="26751-167">wsat</span></span>|<span data-ttu-id="26751-168">1.0</span><span class="sxs-lookup"><span data-stu-id="26751-168">1.0</span></span><br /><br /> <span data-ttu-id="26751-169">1.1</span><span class="sxs-lookup"><span data-stu-id="26751-169">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
|<span data-ttu-id="26751-170">t</span><span class="sxs-lookup"><span data-stu-id="26751-170">t</span></span>|<span data-ttu-id="26751-171">Pre-1.3</span><span class="sxs-lookup"><span data-stu-id="26751-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="26751-172">1.3</span><span class="sxs-lookup"><span data-stu-id="26751-172">1.3</span></span>|<http://schemas.xmlsoap.org/ws/2005/02/trust/><br /><br /> <https://docs.oasis-open.org/ws-sx/ws-trust/200512>|  
|<span data-ttu-id="26751-173">o</span><span class="sxs-lookup"><span data-stu-id="26751-173">o</span></span>||<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd>|  
|<span data-ttu-id="26751-174">xsd</span><span class="sxs-lookup"><span data-stu-id="26751-174">xsd</span></span>||<https://www.w3.org/2001/XMLSchema>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="26751-175">트랜잭션 관리자 바인딩</span><span class="sxs-lookup"><span data-stu-id="26751-175">Transaction Manager Bindings</span></span>  

 <span data-ttu-id="26751-176">R1001: WS-AT 1.0 트랜잭션에 참여 하는 트랜잭션 관리자는 WS-Atomic 트랜잭션 및 WS-Coordination 메시지 교환을 위해 SOAP 1.1 및 WS-Addressing 2004/08를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="26751-177">R1002: WS-AT 1.1 트랜잭션에 참여 중인 트랜잭션 관리자는 WS-Atomic Transaction 및 WS-Coordination 메시지 교환을 위해 SOAP 1.1과 WS-Addressing 2005/08을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="26751-178">애플리케이션 메시지는 이러한 바인딩에 제한되지 않으며, 이에 대해서는 나중에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="26751-179">트랜잭션 관리자 HTTPS 바인딩</span><span class="sxs-lookup"><span data-stu-id="26751-179">Transaction Manager HTTPS Binding</span></span>  

 <span data-ttu-id="26751-180">트랜잭션 관리자 HTTPS 바인딩은 전송 보안에만 전적으로 의존하여 보안을 수행하며, 트랜잭션 트리에 있는 각 발신자-수신자 쌍 간의 신뢰를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="26751-181">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="26751-181">HTTPS Transport Configuration</span></span>  

 <span data-ttu-id="26751-182">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="26751-183">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="26751-184">R1111: 연결을 통해 표시되는 X.509 인증서에는 원래 컴퓨터의 FQDN(정규화된 도메인 이름)과 일치하는 주체 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="26751-185">B1112: DNS는 X.509 주체 이름을 확인한 시스템에서 각 발신자-수신자 쌍 간에 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="26751-186">바인딩 구성 활성화 및 등록</span><span class="sxs-lookup"><span data-stu-id="26751-186">Activation and Registration Binding Configuration</span></span>  

 <span data-ttu-id="26751-187">WCF에는 HTTPS를 통한 상관 관계가 있는 요청/응답 이중 바인딩이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="26751-188">요청/회신 메시지 교환 패턴의 상관 관계 및 설명에 대한 자세한 내용은 8단원 WS-Atomic Transaction을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26751-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="26751-189">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="26751-189">2PC Protocol Binding Configuration</span></span>  

 <span data-ttu-id="26751-190">WCF는 HTTPS를 통해 단방향 (데이터 그램) 메시지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="26751-191">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="26751-192">B1131: 구현은 `wsa:ReferenceParameters` WCF의 2pc 메시지의 상관 관계를 얻기 위해 WS-Addressing에 설명 된 대로를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="26751-193">트랜잭션 관리자가 혼합된 보안 바인딩</span><span class="sxs-lookup"><span data-stu-id="26751-193">Transaction Manager Mixed Security Binding</span></span>  

 <span data-ttu-id="26751-194">이는 ID 설정을 목적으로 WS-Coordination 발급 토큰 모델과 혼합된 전송 보안을 사용하는 대체(혼합 모드) 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="26751-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="26751-195">두 바인딩 간에 다른 요소는 활성화와 등록뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="26751-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="26751-196">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="26751-196">HTTPS Transport Configuration</span></span>  

 <span data-ttu-id="26751-197">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="26751-198">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="26751-199">활성화 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="26751-199">Activation Message Binding Configuration</span></span>  

 <span data-ttu-id="26751-200">활성화 메시지는 일반적으로 애플리케이션과 해당 로컬 트랜잭션 관리자 간에 발생하기 때문에 대개 상호 운용성에 관여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26751-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="26751-201">B1221: WCF는 활성화 메시지에 이중 HTTPS 바인딩 ( [메시징 프로토콜](messaging-protocols.md)에서 설명)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="26751-202">요청 및 회신 메시지는 WS-AT 1.0용 WS-Addressing 2004/08 및 WS-AT 1.1용 WS-Addressing 2005/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="26751-203">8단원 WS-Atomic Transaction 사양에서는 상관 관계 및 메시지 교환 패턴에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="26751-204">R1222: 코디네이터는 `CreateCoordinationContext`를 수신하는 즉시 연관된 비밀 `SecurityContextToken`로 `STx`을 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="26751-205">이 토큰은 WS-Trust 사양을 따르는 `t:IssuedTokens` 헤더의 내부로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="26751-206">R1223: 기존 코디네이션 컨텍스트 내에서 활성화가 수행되면 기존 컨텍스트와 연관된 `t:IssuedTokens`과 함께 `SecurityContextToken` 헤더가 `CreateCoordinationContext` 메시지에서 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="26751-207">`t:IssuedTokens`보내는 메시지에 연결 하기 위해 새 헤더를 생성 해야 합니다 `wscoor:CreateCoordinationContextResponse` .</span><span class="sxs-lookup"><span data-stu-id="26751-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="26751-208">등록 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="26751-208">Registration Message Binding Configuration</span></span>  

 <span data-ttu-id="26751-209">B1231: WCF는 이중 HTTPS 바인딩 ( [메시징 프로토콜](messaging-protocols.md)에 설명)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)).</span></span> <span data-ttu-id="26751-210">요청 및 회신 메시지는 WS-AT 1.0용 WS-Addressing 2004/08 및 WS-AT 1.1용 WS-Addressing 2005/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="26751-211">8단원 WS-AtomicTransaction에서는 메시지 교환 패턴의 상관 관계 및 설명에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="26751-212">R1232: 나가는 `wscoor:Register` 메시지는 `IssuedTokenOverTransport` [보안 프로토콜](security-protocols.md)에 설명 된 인증 모드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](security-protocols.md).</span></span>  
  
 <span data-ttu-id="26751-213">`wsse:Timestamp`요소가 발급 된를 사용 하 여 서명 되어야 합니다 `SecurityContextToken STx` .</span><span class="sxs-lookup"><span data-stu-id="26751-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="26751-214">이 서명은 특정 트랜잭션과 연관된 토큰을 소유했음을 나타내며, 트랜잭션에 등록된 참가자를 인증하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="26751-215">RegistrationResponse 메시지는 HTTPS를 통해 다시 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="26751-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="26751-216">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="26751-216">2PC Protocol Binding Configuration</span></span>  

 <span data-ttu-id="26751-217">WCF는 HTTPS를 통해 단방향 (데이터 그램) 메시지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="26751-218">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="26751-219">B1241: 구현은 `wsa:ReferenceParameters` WCF의 2pc 메시지의 상관 관계를 얻기 위해 WS-Addressing에 설명 된 대로를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="26751-220">애플리케이션 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="26751-220">Application Message Exchange</span></span>  

 <span data-ttu-id="26751-221">바인딩이 다음 보안 요구 사항을 만족하는 경우, 애플리케이션에서는 애플리케이션 간 메시지에 대해 특정 바인딩을 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26751-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="26751-222">R2001: 애플리케이션 간 메시지는 메시지의 헤더에서 `t:IssuedTokens`와 함께 `CoordinationContext` 헤더를 이동시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="26751-223">R2002: `t:IssuedToken`의 무결성 및 기밀성이 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26751-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="26751-224">`CoordinationContext` 헤더에는 `wscoor:Identifier`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="26751-225">의 정의는 `xsd:AnyURI` 절대 uri와 상대 uri를 모두 사용할 수 있지만 WCF는 절대 uri 인만 지원 합니다 `wscoor:Identifiers` .</span><span class="sxs-lookup"><span data-stu-id="26751-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="26751-226">B2003:의가 `wscoor:Identifier` `wscoor:CoordinationContext` 상대 URI 인 경우 트랜잭션 WCF 서비스에서 오류가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="26751-227">메시지 예제</span><span class="sxs-lookup"><span data-stu-id="26751-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="26751-228">CreateCoordinationContext 요청/응답 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-228">CreateCoordinationContext Request/Response Messages</span></span>  

 <span data-ttu-id="26751-229">다음 메시지는 요청/응답 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="26751-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="26751-230">WSCoor 1.0를 사용 하는 CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="26751-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="26751-231">CreateCoordinationContext와 WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="26751-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="26751-232">CreateCoordinationContextResponse와 Trust Pre-1.3 및 WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="26751-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="26751-233">CreateCoordinationContextResponse와 Trust 1.3 및 WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="26751-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>
<t:IssuedTokens>
<wst:RequestSecurityTokenResponse
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>
<wsc:SecurityContextToken>
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>
</wsc:SecurityContextToken>
</wst:RequestedSecurityToken>
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
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
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
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
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>
</wscoor:CoordinationContext>
</wscoor:CreateCoordinationContextResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="26751-234">등록 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-234">Registration Messages</span></span>  

 <span data-ttu-id="26751-235">다음 메시지는 등록 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="26751-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="26751-236">WSCoor 1.0에 등록</span><span class="sxs-lookup"><span data-stu-id="26751-236">Register with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="26751-237">WSCoor 1.1로 등록</span><span class="sxs-lookup"><span data-stu-id="26751-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>
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
<wssu:Identifier> http://fabrikam123.com/SCTi  
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
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>
</ds:Reference>
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
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
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="26751-238">WSCoor 1.0를 사용 하 여 응답 등록</span><span class="sxs-lookup"><span data-stu-id="26751-238">Register Response with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="26751-239">WSCoor 1.1로 응답 등록</span><span class="sxs-lookup"><span data-stu-id="26751-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
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
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>
</wscoor:RegisterResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="26751-240">2단계 커밋 프로토콜 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-240">Two Phase Commit Protocol Messages</span></span>  

 <span data-ttu-id="26751-241">다음 메시지는 2PC(2단계 커밋) 프로토콜과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="26751-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="26751-242">WSAT 1.0를 사용 하 여 커밋</span><span class="sxs-lookup"><span data-stu-id="26751-242">Commit with WSAT 1.0</span></span>  
  
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
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="26751-243">WSAT 1.1로 커밋</span><span class="sxs-lookup"><span data-stu-id="26751-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
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
  
### <a name="application-messages"></a><span data-ttu-id="26751-244">애플리케이션 메시지</span><span class="sxs-lookup"><span data-stu-id="26751-244">Application Messages</span></span>  

 <span data-ttu-id="26751-245">다음 메시지는 애플리케이션 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="26751-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="26751-246">애플리케이션 메시지-요청</span><span class="sxs-lookup"><span data-stu-id="26751-246">Application message-Request</span></span>  
  
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
