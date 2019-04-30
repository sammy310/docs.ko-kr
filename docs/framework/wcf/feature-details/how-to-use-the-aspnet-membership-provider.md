---
title: '방법: ASP.NET 멤버 자격 공급자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 8011b026e857dd6e5815ef7da00c1c33db8b5b4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038716"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="c96e7-102">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="c96e7-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="c96e7-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발자가 웹 사이트를 만들어 사용자에게 고유 사용자 이름 및 암호 조합을 만들 수 있도록 해주는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="c96e7-104">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="c96e7-105">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="c96e7-106">대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="c96e7-107">샘플 응용 프로그램을 참조 하세요 [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="c96e7-108">사용에 관한 정보를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자 기능 참조 [방법: ASP.NET 역할 공급자를 사용 하 여 서비스를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="c96e7-109">멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="c96e7-110">해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="c96e7-111">Windows Communication Foundation (WCF) 개발자는 보안상의 이유로 이러한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="c96e7-112">WCF 응용 프로그램을 통합 하는 경우 사용자가 WCF 클라이언트 응용 프로그램에는 사용자 이름/암호 조합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="c96e7-113">WCF 서비스에 데이터를 전송 하려면와 같은 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용 하 여는 <xref:System.ServiceModel.WSHttpBinding> (구성에서 합니다 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) 자격 증명 유형을 클라이언트를설정하고`UserName`.</span><span class="sxs-lookup"><span data-stu-id="c96e7-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="c96e7-114">서비스에서 WCF 보안 사용자 이름 및 암호를 기반으로 사용자를 인증 하 고 지정 된 역할 할당을 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c96e7-115">WCF는 사용자 이름/암호 조합 사용 하 여 데이터베이스 또는 기타 사용자 정보를 채우는 메서드를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="c96e7-116">멤버 자격 공급자를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c96e7-116">To configure the membership provider</span></span>  
  
1. <span data-ttu-id="c96e7-117">Web.config 파일에 아래는 <`system.web`> 요소를 만들기는 <`membership`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2. <span data-ttu-id="c96e7-118">`<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3. <span data-ttu-id="c96e7-119">에 자식 항목으로 <`providers`> 요소를 추가 `<clear />` 요소를 공급자의 컬렉션을 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4. <span data-ttu-id="c96e7-120">아래는 `<clear />` 요소를 만들기는 <`add`> 요소는 다음 특성을 사용 하 여 적절 한 값으로 설정: `name`, `type`, `connectionStringName`를 `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` 하십시오 `requiresUniqueEmail`, 및 `passwordFormat`합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="c96e7-121">`name` 특성은 나중에 구성 파일의 값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="c96e7-122">다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="c96e7-123">다음 예제에서는 구성 섹션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-123">The following example shows the configuration section.</span></span>  
  
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
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="c96e7-124">사용자 이름/암호 조합을 허용하도록 서비스 보안을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c96e7-124">To configure service security to accept the user name/password combination</span></span>  
  
1. <span data-ttu-id="c96e7-125">구성 파일에 아래 합니다 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="c96e7-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2. <span data-ttu-id="c96e7-126">추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 를 바인딩 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="c96e7-127">WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3. <span data-ttu-id="c96e7-128">`mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4. <span data-ttu-id="c96e7-129">설정 합니다 `clientCredentialType` 특성을 <`message`> 요소를 `UserName`입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="c96e7-130">이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="c96e7-131">다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-131">The following example shows the configuration code for the binding.</span></span>  
  
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
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="c96e7-132">멤버 자격 공급자를 사용하여 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c96e7-132">To configure a service to use the membership provider</span></span>  
  
1. <span data-ttu-id="c96e7-133">에 자식 항목으로 `<system.serviceModel>` 요소를 추가 된 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소</span><span class="sxs-lookup"><span data-stu-id="c96e7-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2. <span data-ttu-id="c96e7-134">추가 된 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소.</span><span class="sxs-lookup"><span data-stu-id="c96e7-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3. <span data-ttu-id="c96e7-135">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 설정 하 고는 `name` 특성을 적절 한 값으로.</span><span class="sxs-lookup"><span data-stu-id="c96e7-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="c96e7-136">추가 된 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 <`behavior`> 요소.</span><span class="sxs-lookup"><span data-stu-id="c96e7-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5. <span data-ttu-id="c96e7-137">추가 된 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 `<serviceCredentials>` 요소.</span><span class="sxs-lookup"><span data-stu-id="c96e7-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6. <span data-ttu-id="c96e7-138">`userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c96e7-139">경우는 `userNamePasswordValidationMode` 값 설정 하지 않으면, 대신 Windows 인증을 사용 하는 WCF는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7. <span data-ttu-id="c96e7-140">`membershipProviderName` 특성을 공급자의 이름으로 설정합니다(이 항목의 첫 번째 절차에서 공급자를 추가할 때 지정됨).</span><span class="sxs-lookup"><span data-stu-id="c96e7-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="c96e7-141">다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="c96e7-142">예제</span><span class="sxs-lookup"><span data-stu-id="c96e7-142">Example</span></span>  
 <span data-ttu-id="c96e7-143">다음 코드에서는 ASP 멤버 자격 기능을 사용하는 서비스의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c96e7-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c96e7-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="c96e7-144">See also</span></span>

- [<span data-ttu-id="c96e7-145">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="c96e7-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="c96e7-146">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="c96e7-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
