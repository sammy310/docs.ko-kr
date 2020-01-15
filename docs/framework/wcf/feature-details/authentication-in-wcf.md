---
title: WCF에서 권한 부여
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: abe7aff025207ad8bdf8657daba3584e6a1b2e7f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964693"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="e1e43-102">WCF에서 권한 부여</span><span class="sxs-lookup"><span data-stu-id="e1e43-102">Authentication in WCF</span></span>
<span data-ttu-id="e1e43-103">다음 항목에서는 Windows 인증, x.509 인증서, 사용자 이름 및 암호 등의 인증을 제공 하는 Windows Communication Foundation (WCF)의 다양 한 메커니즘을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1e43-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e1e43-104">In This Section</span></span>  
 [<span data-ttu-id="e1e43-105">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="e1e43-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="e1e43-106">ASP.NET 기능에는 멤버 자격 및 역할 공급자, 인증에 필요한 사용자 이름/암호 쌍을 저장할 데이터베이스 및 권한 부여를 위한 사용자 역할이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="e1e43-107">이 항목에서는 WCF 서비스가 동일한 데이터베이스를 사용 하 여 사용자를 인증 하 고 권한을 부여 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="e1e43-108">방법: 사용자 지정 사용자 이름 및 암호 유효성 검사기 사용</span><span class="sxs-lookup"><span data-stu-id="e1e43-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="e1e43-109">사용자 지정 사용자 이름/암호 유효성 검사기를 통합하는 방법에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="e1e43-110">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="e1e43-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="e1e43-111">추가 보호 수단으로 클라이언트는 서비스의 예상 *id* 를 지정 하 여 서비스를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="e1e43-112">예상 ID 및 서비스에서 반환한 ID가 서로 일치하지 않으면 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="e1e43-113">보안 협상 및 시간 제한</span><span class="sxs-lookup"><span data-stu-id="e1e43-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="e1e43-114"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 클래스의 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> 속성을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="e1e43-115">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="e1e43-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="e1e43-116">Windows 인증을 사용할 때 일반적으로 발생하는 문제에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1e43-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e1e43-117">참조</span><span class="sxs-lookup"><span data-stu-id="e1e43-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="e1e43-118">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="e1e43-118">Related Sections</span></span>  
 [<span data-ttu-id="e1e43-119">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="e1e43-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1e43-120">참조</span><span class="sxs-lookup"><span data-stu-id="e1e43-120">See also</span></span>

- [<span data-ttu-id="e1e43-121">보안 개요</span><span class="sxs-lookup"><span data-stu-id="e1e43-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="e1e43-122">[Windows Server Fabric 용 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e1e43-122">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
