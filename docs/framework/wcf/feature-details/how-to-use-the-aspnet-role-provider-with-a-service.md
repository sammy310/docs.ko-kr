---
title: '방법: 서비스에서 ASP.NET 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: f989252c7dd9b2ccdce8331e7cdd987042230ded
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880239"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="2f4cb-102">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="2f4cb-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="2f4cb-103">(ASP.NET 멤버 자격 공급자와 함께)에서 ASP.NET 역할 공급자 기능은 ASP.NET 개발자가 사용자가 사이트를 사용 하 여 계정 만들기를 권한 부여를 위해 역할을 할당 받을 수 있도록 웹 사이트를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="2f4cb-104">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="2f4cb-105">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="2f4cb-106">대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="2f4cb-107">샘플 응용 프로그램을 참조 하세요 [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="2f4cb-108">ASP.NET 멤버 자격 공급자 기능에 대 한 자세한 내용은 참조 하세요. [방법: ASP.NET 멤버 자격 공급자를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="2f4cb-109">역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="2f4cb-110">Windows Communication Foundation (WCF) 개발자는 보안상의 이유로 이러한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="2f4cb-111">WCF 응용 프로그램을 통합 하는 경우 사용자가 WCF 클라이언트 응용 프로그램에는 사용자 이름/암호 조합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="2f4cb-112">인스턴스의 데이터베이스를 사용 하도록 WCF를 사용 하도록 설정 하려면 만들어야 합니다 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 클래스에서 해당 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> 속성을 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, 동작의 컬렉션에 인스턴스를 추가 하 고는 <xref:System.ServiceModel.ServiceHost> 서비스를 호스트 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="2f4cb-113">역할 공급자를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="2f4cb-113">To configure the role provider</span></span>  
  
1. <span data-ttu-id="2f4cb-114">Web.config 파일에 아래는 <`system.web`> 요소를 추가 <`roleManager`> 요소 집합과 해당 `enabled` 특성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="2f4cb-115">`defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="2f4cb-116">에 자식 항목으로 <`roleManager`> 요소에 추가 <`providers`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="2f4cb-117">에 자식 항목으로 <`providers`> 요소를 추가 <`add`> 요소는 다음 특성을 사용 하 여 적절 한 값으로 설정: `name`, `type`를 `connectionStringName`, 및 `applicationName`다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="2f4cb-118">역할 공급자를 사용하도록 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="2f4cb-118">To configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="2f4cb-119">Web.config 파일에 추가 된 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="2f4cb-120">추가 된 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 <`system.ServiceModel`> 요소.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="2f4cb-121">추가 된 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="2f4cb-122">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 `name` 특성을 적절 한 값으로.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="2f4cb-123">추가 된 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 에 <`behavior`> 요소.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="2f4cb-124">`principalPermissionMode` 특성을 `UseAspNetRoles`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="2f4cb-125">`roleProviderName` 특성을 `SqlRoleProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="2f4cb-126">다음 예제에서는 구성의 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f4cb-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f4cb-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f4cb-127">See also</span></span>

- [<span data-ttu-id="2f4cb-128">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="2f4cb-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="2f4cb-129">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="2f4cb-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
