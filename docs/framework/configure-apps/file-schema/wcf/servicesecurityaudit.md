---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 10888f26053014ffb1fec49d1dfe87c7fd09ab54
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399572"
---
# \<serviceSecurityAudit>
<span data-ttu-id="8ede9-101">서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-101">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a><span data-ttu-id="8ede9-102">구문</span><span class="sxs-lookup"><span data-stu-id="8ede9-102">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ede9-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ede9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="8ede9-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ede9-105">특성</span><span class="sxs-lookup"><span data-stu-id="8ede9-105">Attributes</span></span>  
  
|<span data-ttu-id="8ede9-106">attribute</span><span class="sxs-lookup"><span data-stu-id="8ede9-106">Attribute</span></span>|<span data-ttu-id="8ede9-107">Description</span><span class="sxs-lookup"><span data-stu-id="8ede9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ede9-108">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="8ede9-108">auditLogLocation</span></span>|<span data-ttu-id="8ede9-109">감사 로그의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-109">Specifies the location of the audit log.</span></span> <span data-ttu-id="8ede9-110">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8ede9-111">-기본값: 보안 이벤트는 Windows XP의 응용 프로그램 로그와 windows Server 2003 및 Windows Vista의 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-111">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="8ede9-112">-Application: 감사 이벤트는 응용 프로그램 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-112">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="8ede9-113">-보안: 감사 이벤트가 보안 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-113">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="8ede9-114">기본값은 Default입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-114">The default value is Default.</span></span> <span data-ttu-id="8ede9-115">자세한 내용은 <xref:System.ServiceModel.AuditLogLocation>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ede9-115">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="8ede9-116">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="8ede9-116">suppressAuditFailure</span></span>|<span data-ttu-id="8ede9-117">감사 로그에 쓰기 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-117">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="8ede9-118">애플리케이션은 감사 로그 쓰기 실패에 대해 알림을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-118">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="8ede9-119">해당 애플리케이션에 감사 실패 처리 기능이 없는 경우 감사 로그에 쓰기 실패를 표시하지 않으려면 이 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-119">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="8ede9-120">이 특성이 `true`이면 감사 이벤트 쓰기 시도로 인해 발생한 OutOfMemoryException, StackOverFlowException, ThreadAbortException 및 ArgumentException 이외의 예외는 시스템에 의해 처리되며 애플리케이션으로 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-120">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="8ede9-121">이 특성이 `false`이면 감사 이벤트 쓰기 시도로 인해 발생한 모든 예외가 애플리케이션까지 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-121">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="8ede9-122">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-122">The default is `true`.</span></span>|  
|<span data-ttu-id="8ede9-123">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="8ede9-123">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="8ede9-124">감사 로그에 기록되는 인증 이벤트의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-124">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="8ede9-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8ede9-126">-None: 서비스 권한 부여 이벤트의 감사가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-126">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="8ede9-127">-성공: 성공한 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-127">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="8ede9-128">-실패: 실패 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-128">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="8ede9-129">-SuccessOrFailure: 성공 및 실패 서비스 권한 부여 이벤트를 모두 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-129">-   SuccessOrFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="8ede9-130">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-130">The default value is None.</span></span> <span data-ttu-id="8ede9-131">자세한 내용은 <xref:System.ServiceModel.AuditLevel>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ede9-131">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="8ede9-132">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="8ede9-132">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="8ede9-133">기록되는 메시지 인증 감사 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-133">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="8ede9-134">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-134">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8ede9-135">-None: 감사 이벤트가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-135">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="8ede9-136">-성공: 성공적인 보안만 (메시지 서명 유효성 검사, 암호 및 토큰 유효성 검사를 포함 한 전체 유효성 검사) 이벤트가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-136">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="8ede9-137">-실패: 실패 이벤트만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-137">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="8ede9-138">-SuccessOrFailure: 성공 및 실패 이벤트가 모두 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-138">-   SuccessOrFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="8ede9-139">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-139">The default value is None.</span></span> <span data-ttu-id="8ede9-140">자세한 내용은 <xref:System.ServiceModel.AuditLevel>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ede9-140">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ede9-141">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ede9-141">Child Elements</span></span>  
 <span data-ttu-id="8ede9-142">없음</span><span class="sxs-lookup"><span data-stu-id="8ede9-142">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ede9-143">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ede9-143">Parent Elements</span></span>  
  
|<span data-ttu-id="8ede9-144">요소</span><span class="sxs-lookup"><span data-stu-id="8ede9-144">Element</span></span>|<span data-ttu-id="8ede9-145">Description</span><span class="sxs-lookup"><span data-stu-id="8ede9-145">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8ede9-146">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-146">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ede9-147">설명</span><span class="sxs-lookup"><span data-stu-id="8ede9-147">Remarks</span></span>  
 <span data-ttu-id="8ede9-148">이 구성 요소는 WCF (Windows Communication Foundation) 인증 이벤트를 감사 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-148">This configuration element is used to audit Windows Communication Foundation (WCF) authentication events.</span></span> <span data-ttu-id="8ede9-149">감사 기능을 사용하도록 설정하면 성공한 인증 시도나 실패한 인증 시도 또는 둘 모두를 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-149">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="8ede9-150">이벤트는 운영 체제 버전의 애플리케이션 로그, 보안 로그 또는 기본 로그의 세 가지 이벤트 로그 중 하나에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-150">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="8ede9-151">이벤트 로그는 Windows 이벤트 뷰어를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-151">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="8ede9-152">이 구성 요소 사용에 대 한 자세한 예제는 [서비스 감사 동작](../../../wcf/samples/service-auditing-behavior.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ede9-152">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="8ede9-153">기본적으로 Windows XP에서는 애플리케이션 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-153">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="8ede9-154">감사 이벤트의 위치는 `auditLogLocation` 특성을 'Application' 또는 'Security'로 설정하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-154">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="8ede9-155">자세한 내용은 [방법: 보안 이벤트 감사](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ede9-155">For more information, see [How to: Audit Security Events](../../../wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="8ede9-156">이벤트가 보안 로그에 기록 되는 경우 "성공" 및 "실패"에 대해 LocalSecurityPolicy > 사용 개체 액세스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-156">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="8ede9-157">이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-157">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="8ede9-158">메시지 인증 감사 레코드의 범주는 "MessageAuthentication"이지만 서비스 권한 부여 감사 레코드의 범주는 'ServiceAuthorization'입니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-158">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="8ede9-159">메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-159">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="8ede9-160">이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 엔드포인트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-160">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="8ede9-161">서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-161">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="8ede9-162">이는 클라이언트 id, 메시지를 보낸 끝점, 메시지와 연결 된 동작, 들어오는 메시지에서 생성 된 권한 부여 컨텍스트의 식별자 및 액세스 결정을 내린 권한 부여 관리자의 형식에 따라 권한 부여 성공 또는 실패 여부에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ede9-162">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ede9-163">예제</span><span class="sxs-lookup"><span data-stu-id="8ede9-163">Example</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="8ede9-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ede9-164">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [<span data-ttu-id="8ede9-165">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8ede9-165">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8ede9-166">감사</span><span class="sxs-lookup"><span data-stu-id="8ede9-166">Auditing</span></span>](../../../wcf/feature-details/auditing-security-events.md)
- [<span data-ttu-id="8ede9-167">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="8ede9-167">How to: Audit Security Events</span></span>](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [<span data-ttu-id="8ede9-168">Service Auditing Behavior</span><span class="sxs-lookup"><span data-stu-id="8ede9-168">Service Auditing Behavior</span></span>](../../../wcf/samples/service-auditing-behavior.md)
