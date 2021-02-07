---
description: '자세한 정보: 방법: 서비스와 함께 ASP.NET 역할 공급자 사용'
title: '방법: 서비스에서 ASP.NET 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 24bf9ad72d3634baf1d7120e4e60ccde5a4078a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734115"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="9c36e-103">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="9c36e-103">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="9c36e-104">ASP.NET 역할 공급자 (ASP.NET 멤버 자격 공급자와 함께 사용)는 ASP.NET 개발자가 사이트를 사용 하 여 계정을 만들고 권한 부여를 위해 역할을 할당할 수 있도록 하는 웹 사이트를 만들 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-104">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="9c36e-105">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-105">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="9c36e-106">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-106">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="9c36e-107">대신 자격 증명 (사용자 이름/암호 조합)을 제공 하는 모든 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-107">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="9c36e-108">응용 프로그램 예제는 [멤버 자격 및 역할 공급자](../samples/membership-and-role-provider.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c36e-108">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="9c36e-109">ASP.NET membership provider 기능에 대 한 자세한 내용은 [방법: ASP.NET 멤버 자격 공급자 사용](how-to-use-the-aspnet-membership-provider.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c36e-109">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="9c36e-110">역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-110">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="9c36e-111">WCF (Windows Communication Foundation) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="9c36e-112">WCF 응용 프로그램에 통합 된 경우 사용자는 WCF 클라이언트 응용 프로그램에 대 한 사용자 이름/암호 조합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-112">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="9c36e-113">WCF가 데이터베이스를 사용할 수 있도록 하려면 클래스의 인스턴스를 만들고, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 해당 속성을로 설정 하 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> 고, 서비스를 호스팅하는에 대 한 동작 컬렉션에 인스턴스를 추가 <xref:System.ServiceModel.ServiceHost> 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-113">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="9c36e-114">역할 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="9c36e-114">Configure the role provider</span></span>  
  
1. <span data-ttu-id="9c36e-115">Web.config 파일의 <> 요소 아래에서 `system.web` <> 요소를 추가 하 `roleManager` 고 `enabled` 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-115">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="9c36e-116">`defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-116">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="9c36e-117"><> 요소에 대 한 자식으로 `roleManager` <`providers`> 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-117">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="9c36e-118"><> 요소에 대 한 자식으로, `providers` `add` `name` `type` `connectionStringName` 다음 예제와 같이 적절 한 값으로 설정 된,, 및 특성을 사용 하 여 <> 요소를 추가 `applicationName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-118">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="9c36e-119">역할 공급자를 사용 하도록 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="9c36e-119">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="9c36e-120">Web.config 파일에서 요소를 추가 [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-120">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="9c36e-121">요소를 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) <`system.ServiceModel`> 요소에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-121">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="9c36e-122">[\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)<> 요소에를 추가 `behaviors` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-122">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="9c36e-123">요소를 추가 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 하 고 `name` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-123">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="9c36e-124">[\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md)<> 요소에를 추가 `behavior` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-124">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="9c36e-125">`principalPermissionMode` 특성을 `UseAspNetRoles`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-125">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="9c36e-126">`roleProviderName` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-126">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="9c36e-127">다음 예제에서는 구성의 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9c36e-127">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9c36e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c36e-128">See also</span></span>

- [<span data-ttu-id="9c36e-129">Membership and Role Provider</span><span class="sxs-lookup"><span data-stu-id="9c36e-129">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="9c36e-130">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="9c36e-130">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
