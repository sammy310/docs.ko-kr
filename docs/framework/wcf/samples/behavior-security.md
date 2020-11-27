---
title: 동작 보안
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
ms.openlocfilehash: c06c615af773affe9b824c6a862afcbadfb16295
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258740"
---
# <a name="behavior-security"></a><span data-ttu-id="73136-102">동작 보안</span><span class="sxs-lookup"><span data-stu-id="73136-102">Behavior Security</span></span>

<span data-ttu-id="73136-103">이 단원에는 서비스 동작에 대한 보안을 구성하는 방법을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73136-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73136-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="73136-104">In This Section</span></span>  

 [<span data-ttu-id="73136-105">Service Auditing Behavior</span><span class="sxs-lookup"><span data-stu-id="73136-105">Service Auditing Behavior</span></span>](service-auditing-behavior.md)  
 <span data-ttu-id="73136-106">이 샘플에서는 서비스 작업 중에 서비스 이벤트 감사를 활성화하기 위해 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73136-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="73136-107">Membership and Role Provider</span><span class="sxs-lookup"><span data-stu-id="73136-107">Membership and Role Provider</span></span>](membership-and-role-provider.md)  
 <span data-ttu-id="73136-108">이 샘플에서는 서비스에서 ASP.NET 멤버 자격 및 역할 공급자를 사용 하 여 클라이언트를 인증 하 고 권한을 부여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73136-108">This sample demonstrates how a service can use the ASP.NET membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="73136-109">Authorizing Access to Service Operations</span><span class="sxs-lookup"><span data-stu-id="73136-109">Authorizing Access to Service Operations</span></span>](authorizing-access-to-service-operations.md)  
 <span data-ttu-id="73136-110">이 샘플에서는를 사용 하 여 [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) 특성을 사용 하 여 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 서비스 작업에 대 한 액세스 권한을 부여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73136-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="73136-111">Impersonating the Client</span><span class="sxs-lookup"><span data-stu-id="73136-111">Impersonating the Client</span></span>](impersonating-the-client.md)  
 <span data-ttu-id="73136-112">이 샘플에서는 서비스가 호출자를 대신하여 시스템 리소스에 액세스할 수 있도록 서비스에서 호출자 애플리케이션을 가장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73136-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
