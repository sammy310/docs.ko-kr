---
title: Access Control 메커니즘
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: b423dac4d8324069eb1825666419b23b5afdca63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185502"
---
# <a name="access-control-mechanisms"></a>Access Control 메커니즘
WCF(Windows 통신 재단)를 통해 여러 가지 방법으로 액세스를 제어할 수 있습니다. 이 항목에서는 여러 메커니즘에 대해 간략하게 설명하고 올바른 메커니즘을 선택하여 사용하도록 각 메커니즘을 사용하는 시기에 대해 설명합니다. 액세스 기술은 복잡성 순서대로 나열되어 있습니다. <xref:System.Security.Permissions.PrincipalPermissionAttribute>가 가장 단순하며 ID 모델이 가장 복잡합니다.  
  
 이러한 메커니즘 외에도 WCF를 사용하는 가장 및 위임은 [위임 및 가장에](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)설명되어 있습니다.  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>는 서비스 메서드에 대한 액세스를 제한하는 데 사용됩니다. 특성이 메서드에 적용되면 Windows 그룹 또는 ASP.NET 역할에서 특정 호출자의 ID 또는 구성원 자격을 요구하는 데 사용할 수 있습니다. X.509 인증서를 사용하여 클라이언트가 인증된 경우 클라이언트에 인증서의 지문 및 주체 이름으로 구성된 기본 ID가 지정됩니다.  
  
 항상 서비스의 사용자가 서비스를 실행 중인 동일한 Windows 도메인의 일부인 경우 그리고 서비스를 실행 중인 컴퓨터의 리소스에 대한 액세스를 제어하려면 <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용합니다. 없음, 읽기 전용 또는 읽기 및 쓰기와 같은 특정 수준의 액세스 권한을 가진 Windows 그룹을 손쉽게 만들 수 있습니다.  
  
 특성 사용에 대한 자세한 내용은 [사용 방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)을 참조하십시오. ID에 대한 자세한 내용은 [서비스 ID 및 인증을](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)참조하십시오.  
  
## <a name="aspnet-membership-provider"></a>ASP.NET 멤버 자격 공급자  
 ASP.NET 기능은 멤버십 공급자입니다. 멤버 자격 공급자가 기술적으로는 액세스 제어 메커니즘이 아닌 경우에도 이 공급자를 사용하면 서비스의 엔드포인트에 액세스할 수 있는 가능한 ID의 집합을 제한하여 서비스에 대한 액세스를 제어할 수 있습니다. 멤버 자격 기능에는 사용자 이름/암호의 조합으로 채울 수 있는 데이터베이스가 포함되며, 이 조합은 웹 사이트의 사용자가 사이트에 계정을 설정하는 데 사용할 수 있습니다. 멤버 자격 공급자를 사용하는 서비스에 액세스하려면 사용자가 사용자 이름과 암호로 로그온해야 합니다.  
  
> [!NOTE]
> WCF 서비스가 권한 부여를 위해 데이터베이스를 사용하려면 먼저 ASP.NET 기능을 사용하여 데이터베이스를 채워야 합니다.  
  
 기존 ASP.NET 웹 사이트의 멤버 자격 데이터베이스가 이미 있고 동일한 사용자 이름과 암호로 권한이 부여된 동일한 사용자가 서비스를 사용하도록 설정하려는 경우에도 멤버 자격 기능을 사용할 수 있습니다.  
  
 WCF 서비스의 멤버 자격 기능 사용에 대한 자세한 내용은 ASP.NET [멤버십 공급자 사용 방법을](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)참조하십시오.  
  
## <a name="aspnet-role-provider"></a>ASP.NET 역할 공급자  
 ASP.NET 또 다른 기능은 역할을 사용하여 권한 부여를 관리하는 기능입니다. ASP.NET 역할 공급자를 사용하면 개발자가 사용자에 대한 역할을 만들고 각 사용자를 역할 또는 역할에 할당할 수 있습니다. 멤버 자격 공급자와 마찬가지로 역할 및 할당은 데이터베이스에 저장되며 ASP.NET 역할 공급자의 특정 구현에서 제공하는 도구를 사용하여 채울 수 있습니다. 멤버 자격 기능과 마찬가지로 WCF 개발자는 데이터베이스의 정보를 사용하여 서비스 사용자에게 역할별로 권한을 부여할 수 있습니다. 예를 들어, 개발자는 위에서 설명한 `PrincipalPermissionAttribute` 액세스 제어 메커니즘과 함께 역할 공급자를 사용할 수 있습니다.  
  
 기존 ASP.NET 역할 공급자 데이터베이스가 있고 WCF 서비스에서 동일한 규칙 및 사용자 할당 집합을 사용하려는 경우 ASP.NET 역할 공급자를 사용할 수도 있습니다.  
  
 역할 공급자 기능 사용에 대한 자세한 내용은 [서비스 공급자를 ASP.NET 역할 공급자 를 사용하는 방법을](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)참조하십시오.  
  
## <a name="authorization-manager"></a>권한 부여 관리자  
 또 다른 기능은 권한 부여 관리자(AzMan)와 클라이언트에 권한을 부여하기 위한 ASP.NET 역할 공급자를 결합합니다. ASP.NET 웹 서비스를 호스팅하는 경우 AzMan을 응용 프로그램에 통합하여 AzMan을 통해 서비스에 대한 권한 부여를 수행할 수 있습니다. ASP.NET 역할 관리자는 응용 프로그램 역할을 관리하고, 역할에서 사용자를 추가 및 제거하고, 역할 구성원 자격을 확인할 수 있는 API를 제공하지만 사용자가 명명된 작업 또는 작업을 수행할 권한이 있는지 여부를 쿼리할 수는 없습니다. AzMan을 사용하면 개별 작업을 정의하여 다른 작업에 결합할 수 있습니다. AZMan을 사용하면 역할 확인뿐 아니라 사용자가 작업을 수행할 수 있는지 여부도 확인할 수 있습니다. 역할 할당 및 작업 인증은 애플리케이션 외부에서 구성하거나 애플리케이션 내부에서 프로그래밍 방식으로 수행할 수 있습니다. 관리자는 AzMan 관리 MMC(Microsoft Management Console) 스냅인을 사용하여 런타임에 역할에서 수행할 수 있는 작업을 변경하고 각 사용자의 역할 멤버 자격을 관리할 수 있습니다.  
  
 기존 AzMan 설치에 이미 액세스할 수 있고 AzMan/역할 공급자 조합의 기능을 사용하여 서비스 사용자에게 권한을 부여하려는 경우 AzMan 및 ASP.NET 역할 공급자를 사용할 수도 있습니다.  
  
 AzMan 및 ASP.NET 역할 공급자에 대한 자세한 내용은 [ASP.NET 2.0의 권한 부여 관리자(AzMan) 사용 방법을](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10))참조하십시오. WCF 서비스의 AzMan 및 역할 공급자 사용에 대한 자세한 내용은 서비스 ASP.NET [권한 부여 관리자 역할 공급자를 사용하는 방법을](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)참조하십시오.  
  
## <a name="identity-model"></a>ID 모델  
 ID 모델은 클라이언트에 권한을 부여하는 클레임 및 정책을 관리할 수 있는 API의 집합입니다. ID 모델을 사용하면 호출자가 서비스에서 자신을 인증하고, 클레임을 서비스의 정책 집합과 비교하고, 비교를 바탕으로 액세스 권한을 부여하거나 거부하는 데 사용한 자격 증명에 포함된 모든 클레임을 조사할 수 있습니다.  
  
 액세스 권한을 부여하기 전에 특정 범주를 설정하는 기능 및 정밀한 제어가 필요한 경우 ID 모델을 사용합니다. 예를 들어, <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하는 경우 기준은 단순히 사용자의 ID가 인증되었으며 특정 역할에 속하는지 여부입니다. 반대로 ID 모델을 사용하는 경우 유효한 운전 면허증을 소지한 19세 이상의 사용자만이 문서를 볼 수 있음이 명시된 정책을 만들 수 있습니다.  
  
 ID 모델 클레임 기반 액세스 제어가 유용한 한 가지 예는 발급된 토큰 시나리오에서 페더레이션 자격 증명을 사용하는 경우입니다. 페더레이션 및 발급된 토큰에 대한 자세한 내용은 [페더레이션 및 발급 된 토큰을](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)참조하십시오.  
  
 ID 모델에 대한 자세한 내용은 [ID 모델의 클레임 및 권한 부여 관리를](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [ID 모델을 사용하여 클레임 및 권한 부여 관리](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [위임 및 가장](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
