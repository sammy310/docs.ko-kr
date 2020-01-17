---
title: '방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 20955578ce4d344c2057036c0944557edf737389
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212230"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용
ASP.NET가 웹 서비스를 호스팅하는 경우 권한 부여 관리자를 응용 프로그램에 통합 하 여 서비스에 대 한 권한 부여를 제공할 수 있습니다. 애플리케이션 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다. 관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다. 권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC(Microsoft Management Console) 스냅인과 같은 관리 도구를 제공합니다. 관리자는 XML 파일, Active Directory 또는 ADAM(Active Directory Application Mode) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.  
  
 권한 부여 관리자는 웹 서비스를 호스트 하는 ASP.NET 응용 프로그램에 대 한 권한 부여 관리자 ASP.NET 역할 공급자를 구성 하 여 응용 프로그램에 통합 됩니다. 다른 ASP.NET 역할 공급자와 마찬가지로 권한 부여 관리자 ASP.NET 역할 공급자는 <`providers`> 요소를 사용 하 여 구성 됩니다.  
  
 다음 코드 예제는 권한 부여 관리자를 애플리케이션에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.  
  
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
  
 ASP.NET 역할 공급자를 WCF 응용 프로그램과 통합 하는 방법에 대 한 자세한 내용은 [방법: 서비스에 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)을 참조 하세요. ASP.NET에서 권한 부여 관리자를 사용 하는 방법에 대 한 자세한 내용은 [How to: Use Authorization manager (AzMan) with ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10))을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
