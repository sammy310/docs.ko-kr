---
title: '방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 778af929b4cfc96ce0683d304be5f8fb87a0e47b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880194"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="d017d-102">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="d017d-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="d017d-103">ASP.NET 웹 서비스를 호스트 하는 경우에 서비스에 권한 부여를 제공 하는 응용 프로그램에 권한 부여 관리자를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="d017d-104">응용 프로그램 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="d017d-105">관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="d017d-106">권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC(Microsoft Management Console) 스냅인과 같은 관리 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="d017d-107">관리자는 XML 파일, Active Directory 또는 ADAM(Active Directory Application Mode) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="d017d-108">권한 부여 관리자는 웹 서비스를 호스팅하는 ASP.NET 응용 프로그램에 대 한 권한 부여 관리자 ASP.NET 역할 공급자를 구성 하 여 응용 프로그램에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="d017d-109">다른 ASP.NET 역할 공급자와 같은 권한 부여 관리자 ASP.NET 역할 공급자 사용 하 여 구성 되는 <`providers`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="d017d-110">다음 코드 예제는 권한 부여 관리자를 응용 프로그램에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="d017d-111">WCF 응용 프로그램을 사용 하 여 ASP.NET 역할 공급자를 통합 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: ASP.NET 역할 공급자를 사용 하 여 서비스를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="d017d-112">ASP.NET을 사용 하 여 권한 부여 관리자를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303)합니다.</span><span class="sxs-lookup"><span data-stu-id="d017d-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d017d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d017d-113">See also</span></span>

- [<span data-ttu-id="d017d-114">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="d017d-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
