---
description: '자세한 정보: 서비스 감사 동작'
title: Service Auditing Behavior
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: 101f737d790d7e5ec0fdefc3a60695cb3c432c28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793131"
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="91764-103">Service Auditing Behavior</span><span class="sxs-lookup"><span data-stu-id="91764-103">Service Auditing Behavior</span></span>

<span data-ttu-id="91764-104">이 샘플에서는 서비스 작업 중에 서비스 이벤트 감사를 활성화하기 위해 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91764-104">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="91764-105">이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-105">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="91764-106">서비스와 클라이언트는를 사용 하 여 구성 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91764-106">The service and client have been configured using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="91764-107">`mode`의 특성이로 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 설정 되 `Message` 고 `clientCredentialType` 가로 설정 `Windows` 된 경우</span><span class="sxs-lookup"><span data-stu-id="91764-107">The `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="91764-108">이 샘플에서 클라이언트는 콘솔 애플리케이션(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="91764-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91764-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91764-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="91764-110">서비스 구성 파일은 `serviceSecurityAudit` 요소를 사용하여 감사를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-110">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="91764-111">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="91764-111">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="91764-112">클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="91764-112">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="91764-113">결과 감사 로그는 이벤트 뷰어를 실행하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91764-113">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="91764-114">기본적으로 Windows XP에서는 애플리케이션 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91764-114">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="91764-115">Windows Server 2008 및 Windows 7에서는 애플리케이션 및 서비스 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91764-115">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="91764-116">감사 이벤트의 위치는 `auditLogLocation` 특성을 "Application" 또는 "Security"로 설정 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91764-116">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="91764-117">자세한 내용은 [방법: 보안 이벤트 감사](../feature-details/how-to-audit-wcf-security-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91764-117">For more information, see [How to: Audit Security Events](../feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="91764-118">이벤트가 보안 로그에 기록 되는 경우 LocalSecurityPolicy > 사용 개체 액세스는 "성공" 및 "실패"에 대해 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-118">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="91764-119">이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다.</span><span class="sxs-lookup"><span data-stu-id="91764-119">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="91764-120">메시지 인증 감사 레코드의 범주는 "MessageAuthentication" 이지만 서비스 권한 부여 감사 레코드의 범주는 "ServiceAuthorization"입니다.</span><span class="sxs-lookup"><span data-stu-id="91764-120">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="91764-121">메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-121">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="91764-122">이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 엔드포인트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-122">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="91764-123">서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-123">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="91764-124">이 이벤트는 클라이언트 ID와 함께 권한 부여의 성공 여부, 메시지가 보내진 엔드포인트, 메시지와 연결된 동작, 들어오는 메시지에서 생성된 권한 부여 컨텍스트의 식별자 및 액세스 결정을 내린 권한 부여 관리자의 형식에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-124">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="91764-125">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="91764-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="91764-126">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="91764-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="91764-127">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="91764-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="91764-128">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="91764-128">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91764-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91764-129">See also</span></span>

- [<span data-ttu-id="91764-130">감사</span><span class="sxs-lookup"><span data-stu-id="91764-130">Auditing</span></span>](../feature-details/auditing-security-events.md)
- [<span data-ttu-id="91764-131">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="91764-131">How to: Audit Security Events</span></span>](../feature-details/how-to-audit-wcf-security-events.md)
