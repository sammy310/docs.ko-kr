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
# <a name="how-to-use-the-aspnet-membership-provider"></a>방법: ASP.NET 멤버 자격 공급자 사용
[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발자가 웹 사이트를 만들어 사용자에게 고유 사용자 이름 및 암호 조합을 만들 수 있도록 해주는 기능입니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.  
  
 샘플 응용 프로그램을 참조 하세요 [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다. 사용에 관한 정보를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자 기능 참조 [방법: ASP.NET 역할 공급자를 사용 하 여 서비스를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)입니다.  
  
 멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다. 해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.  
  
 Windows Communication Foundation (WCF) 개발자는 보안상의 이유로 이러한 기능을 사용할 수 있습니다. WCF 응용 프로그램을 통합 하는 경우 사용자가 WCF 클라이언트 응용 프로그램에는 사용자 이름/암호 조합을 제공 해야 합니다. WCF 서비스에 데이터를 전송 하려면와 같은 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용 하 여는 <xref:System.ServiceModel.WSHttpBinding> (구성에서 합니다 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) 자격 증명 유형을 클라이언트를설정하고`UserName`. 서비스에서 WCF 보안 사용자 이름 및 암호를 기반으로 사용자를 인증 하 고 지정 된 역할 할당을 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할입니다.  
  
> [!NOTE]
>  WCF는 사용자 이름/암호 조합 사용 하 여 데이터베이스 또는 기타 사용자 정보를 채우는 메서드를 제공 하지 않습니다.  
  
### <a name="to-configure-the-membership-provider"></a>멤버 자격 공급자를 구성하려면  
  
1. Web.config 파일에 아래는 <`system.web`> 요소를 만들기는 <`membership`> 요소입니다.  
  
2. `<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.  
  
3. 에 자식 항목으로 <`providers`> 요소를 추가 `<clear />` 요소를 공급자의 컬렉션을 플러시합니다.  
  
4. 아래는 `<clear />` 요소를 만들기는 <`add`> 요소는 다음 특성을 사용 하 여 적절 한 값으로 설정: `name`, `type`, `connectionStringName`를 `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` 하십시오 `requiresUniqueEmail`, 및 `passwordFormat`합니다. `name` 특성은 나중에 구성 파일의 값으로 사용됩니다. 다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.  
  
     다음 예제에서는 구성 섹션을 보여 줍니다.  
  
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
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>사용자 이름/암호 조합을 허용하도록 서비스 보안을 구성하려면  
  
1. 구성 파일에 아래 합니다 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소.  
  
2. 추가 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 를 바인딩 섹션입니다. WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
3. `mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.  
  
4. 설정 합니다 `clientCredentialType` 특성을 <`message`> 요소를 `UserName`입니다. 이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.  
  
     다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.  
  
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
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a>멤버 자격 공급자를 사용하여 서비스를 구성하려면  
  
1. 에 자식 항목으로 `<system.serviceModel>` 요소를 추가 된 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소  
  
2. 추가 된 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소.  
  
3. 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 설정 하 고는 `name` 특성을 적절 한 값으로.  
  
4. 추가 된 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 <`behavior`> 요소.  
  
5. 추가 된 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 `<serviceCredentials>` 요소.  
  
6. `userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.  
  
    > [!IMPORTANT]
    >  경우는 `userNamePasswordValidationMode` 값 설정 하지 않으면, 대신 Windows 인증을 사용 하는 WCF는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자입니다.  
  
7. `membershipProviderName` 특성을 공급자의 이름으로 설정합니다(이 항목의 첫 번째 절차에서 공급자를 추가할 때 지정됨). 다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.  
  
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
  
## <a name="example"></a>예제  
 다음 코드에서는 ASP 멤버 자격 기능을 사용하는 서비스의 구성을 보여 줍니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
