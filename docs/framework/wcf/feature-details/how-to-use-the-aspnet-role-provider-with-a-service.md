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
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>방법: 서비스에서 ASP.NET 역할 공급자 사용

ASP.NET 역할 공급자 (ASP.NET 멤버 자격 공급자와 함께 사용)는 ASP.NET 개발자가 사이트를 사용 하 여 계정을 만들고 권한 부여를 위해 역할을 할당할 수 있도록 하는 웹 사이트를 만들 수 있도록 하는 기능입니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자격 증명 (사용자 이름/암호 조합)을 제공 하는 모든 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.  
  
응용 프로그램 예제는 [멤버 자격 및 역할 공급자](../samples/membership-and-role-provider.md)를 참조 하세요. ASP.NET membership provider 기능에 대 한 자세한 내용은 [방법: ASP.NET 멤버 자격 공급자 사용](how-to-use-the-aspnet-membership-provider.md)을 참조 하세요.  
  
역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다. WCF (Windows Communication Foundation) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다. WCF 응용 프로그램에 통합 된 경우 사용자는 WCF 클라이언트 응용 프로그램에 대 한 사용자 이름/암호 조합을 제공 해야 합니다. WCF가 데이터베이스를 사용할 수 있도록 하려면 클래스의 인스턴스를 만들고, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 해당 속성을로 설정 하 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> 고, 서비스를 호스팅하는에 대 한 동작 컬렉션에 인스턴스를 추가 <xref:System.ServiceModel.ServiceHost> 해야 합니다.  
  
## <a name="configure-the-role-provider"></a>역할 공급자 구성  
  
1. Web.config 파일의 <> 요소 아래에서 `system.web` <> 요소를 추가 하 `roleManager` 고 `enabled` 특성을로 설정 `true` 합니다.  
  
2. `defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.  
  
3. <> 요소에 대 한 자식으로 `roleManager` <`providers`> 요소를 추가 합니다.  
  
4. <> 요소에 대 한 자식으로, `providers` `add` `name` `type` `connectionStringName` 다음 예제와 같이 적절 한 값으로 설정 된,, 및 특성을 사용 하 여 <> 요소를 추가 `applicationName` 합니다.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>역할 공급자를 사용 하도록 서비스 구성  
  
1. Web.config 파일에서 요소를 추가 [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 합니다.  
  
2. 요소를 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) <`system.ServiceModel`> 요소에 추가 합니다.  
  
3. [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md)<> 요소에를 추가 `behaviors` 합니다.  
  
4. 요소를 추가 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 하 고 `name` 특성을 적절 한 값으로 설정 합니다.  
  
5. [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md)<> 요소에를 추가 `behavior` 합니다.  
  
6. `principalPermissionMode` 특성을 `UseAspNetRoles`으로 설정합니다.  
  
7. `roleProviderName` 특성을 `SqlRoleProvider`으로 설정합니다. 다음 예제에서는 구성의 단편을 보여 줍니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [Membership and Role Provider](../samples/membership-and-role-provider.md)
- [방법: ASP.NET 멤버 자격 공급자 사용](how-to-use-the-aspnet-membership-provider.md)
