---
title: '방법: ASP.NET 멤버 자격 공급자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: c2567b6abd42ae725b4786eb111e411f7328154e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939796"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="ed40e-102">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="ed40e-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="ed40e-103">ASP.NET 멤버 자격 공급자는 ASP.NET 개발자가 고유한 사용자 이름 및 암호 조합을 만들 수 있는 웹 사이트를 만들 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="ed40e-104">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="ed40e-105">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="ed40e-106">대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="ed40e-107">응용 프로그램 예제는 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed40e-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="ed40e-108">ASP.NET 역할 공급자 기능 [사용에 대 한 자세한 내용은 방법: 서비스](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)에서 ASP.NET 역할 공급자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="ed40e-109">멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="ed40e-110">해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="ed40e-111">WCF (Windows Communication Foundation) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="ed40e-112">WCF 응용 프로그램에 통합 된 경우 사용자는 WCF 클라이언트 응용 프로그램에 대 한 사용자 이름/암호 조합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="ed40e-113">데이터를 WCF 서비스로 전송 하려면 <xref:System.ServiceModel.WSHttpBinding> (구성의 `UserName` [ \<경우 wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md))와 같이 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용 하 고 클라이언트 자격 증명 형식을로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="ed40e-114">서비스에서 WCF 보안은 사용자 이름 및 암호를 기반으로 사용자를 인증 하 고 ASP.NET 역할에 지정 된 역할도 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed40e-115">WCF는 사용자 이름/암호 조합이 나 기타 사용자 정보를 사용 하 여 데이터베이스를 채우는 메서드를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="ed40e-116">멤버 자격 공급자를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ed40e-116">To configure the membership provider</span></span>  
  
1. <span data-ttu-id="ed40e-117">Web.config 파일의 <`system.web`> 요소 아래에서 <`membership`> 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2. <span data-ttu-id="ed40e-118">`<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3. <span data-ttu-id="ed40e-119"><`providers`> 요소에 대 한 자식인 `<clear />` 요소를 추가 하 여 공급자 컬렉션을 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4. <span data-ttu-id="ed40e-120">`connectionStringName` `type` `enablePasswordReset` `requiresQuestionAndAnswer` `enablePasswordRetrieval``add` `applicationName` `name`요소 아래에서 다음 특성을 적절 한 값으로 설정 하 여 < > 요소를 만듭니다.,,,,,, `<clear />` , `requiresUniqueEmail` 및`passwordFormat`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="ed40e-121">`name` 특성은 나중에 구성 파일의 값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="ed40e-122">다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="ed40e-123">다음 예제에서는 구성 섹션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-123">The following example shows the configuration section.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="ed40e-124">사용자 이름/암호 조합을 허용하도록 서비스 보안을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ed40e-124">To configure service security to accept the user name/password combination</span></span>  
  
1. <span data-ttu-id="ed40e-125">구성 파일의 [ \<system.servicemodel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소 아래에서 요소 > 바인딩을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2. <span data-ttu-id="ed40e-126">WsHttpBinding >를 바인딩 섹션에 추가 합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ed40e-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="ed40e-127">WCF 바인딩 요소를 [만드는 방법에 대 한 자세한 내용은 방법: 구성](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)에서 서비스 바인딩을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3. <span data-ttu-id="ed40e-128">`mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4. <span data-ttu-id="ed40e-129">`UserName`< `clientCredentialType` >`message`요소의 특성을로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="ed40e-130">이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="ed40e-131">다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-131">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="ed40e-132">멤버 자격 공급자를 사용하여 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ed40e-132">To configure a service to use the membership provider</span></span>  
  
1. <span data-ttu-id="ed40e-133">`<system.serviceModel>` 요소에 대 한 자식인 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2. <span data-ttu-id="ed40e-134">Servicebehaviors`behaviors`>를 < > 요소에 추가 합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ed40e-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3. <span data-ttu-id="ed40e-135">동작 > 추가 하 고 `name` 특성을 적절 한 값으로 설정 합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ed40e-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="ed40e-136"><`behavior`>요소에 [ serviceCredentials>를추가합니다.\<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="ed40e-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5. <span data-ttu-id="ed40e-137">요소에 [ \<userNameAuthentication](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) `<serviceCredentials>` >를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6. <span data-ttu-id="ed40e-138">`userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ed40e-139">`userNamePasswordValidationMode` 값이 설정 되지 않은 경우 WCF는 ASP.NET 멤버 자격 공급자 대신 Windows 인증을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>  
  
7. <span data-ttu-id="ed40e-140">`membershipProviderName` 특성을 공급자의 이름으로 설정합니다(이 항목의 첫 번째 절차에서 공급자를 추가할 때 지정됨).</span><span class="sxs-lookup"><span data-stu-id="ed40e-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="ed40e-141">다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="ed40e-142">예제</span><span class="sxs-lookup"><span data-stu-id="ed40e-142">Example</span></span>  
 <span data-ttu-id="ed40e-143">다음 코드에서는 ASP 멤버 자격 기능을 사용하는 서비스의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed40e-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed40e-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed40e-144">See also</span></span>

- [<span data-ttu-id="ed40e-145">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="ed40e-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="ed40e-146">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="ed40e-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
