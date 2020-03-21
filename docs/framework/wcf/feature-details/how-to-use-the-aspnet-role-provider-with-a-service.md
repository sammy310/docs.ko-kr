---
title: '방법: 서비스에서 ASP.NET 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184764"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="5491f-102">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="5491f-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="5491f-103">ASP.NET 역할 공급자(ASP.NET 멤버 자격 공급자와 함께)는 ASP.NET 개발자가 사용자가 사이트로 계정을 만들고 권한 부여를 위해 역할을 할당할 수 있는 웹 사이트를 만들 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="5491f-104">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="5491f-105">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="5491f-106">대신 자격 증명(사용자 이름/암호 조합)을 제공하는 모든 사용자는 사이트와 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="5491f-107">샘플 응용 프로그램에 대 한 [멤버 자격 및 역할 공급자를](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="5491f-108">ASP.NET 멤버십 공급자 기능에 대한 자세한 내용은 ASP.NET [멤버십 공급자 를 사용하는 방법](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)참조.</span><span class="sxs-lookup"><span data-stu-id="5491f-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="5491f-109">역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="5491f-110">WCF(Windows 통신 재단) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="5491f-111">WCF 응용 프로그램에 통합된 경우 사용자는 WCF 클라이언트 응용 프로그램에 사용자 이름/암호 조합을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="5491f-112">WCF가 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 데이터베이스를 사용하도록 설정하려면 클래스의 인스턴스를 만들고, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> 해당 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>속성을 로 설정하고, 인스턴스를 서비스를 호스팅하는 동작 컬렉션에 <xref:System.ServiceModel.ServiceHost> 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="5491f-113">역할 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="5491f-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="5491f-114">`system.web` Web.config 파일에서 <> 요소 아래에 <`roleManager`> 요소를 `enabled` 추가하고 `true`해당 특성을 에 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="5491f-115">`defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="5491f-116"><`roleManager`> 요소에 자식으로 <`providers`> 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="5491f-117">`providers` <> 요소에 자식으로 다음 `add` 예제와 같이 다음 `name`값으로 `type` `connectionStringName` `applicationName`설정된 다음 특성이 있는 <> 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="5491f-118">역할 공급자를 사용하도록 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="5491f-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="5491f-119">Web.config 파일에서 [ \<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="5491f-120"><`system.ServiceModel`> 요소에 [ \<비헤이비어>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="5491f-121"><> 요소에 서비스 동작>추가합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) `behaviors`</span><span class="sxs-lookup"><span data-stu-id="5491f-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="5491f-122">동작>요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5491f-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="5491f-123"><> 요소에 서비스권한 부여>추가합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) `behavior`</span><span class="sxs-lookup"><span data-stu-id="5491f-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="5491f-124">`principalPermissionMode` 특성을 `UseAspNetRoles`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="5491f-125">`roleProviderName` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="5491f-126">다음 예제에서는 구성의 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5491f-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5491f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5491f-127">See also</span></span>

- [<span data-ttu-id="5491f-128">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="5491f-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="5491f-129">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="5491f-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
