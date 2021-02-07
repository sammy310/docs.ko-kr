---
description: 다음에 대해 자세히 알아보세요. <serviceSecurityAudit>
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 262341f44adb7657086edb8d33514c07195ddfa3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682750"
---
# \<serviceSecurityAudit>

<span data-ttu-id="cdb4d-102">서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-102">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a><span data-ttu-id="cdb4d-103">구문</span><span class="sxs-lookup"><span data-stu-id="cdb4d-103">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdb4d-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cdb4d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="cdb4d-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdb4d-106">특성</span><span class="sxs-lookup"><span data-stu-id="cdb4d-106">Attributes</span></span>  
  
|<span data-ttu-id="cdb4d-107">attribute</span><span class="sxs-lookup"><span data-stu-id="cdb4d-107">Attribute</span></span>|<span data-ttu-id="cdb4d-108">설명</span><span class="sxs-lookup"><span data-stu-id="cdb4d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cdb4d-109">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="cdb4d-109">auditLogLocation</span></span>|<span data-ttu-id="cdb4d-110">감사 로그의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-110">Specifies the location of the audit log.</span></span> <span data-ttu-id="cdb4d-111">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-111">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cdb4d-112">-기본값: 보안 이벤트는 Windows XP의 응용 프로그램 로그와 windows Server 2003 및 Windows Vista의 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-112">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="cdb4d-113">-Application: 감사 이벤트는 응용 프로그램 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-113">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="cdb4d-114">-보안: 감사 이벤트가 보안 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-114">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="cdb4d-115">기본값은 Default입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-115">The default value is Default.</span></span> <span data-ttu-id="cdb4d-116">자세한 내용은 <xref:System.ServiceModel.AuditLogLocation>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-116">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="cdb4d-117">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="cdb4d-117">suppressAuditFailure</span></span>|<span data-ttu-id="cdb4d-118">감사 로그에 쓰기 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-118">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="cdb4d-119">애플리케이션은 감사 로그 쓰기 실패에 대해 알림을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-119">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="cdb4d-120">해당 애플리케이션에 감사 실패 처리 기능이 없는 경우 감사 로그에 쓰기 실패를 표시하지 않으려면 이 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-120">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="cdb4d-121">이 특성이 `true`이면 감사 이벤트 쓰기 시도로 인해 발생한 OutOfMemoryException, StackOverFlowException, ThreadAbortException 및 ArgumentException 이외의 예외는 시스템에 의해 처리되며 애플리케이션으로 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-121">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="cdb4d-122">이 특성이 `false`이면 감사 이벤트 쓰기 시도로 인해 발생한 모든 예외가 애플리케이션까지 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-122">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="cdb4d-123">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-123">The default is `true`.</span></span>|  
|<span data-ttu-id="cdb4d-124">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="cdb4d-124">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="cdb4d-125">감사 로그에 기록되는 인증 이벤트의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-125">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="cdb4d-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cdb4d-127">-None: 서비스 권한 부여 이벤트의 감사가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-127">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="cdb4d-128">-성공: 성공한 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-128">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="cdb4d-129">-실패: 실패 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-129">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="cdb4d-130">-SuccessOrFailure: 성공 및 실패 서비스 권한 부여 이벤트를 모두 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-130">-   SuccessOrFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="cdb4d-131">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-131">The default value is None.</span></span> <span data-ttu-id="cdb4d-132">자세한 내용은 <xref:System.ServiceModel.AuditLevel>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-132">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="cdb4d-133">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="cdb4d-133">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="cdb4d-134">기록되는 메시지 인증 감사 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-134">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="cdb4d-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cdb4d-136">-None: 감사 이벤트가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-136">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="cdb4d-137">-성공: 성공적인 보안만 (메시지 서명 유효성 검사, 암호 및 토큰 유효성 검사를 포함 한 전체 유효성 검사) 이벤트가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-137">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="cdb4d-138">-실패: 실패 이벤트만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-138">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="cdb4d-139">-SuccessOrFailure: 성공 및 실패 이벤트가 모두 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-139">-   SuccessOrFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="cdb4d-140">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-140">The default value is None.</span></span> <span data-ttu-id="cdb4d-141">자세한 내용은 <xref:System.ServiceModel.AuditLevel>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-141">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdb4d-142">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cdb4d-142">Child Elements</span></span>  

 <span data-ttu-id="cdb4d-143">없음</span><span class="sxs-lookup"><span data-stu-id="cdb4d-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdb4d-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cdb4d-144">Parent Elements</span></span>  
  
|<span data-ttu-id="cdb4d-145">요소</span><span class="sxs-lookup"><span data-stu-id="cdb4d-145">Element</span></span>|<span data-ttu-id="cdb4d-146">설명</span><span class="sxs-lookup"><span data-stu-id="cdb4d-146">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cdb4d-147">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdb4d-148">설명</span><span class="sxs-lookup"><span data-stu-id="cdb4d-148">Remarks</span></span>  

 <span data-ttu-id="cdb4d-149">이 구성 요소는 WCF (Windows Communication Foundation) 인증 이벤트를 감사 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-149">This configuration element is used to audit Windows Communication Foundation (WCF) authentication events.</span></span> <span data-ttu-id="cdb4d-150">감사 기능을 사용하도록 설정하면 성공한 인증 시도나 실패한 인증 시도 또는 둘 모두를 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-150">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="cdb4d-151">이벤트는 운영 체제 버전의 애플리케이션 로그, 보안 로그 또는 기본 로그의 세 가지 이벤트 로그 중 하나에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-151">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="cdb4d-152">이벤트 로그는 Windows 이벤트 뷰어를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-152">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="cdb4d-153">이 구성 요소 사용에 대 한 자세한 예제는 [서비스 감사 동작](../../../wcf/samples/service-auditing-behavior.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-153">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="cdb4d-154">기본적으로 Windows XP에서는 애플리케이션 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-154">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="cdb4d-155">감사 이벤트의 위치는 `auditLogLocation` 특성을 'Application' 또는 'Security'로 설정하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-155">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="cdb4d-156">자세한 내용은 [방법: 보안 이벤트 감사](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-156">For more information, see [How to: Audit Security Events](../../../wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="cdb4d-157">이벤트가 보안 로그에 기록 되는 경우 "성공" 및 "실패"에 대해 LocalSecurityPolicy > 사용 개체 액세스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-157">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="cdb4d-158">이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-158">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="cdb4d-159">메시지 인증 감사 레코드의 범주는 "MessageAuthentication"이지만 서비스 권한 부여 감사 레코드의 범주는 'ServiceAuthorization'입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-159">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="cdb4d-160">메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-160">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="cdb4d-161">이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 엔드포인트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-161">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="cdb4d-162">서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-162">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="cdb4d-163">이는 클라이언트 id, 메시지를 보낸 끝점, 메시지와 연결 된 동작, 들어오는 메시지에서 생성 된 권한 부여 컨텍스트의 식별자 및 액세스 결정을 내린 권한 부여 관리자의 형식에 따라 권한 부여 성공 또는 실패 여부에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb4d-163">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb4d-164">예제</span><span class="sxs-lookup"><span data-stu-id="cdb4d-164">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cdb4d-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdb4d-165">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [<span data-ttu-id="cdb4d-166">보안 동작</span><span class="sxs-lookup"><span data-stu-id="cdb4d-166">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="cdb4d-167">감사</span><span class="sxs-lookup"><span data-stu-id="cdb4d-167">Auditing</span></span>](../../../wcf/feature-details/auditing-security-events.md)
- [<span data-ttu-id="cdb4d-168">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="cdb4d-168">How to: Audit Security Events</span></span>](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [<span data-ttu-id="cdb4d-169">Service Auditing Behavior</span><span class="sxs-lookup"><span data-stu-id="cdb4d-169">Service Auditing Behavior</span></span>](../../../wcf/samples/service-auditing-behavior.md)
