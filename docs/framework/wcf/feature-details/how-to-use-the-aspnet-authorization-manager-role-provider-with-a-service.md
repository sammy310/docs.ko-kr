---
title: '방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: ebdfa8bd7d222c4f9a33b6718b215d327d589c6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073574"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용
[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에서 웹 서비스를 호스트할 때 권한 부여 관리자를 응용 프로그램에 통합하여 서비스에 권한을 부여할 수 있습니다. 응용 프로그램 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다. 관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다. 권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC(Microsoft Management Console) 스냅인과 같은 관리 도구를 제공합니다. 관리자는 XML 파일, Active Directory 또는 ADAM(Active Directory Application Mode) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.  
  
 웹 서비스를 호스트하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에 대한 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 구성하여 권한 부여 관리자를 응용 프로그램에 통합합니다. 와 같은 다른 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자와 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 사용 하 여 구성 되어 합니다 <`providers`> 요소입니다.  
  
 다음 코드 예제는 권한 부여 관리자를 응용 프로그램에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.  
  
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
  
 통합 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] WCF 응용 프로그램의 경우 역할 공급자 참조 [방법: ASP.NET 역할 공급자를 사용 하 여 서비스를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)입니다. 권한 부여 관리자를 사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]를 참조 하세요 [방법: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303)합니다.  
  
## <a name="see-also"></a>참고자료

- [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
