---
title: WCF에서 권한 부여
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 67da01508fbb8f14b6405b79445bdef297e63288
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247488"
---
# <a name="authorization-in-wcf"></a>WCF에서 권한 부여

권한 부여는 서비스나 파일과 같은 리소스에 대한 액세스 및 권한을 제어하는 프로세스입니다. 이 단원의 항목에서는 Windows Communication Foundation (WCF)에서 다양 한 방법으로이 기본 작업을 수행 하는 방법을 보여 줍니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [Access Control 메커니즘](access-control-mechanisms.md)  
 WCF의 권한 부여 메커니즘과 제안 된 사용에 대 한 간략 한 개요를 제공 합니다.  
  
 [방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하여 서비스에 대한 액세스를 제한하는 프로세스를 보여 줍니다.  
  
 [방법: 서비스에서 ASP.NET 역할 공급자 사용](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 ASP.NET의 역할 공급자 기능을 사용할 수 있도록 하는 서비스의 구성 과정을 안내 합니다.  
  
 [방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET은 권한 부여 관리자를 사용 하 여 웹 사이트에 대 한 권한 부여를 관리할 수 있습니다. WCF는 마찬가지로 클라이언트 권한 부여를 위해 ASP.NET/Authorization Manager 조합을 활용할 수 있습니다.  
  
 [ID 모델을 사용하여 클레임 및 권한 부여 관리](managing-claims-and-authorization-with-the-identity-model.md)  
 클레임 기반 권한 부여에 ID 모델 인프라를 사용하는 기본적인 사용법에 대해 설명합니다 .  
  
 [위임 및 가장](delegation-and-impersonation-with-wcf.md)  
 위임과 가장의 차이점을 설명합니다.  
  
## <a name="reference"></a>참고  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>관련 단원  

 [인증](authentication-in-wcf.md)  
  
## <a name="see-also"></a>참고 항목

- [보안 개요](security-overview.md)
- [Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))
