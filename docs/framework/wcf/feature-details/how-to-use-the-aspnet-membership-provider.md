---
title: '방법: ASP.NET 멤버 자격 공급자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 840e4a5d365f2adbaf335c1061a580665a39824d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595325"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>방법: ASP.NET 멤버 자격 공급자 사용

ASP.NET 멤버 자격 공급자는 ASP.NET 개발자가 고유한 사용자 이름 및 암호 조합을 만들 수 있는 웹 사이트를 만들 수 있도록 하는 기능입니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자격 증명 (사용자 이름/암호 조합)을 제공 하는 모든 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.

응용 프로그램 예제는 [멤버 자격 및 역할 공급자](../samples/membership-and-role-provider.md)를 참조 하세요. ASP.NET 역할 공급자 기능 사용에 대 한 자세한 내용은 [방법: 서비스에 ASP.NET 역할 공급자 사용](how-to-use-the-aspnet-role-provider-with-a-service.md)을 참조 하세요.

멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다. 해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.

WCF (Windows Communication Foundation) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다. WCF 응용 프로그램에 통합 된 경우 사용자는 WCF 클라이언트 응용 프로그램에 대 한 사용자 이름/암호 조합을 제공 해야 합니다. 데이터를 WCF 서비스로 전송 하려면 (구성에서)와 같이 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용 하 <xref:System.ServiceModel.WSHttpBinding> [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 고 클라이언트 자격 증명 형식을로 설정 합니다 `UserName` . 서비스에서 WCF 보안은 사용자 이름 및 암호를 기반으로 사용자를 인증 하 고 ASP.NET 역할에 지정 된 역할도 할당 합니다.

> [!NOTE]
> WCF는 사용자 이름/암호 조합이 나 기타 사용자 정보를 사용 하 여 데이터베이스를 채우는 메서드를 제공 하지 않습니다.

### <a name="to-configure-the-membership-provider"></a>멤버 자격 공급자를 구성하려면

1. Web.config 파일의 < `system.web` > 요소 아래에서 < `membership` > 요소를 만듭니다.

2. `<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.

3. <> 요소에 대 한 자식인 `providers` 요소를 추가 `<clear />` 하 여 공급자 컬렉션을 플러시합니다.

4. 요소 아래에서,,,,,,, `<clear />` `add` 및 특성을 적절 한 값으로 설정 하 여 <> 요소를 만듭니다 `name` `type` `connectionStringName` `applicationName` `enablePasswordRetrieval` `enablePasswordReset` `requiresQuestionAndAnswer` `requiresUniqueEmail` `passwordFormat` . `name` 특성은 나중에 구성 파일의 값으로 사용됩니다. 다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.

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

1. 구성 파일의 요소 아래에 [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) 합니다.

2. 를 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 바인딩 섹션에 추가 합니다. WCF 바인딩 요소를 만드는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](../how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요.

3. `mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.

4. `clientCredentialType`<`message`> 요소의 특성을로 설정 `UserName` 합니다. 이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.

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

1. 요소에 대 한 자식으로 `<system.serviceModel>` 요소를 추가 합니다. [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)

2. [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)<> 요소에를 추가 `behaviors` 합니다.

3. 를 추가 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 하 고 `name` 특성을 적절 한 값으로 설정 합니다.

4. [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md)<> 요소에를 추가 `behavior` 합니다.

5. [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md)요소에를 추가 `<serviceCredentials>` 합니다.

6. `userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.

    > [!IMPORTANT]
    > `userNamePasswordValidationMode`값이 설정 되지 않은 경우 WCF는 ASP.NET 멤버 자격 공급자 대신 Windows 인증을 사용 합니다.

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

## <a name="see-also"></a>참고 항목

- [방법: 서비스에서 ASP.NET 역할 공급자 사용](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Membership and Role Provider](../samples/membership-and-role-provider.md)
