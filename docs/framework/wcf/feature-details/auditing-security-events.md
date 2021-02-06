---
description: '자세히 알아보기: 보안 이벤트 감사'
title: 보안 이벤트 감사
ms.date: 03/30/2017
helpviewer_keywords:
- auditing security events [WCF]
ms.assetid: 5633f61c-a3c9-40dd-8070-1c373b66a716
ms.openlocfilehash: 84eebeec5ebeec047d840e9902d52b4ae409599f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643724"
---
# <a name="auditing-security-events"></a><span data-ttu-id="04835-103">보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="04835-103">Auditing Security Events</span></span>

<span data-ttu-id="04835-104">WCF (Windows Communication Foundation)를 사용 하 여 만든 응용 프로그램은 감사 기능을 사용 하 여 보안 이벤트 (성공, 실패 또는 둘 다)를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-104">Applications created with Windows Communication Foundation (WCF) can log security events (either success, failure, or both) with the auditing feature.</span></span> <span data-ttu-id="04835-105">이벤트는 Windows의 시스템 이벤트 로그에 기록되며 이벤트 뷰어를 사용하여 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-105">The events are written to the Windows system event log and can be examined using the Event Viewer.</span></span>  
  
 <span data-ttu-id="04835-106">관리자는 감사를 사용하여 이미 발생했거나 진행 중인 공격을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-106">Auditing provides a way for an administrator to detect an attack that has already occurred or is in progress.</span></span> <span data-ttu-id="04835-107">또한 감사는 개발자가 보안 관련 문제를 디버깅하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-107">In addition, auditing can help a developer to debug security-related problems.</span></span> <span data-ttu-id="04835-108">예를 들어, 정책 검사 또는 권한 부여 구성 오류로 인해 실수로 권한 있는 사용자의 액세스가 거부될 경우 개발자는 이벤트 로그를 검사하여 오류의 원인을 신속하게 찾아서 격리시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-108">For example, if an error in the configuration of the authorization or checking policy accidentally denies access to an authorized user, a developer can quickly discover and isolate the cause of this error by examining the event log.</span></span>  
  
 <span data-ttu-id="04835-109">WCF 보안에 대 한 자세한 내용은 [보안 개요](security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04835-109">For more information about WCF security, see [Security Overview](security-overview.md).</span></span> <span data-ttu-id="04835-110">WCF 프로그래밍에 대 한 자세한 내용은 [기본 Wcf 프로그래밍](../basic-wcf-programming.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04835-110">For more information about programming WCF, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="audit-level-and-behavior"></a><span data-ttu-id="04835-111">감사 수준 및 동작</span><span class="sxs-lookup"><span data-stu-id="04835-111">Audit Level and Behavior</span></span>  

 <span data-ttu-id="04835-112">보안 감사에는 다음과 같은 두 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-112">Two levels of security audits exist:</span></span>  
  
- <span data-ttu-id="04835-113">서비스 인증 수준 - 호출자에게 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-113">Service authorization level, in which a caller is authorized.</span></span>  
  
- <span data-ttu-id="04835-114">메시지 수준-WCF에서 메시지의 유효성을 검사 하 고 호출자를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-114">Message level, in which WCF checks for message validity and authenticates the caller.</span></span>  
  
 <span data-ttu-id="04835-115">성공 또는 실패에 대 한 두 감사 수준을 모두 확인할 수 있습니다 .이를 *감사 동작* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-115">You can check both audit levels for success or failure, which is known as the *audit behavior*.</span></span>  
  
## <a name="audit-log-location"></a><span data-ttu-id="04835-116">감사 로그 위치</span><span class="sxs-lookup"><span data-stu-id="04835-116">Audit Log Location</span></span>  

 <span data-ttu-id="04835-117">감사 수준과 동작을 결정한 후 사용자 또는 관리자가 감사 로그의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-117">Once you determine an audit level and behavior, you (or an administrator) can specify a location for the audit log.</span></span> <span data-ttu-id="04835-118">기본값, 애플리케이션, 보안의 세 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-118">The three choices include: Default, Application, and Security.</span></span> <span data-ttu-id="04835-119">기본값을 지정한 경우 실제 로그는 사용 중인 시스템과 시스템에서 보안 로그 기록을 지원하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="04835-119">When you specify Default, the actual log depends on which system you are using and whether the system supports writing to the security log.</span></span> <span data-ttu-id="04835-120">자세한 내용은이 항목의 뒷부분에 나오는 "운영 체제" 단원을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04835-120">For more information, see the "Operating System" section later in this topic.</span></span>  
  
 <span data-ttu-id="04835-121">보안 로그에 기록하려면 `SeAuditPrivilege`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-121">To write to the Security log requires the `SeAuditPrivilege`.</span></span> <span data-ttu-id="04835-122">기본적으로 로컬 시스템 및 네트워크 서비스 계정에만 이 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-122">By default, only Local System and Network Service accounts have this privilege.</span></span> <span data-ttu-id="04835-123">보안 로그 기능 `read` 및 `delete`를 관리하려면 `SeSecurityPrivilege`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-123">To manage the Security log functions `read` and `delete` requires the `SeSecurityPrivilege`.</span></span> <span data-ttu-id="04835-124">기본적으로 관리자만 이 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="04835-124">By default, only administrators have this privilege.</span></span>  
  
 <span data-ttu-id="04835-125">반대로, 인증된 사용자는 애플리케이션 로그를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-125">In contrast, authenticated users can read and write to the Application log.</span></span> <span data-ttu-id="04835-126">Windows XP에서는 기본적으로 응용 프로그램 로그에 감사 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-126">Windows XP writes audit events to the Application log by default.</span></span> <span data-ttu-id="04835-127">이 로그는 모든 인증된 사용자에게 표시되는 개인 정보를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-127">The log can also contain personal information that is visible to all authenticated users.</span></span>  
  
## <a name="suppressing-audit-failures"></a><span data-ttu-id="04835-128">감사 실패 억제</span><span class="sxs-lookup"><span data-stu-id="04835-128">Suppressing Audit Failures</span></span>  

 <span data-ttu-id="04835-129">또한 감사 중에 감사 실패를 억제할지 여부를 지정하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-129">Another option during auditing is whether to suppress any audit failure.</span></span> <span data-ttu-id="04835-130">기본적으로 감사 실패는 애플리케이션에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-130">By default, an audit failure does not affect an application.</span></span> <span data-ttu-id="04835-131">그러나 필요한 경우 이 옵션을 `false`로 설정할 수 있습니다. 그러면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-131">If required, however, you can set the option to `false`, which causes an exception to be thrown.</span></span>  
  
## <a name="programming-auditing"></a><span data-ttu-id="04835-132">감사 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="04835-132">Programming Auditing</span></span>  

 <span data-ttu-id="04835-133">프로그래밍 방식이나 구성을 통해 감사 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-133">You can specify auditing behavior either programmatically or through configuration.</span></span>  
  
### <a name="auditing-classes"></a><span data-ttu-id="04835-134">감사 클래스</span><span class="sxs-lookup"><span data-stu-id="04835-134">Auditing Classes</span></span>  

 <span data-ttu-id="04835-135">다음 표에서는 감사 동작을 프로그래밍하는 데 사용되는 클래스와 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-135">The following table describes the classes and properties used to program auditing behavior.</span></span>  
  
|<span data-ttu-id="04835-136">인스턴스</span><span class="sxs-lookup"><span data-stu-id="04835-136">Class</span></span>|<span data-ttu-id="04835-137">설명</span><span class="sxs-lookup"><span data-stu-id="04835-137">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>|<span data-ttu-id="04835-138">감사 옵션을 서비스 동작으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-138">Enables setting options for auditing as a service behavior.</span></span>|  
|<xref:System.ServiceModel.AuditLogLocation>|<span data-ttu-id="04835-139">기록할 로그를 지정하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="04835-139">Enumeration to specify which log to write to.</span></span> <span data-ttu-id="04835-140">가능한 값은 기본값, 애플리케이션 및 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="04835-140">The possible values are Default, Application, and Security.</span></span> <span data-ttu-id="04835-141">기본값을 선택하면 운영 체제에서 실제 로그 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-141">When you select Default, the operating system determines the actual log location.</span></span> <span data-ttu-id="04835-142">이 항목의 뒷부분에 나오는 &quot;애플리케이션 또는 보안 이벤트 로그 선택&quot; 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="04835-142">See the "Application or Security Event Log Choice" section later in this topic.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>|<span data-ttu-id="04835-143">메시지 수준에서 감사할 메시지 인증 이벤트의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-143">Specifies which types of message authentication events are audited at the message level.</span></span> <span data-ttu-id="04835-144">`None`, `Failure`, `Success` 및 `SuccessOrFailure` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-144">The choices are `None`, `Failure`, `Success`, and `SuccessOrFailure`.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>|<span data-ttu-id="04835-145">서비스 수준에서 감사할 서비스 인증 이벤트의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-145">Specifies which types of service authorization events are audited at the service level.</span></span> <span data-ttu-id="04835-146">`None`, `Failure`, `Success` 및 `SuccessOrFailure` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-146">The choices are `None`, `Failure`, `Success`, and `SuccessOrFailure`.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>|<span data-ttu-id="04835-147">감사가 실패할 경우 클라이언트 요청 처리 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-147">Specifies what happens to the client request when auditing fails.</span></span> <span data-ttu-id="04835-148">예를 들어, 서비스에서 보안 로그에 기록하려고 시도하지만 `SeAuditPrivilege`가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="04835-148">For example, when the service attempts to write to the security log, but does not have `SeAuditPrivilege`.</span></span> <span data-ttu-id="04835-149">기본값 `true`를 지정했다면 실패가 무시되고 클라이언트 요청이 정상적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-149">The default value of `true` indicates that failures are ignored, and the client request is processed normally.</span></span>|  
  
 <span data-ttu-id="04835-150">감사 이벤트를 기록 하도록 응용 프로그램을 설정 하는 예제는 [방법: 보안 이벤트 감사](how-to-audit-wcf-security-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04835-150">For an example of setting up an application to log audit events, see [How to: Audit Security Events](how-to-audit-wcf-security-events.md).</span></span>  
  
### <a name="configuration"></a><span data-ttu-id="04835-151">Configuration</span><span class="sxs-lookup"><span data-stu-id="04835-151">Configuration</span></span>  

 <span data-ttu-id="04835-152">구성을 사용 하 여 아래에를 추가 하 여 감사 동작을 지정할 수도 있습니다 [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="04835-152">You can also use configuration to specify auditing behavior by adding a [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) under the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md).</span></span> <span data-ttu-id="04835-153">다음 코드와 같이 아래에 요소를 추가 해야 합니다 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="04835-153">You must add the element under a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) as shown in the following code.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <behavior>  
        <!-- auditLogLocation="Application" or "Security" -->  
        <serviceSecurityAudit  
                  auditLogLocation="Application"  
                  suppressAuditFailure="true"  
                  serviceAuthorizationAuditLevel="Failure"  
                  messageAuthenticationAuditLevel="SuccessOrFailure" />
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="04835-154">감사가 설정되어 있지만 `auditLogLocation`이 지정되어 있지 않으면 보안 로그 기록을 지원하는 플랫폼의 기본 로그 이름은 "Security" 로그이고, 그렇지 않으면 "Application" 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="04835-154">If auditing is enabled and an `auditLogLocation` is not specified, the default log name is "Security" log for the platform supporting writing to the Security log; otherwise, it is "Application" log.</span></span> <span data-ttu-id="04835-155">Windows Server 2003 및 Windows Vista 운영 체제만 보안 로그에 쓰기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-155">Only the Windows Server 2003 and Windows Vista operating systems support writing to the Security log.</span></span> <span data-ttu-id="04835-156">자세한 내용은이 항목의 뒷부분에 나오는 "운영 체제" 단원을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04835-156">For more information, see the "Operating System" section later in this topic.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="04835-157">보안 고려사항</span><span class="sxs-lookup"><span data-stu-id="04835-157">Security Considerations</span></span>  

 <span data-ttu-id="04835-158">악의적인 사용자가 감사가 설정된 사실을 알고 있다면 잘못된 메시지를 보내 감사 항목을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-158">If a malicious user knows that auditing is enabled, that attacker can send invalid messages that cause audit entries to be written.</span></span> <span data-ttu-id="04835-159">이런 식으로 감사 로그가 채워지면 감사 시스템이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-159">If the audit log is filled in this manner, the auditing system fails.</span></span> <span data-ttu-id="04835-160">이 문제를 완화하려면 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true`로 설정하고 이벤트 뷰어의 속성을 사용하여 감사 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-160">To mitigate this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true` and use the properties of the Event Viewer to control the auditing behavior.</span></span>  
  
 <span data-ttu-id="04835-161">Windows XP의 응용 프로그램 로그에 기록 된 감사 이벤트는 모든 인증 된 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-161">Audit events that are written to the Application Log on Windows XP are visible to any authenticated user.</span></span>  
  
## <a name="choosing-between-application-and-security-event-logs"></a><span data-ttu-id="04835-162">애플리케이션 및 보안 이벤트 로그 선택</span><span class="sxs-lookup"><span data-stu-id="04835-162">Choosing Between Application and Security Event Logs</span></span>  

 <span data-ttu-id="04835-163">다음 표에서는 애플리케이션 이벤트 로그에 기록할지 보안 이벤트 로그에 기록할지 여부를 선택하는 데 도움이 되는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-163">The following tables provide information to help you choose whether to log into the Application or the Security event log.</span></span>  
  
#### <a name="operating-system"></a><span data-ttu-id="04835-164">운영 체제</span><span class="sxs-lookup"><span data-stu-id="04835-164">Operating System</span></span>  
  
|<span data-ttu-id="04835-165">시스템</span><span class="sxs-lookup"><span data-stu-id="04835-165">System</span></span>|<span data-ttu-id="04835-166">애플리케이션 로그</span><span class="sxs-lookup"><span data-stu-id="04835-166">Application log</span></span>|<span data-ttu-id="04835-167">보안 로그</span><span class="sxs-lookup"><span data-stu-id="04835-167">Security log</span></span>|  
|------------|---------------------|------------------|  
|<span data-ttu-id="04835-168">Windows XP SP2 이상</span><span class="sxs-lookup"><span data-stu-id="04835-168">Windows XP SP2 or later</span></span>|<span data-ttu-id="04835-169">지원됨</span><span class="sxs-lookup"><span data-stu-id="04835-169">Supported</span></span>|<span data-ttu-id="04835-170">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="04835-170">Not supported</span></span>|  
|<span data-ttu-id="04835-171">Windows Server 2003 SP1 및 Windows Vista</span><span class="sxs-lookup"><span data-stu-id="04835-171">Windows Server 2003 SP1 and Windows Vista</span></span>|<span data-ttu-id="04835-172">지원됨</span><span class="sxs-lookup"><span data-stu-id="04835-172">Supported</span></span>|<span data-ttu-id="04835-173">스레드 컨텍스트에 `SeAuditPrivilege`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-173">Thread context must possess `SeAuditPrivilege`</span></span>|  
  
#### <a name="other-factors"></a><span data-ttu-id="04835-174">기타 요소</span><span class="sxs-lookup"><span data-stu-id="04835-174">Other Factors</span></span>  

 <span data-ttu-id="04835-175">다음 표에서는 운영 체제 이외에 로깅 사용을 제어하는 기타 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-175">In addition to the operating system, the following table describes other settings that control the enablement of logging.</span></span>  
  
|<span data-ttu-id="04835-176">요인</span><span class="sxs-lookup"><span data-stu-id="04835-176">Factor</span></span>|<span data-ttu-id="04835-177">애플리케이션 로그</span><span class="sxs-lookup"><span data-stu-id="04835-177">Application log</span></span>|<span data-ttu-id="04835-178">보안 로그</span><span class="sxs-lookup"><span data-stu-id="04835-178">Security log</span></span>|  
|------------|---------------------|------------------|  
|<span data-ttu-id="04835-179">정책 관리 감사</span><span class="sxs-lookup"><span data-stu-id="04835-179">Audit policy management</span></span>|<span data-ttu-id="04835-180">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="04835-180">Not applicable.</span></span>|<span data-ttu-id="04835-181">구성과 함께 보안 로그는 LSA(로컬 보안 기관) 정책에 의해서도 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="04835-181">Along with configuration, the Security log is also controlled by the local security authority (LSA) policy.</span></span> <span data-ttu-id="04835-182">"개체 액세스 감사" 범주 또한 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-182">The "Audit object access" category must also be enabled.</span></span>|  
|<span data-ttu-id="04835-183">기본 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="04835-183">Default user experience</span></span>|<span data-ttu-id="04835-184">모든 인증된 사용자는 애플리케이션 로그에 기록할 수 있으므로 애플리케이션 프로세스를 위한 추가 권한 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04835-184">All authenticated users can write to the Application log, so no additional permission step is needed for application processes.</span></span>|<span data-ttu-id="04835-185">애플리케이션 프로세스(컨텍스트)에 `SeAuditPrivilege`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04835-185">The application process (context) must have `SeAuditPrivilege`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04835-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04835-186">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="04835-187">보안 개요</span><span class="sxs-lookup"><span data-stu-id="04835-187">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="04835-188">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="04835-188">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- [<span data-ttu-id="04835-189">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="04835-189">How to: Audit Security Events</span></span>](how-to-audit-wcf-security-events.md)
- [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md)
- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)
- <span data-ttu-id="04835-190">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="04835-190">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
