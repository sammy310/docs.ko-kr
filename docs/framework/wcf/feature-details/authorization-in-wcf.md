---
title: WCF에서 권한 부여
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: d67d64dcf0003de28775ac947f8b5f72d7c2ba2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597633"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="83d2d-102">WCF에서 권한 부여</span><span class="sxs-lookup"><span data-stu-id="83d2d-102">Authorization in WCF</span></span>
<span data-ttu-id="83d2d-103">권한 부여는 서비스나 파일과 같은 리소스에 대한 액세스 및 권한을 제어하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="83d2d-104">이 단원의 항목에서는 Windows Communication Foundation (WCF)에서 다양 한 방법으로이 기본 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83d2d-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="83d2d-105">In This Section</span></span>  
 [<span data-ttu-id="83d2d-106">Access Control 메커니즘</span><span class="sxs-lookup"><span data-stu-id="83d2d-106">Access Control Mechanisms</span></span>](access-control-mechanisms.md)  
 <span data-ttu-id="83d2d-107">WCF의 권한 부여 메커니즘과 제안 된 사용에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="83d2d-108">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="83d2d-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="83d2d-109"><xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하여 서비스에 대한 액세스를 제한하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="83d2d-110">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="83d2d-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="83d2d-111">ASP.NET의 역할 공급자 기능을 사용할 수 있도록 하는 서비스의 구성 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="83d2d-112">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="83d2d-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="83d2d-113">ASP.NET은 권한 부여 관리자를 사용 하 여 웹 사이트에 대 한 권한 부여를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="83d2d-114">WCF는 마찬가지로 클라이언트 권한 부여를 위해 ASP.NET/Authorization Manager 조합을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="83d2d-115">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="83d2d-115">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="83d2d-116">클레임 기반 권한 부여에 ID 모델 인프라를 사용하는 기본적인 사용법에 대해 설명합니다 .</span><span class="sxs-lookup"><span data-stu-id="83d2d-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="83d2d-117">위임 및 가장</span><span class="sxs-lookup"><span data-stu-id="83d2d-117">Delegation and Impersonation</span></span>](delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="83d2d-118">위임과 가장의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2d-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="83d2d-119">참고</span><span class="sxs-lookup"><span data-stu-id="83d2d-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="83d2d-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="83d2d-120">Related Sections</span></span>  
 [<span data-ttu-id="83d2d-121">인증</span><span class="sxs-lookup"><span data-stu-id="83d2d-121">Authentication</span></span>](authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="83d2d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83d2d-122">See also</span></span>

- [<span data-ttu-id="83d2d-123">보안 개요</span><span class="sxs-lookup"><span data-stu-id="83d2d-123">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="83d2d-124">[Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="83d2d-124">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
