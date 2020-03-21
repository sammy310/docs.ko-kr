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
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>방법: 서비스에서 ASP.NET 역할 공급자 사용

ASP.NET 역할 공급자(ASP.NET 멤버 자격 공급자와 함께)는 ASP.NET 개발자가 사용자가 사이트로 계정을 만들고 권한 부여를 위해 역할을 할당할 수 있는 웹 사이트를 만들 수 있도록 하는 기능입니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자격 증명(사용자 이름/암호 조합)을 제공하는 모든 사용자는 사이트와 해당 서비스를 사용할 수 있습니다.  
  
샘플 응용 프로그램에 대 한 [멤버 자격 및 역할 공급자를](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)참조 합니다. ASP.NET 멤버십 공급자 기능에 대한 자세한 내용은 ASP.NET [멤버십 공급자 를 사용하는 방법](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)참조.  
  
역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다. WCF(Windows 통신 재단) 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다. WCF 응용 프로그램에 통합된 경우 사용자는 WCF 클라이언트 응용 프로그램에 사용자 이름/암호 조합을 제공해야 합니다. WCF가 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 데이터베이스를 사용하도록 설정하려면 클래스의 인스턴스를 만들고, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> 해당 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>속성을 로 설정하고, 인스턴스를 서비스를 호스팅하는 동작 컬렉션에 <xref:System.ServiceModel.ServiceHost> 추가해야 합니다.  
  
## <a name="configure-the-role-provider"></a>역할 공급자 구성  
  
1. `system.web` Web.config 파일에서 <> 요소 아래에 <`roleManager`> 요소를 `enabled` 추가하고 `true`해당 특성을 에 설정합니다.  
  
2. `defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.  
  
3. <`roleManager`> 요소에 자식으로 <`providers`> 요소를 추가합니다.  
  
4. `providers` <> 요소에 자식으로 다음 `add` 예제와 같이 다음 `name`값으로 `type` `connectionStringName` `applicationName`설정된 다음 특성이 있는 <> 요소를 추가합니다.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>역할 공급자를 사용하도록 서비스 구성  
  
1. Web.config 파일에서 [ \<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가합니다.  
  
2. <`system.ServiceModel`> 요소에 [ \<비헤이비어>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 추가합니다.  
  
3. <> 요소에 서비스 동작>추가합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) `behaviors`  
  
4. 동작>요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
  
5. <> 요소에 서비스권한 부여>추가합니다. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) `behavior`  
  
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

- [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [방법: ASP.NET 멤버 자격 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
