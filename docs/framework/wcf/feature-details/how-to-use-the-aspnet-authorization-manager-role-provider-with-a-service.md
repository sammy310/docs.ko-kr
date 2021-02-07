---
description: '자세한 정보: 방법: 서비스와 함께 ASP.NET 권한 부여 관리자 역할 공급자 사용'
title: '방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 24d6bbbf2181189104fb0df0068130c402fd2f68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734128"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="228e9-103">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="228e9-103">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>

<span data-ttu-id="228e9-104">ASP.NET가 웹 서비스를 호스팅하는 경우 권한 부여 관리자를 응용 프로그램에 통합 하 여 서비스에 대 한 권한 부여를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-104">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="228e9-105">애플리케이션 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-105">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="228e9-106">관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-106">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="228e9-107">권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC(Microsoft Management Console) 스냅인과 같은 관리 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-107">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="228e9-108">관리자는 XML 파일, Active Directory 또는 ADAM(Active Directory Application Mode) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-108">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="228e9-109">권한 부여 관리자는 웹 서비스를 호스트 하는 ASP.NET 응용 프로그램에 대 한 권한 부여 관리자 ASP.NET 역할 공급자를 구성 하 여 응용 프로그램에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-109">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="228e9-110">다른 ASP.NET 역할 공급자와 마찬가지로 권한 부여 관리자 ASP.NET 역할 공급자는 <> 요소를 사용 하 여 구성 됩니다 `providers` .</span><span class="sxs-lookup"><span data-stu-id="228e9-110">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="228e9-111">다음 코드 예제는 권한 부여 관리자를 애플리케이션에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="228e9-111">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="228e9-112">ASP.NET 역할 공급자를 WCF 응용 프로그램과 통합 하는 방법에 대 한 자세한 내용은 [방법: 서비스에 ASP.NET 역할 공급자 사용](how-to-use-the-aspnet-role-provider-with-a-service.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228e9-112">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="228e9-113">ASP.NET에서 권한 부여 관리자를 사용 하는 방법에 대 한 자세한 내용은 [How to: Use Authorization manager (AzMan) with ASP.NET 2.0](/previous-versions/msp-n-p/ff649313(v=pandp.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228e9-113">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228e9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="228e9-114">See also</span></span>

- [<span data-ttu-id="228e9-115">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="228e9-115">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
