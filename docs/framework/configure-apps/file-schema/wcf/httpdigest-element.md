---
title: <httpDigest> 요소
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 914711e4d6c3dbb1ccc741af1b3abd6b8de716a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165323"
---
# <a name="httpdigest-element"></a>\<httpDigest > 요소
서비스에게 클라이언트를 인증하는 데 사용되는 다이제스트 형식 자격 증명을 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<httpDigest>  
  
## <a name="syntax"></a>구문  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`impersonationLevel`|클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다. 클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다. 유효한 값은 다음과 같습니다.<br /><br /> 식별: 서버 id 및 클라이언트의 권한을 가져올 수는 있지만 클라이언트를 가장할 수 없습니다.<br />가장 합니다. 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.<br />-위임 합니다. 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.<br />익명: 서버를 가장 하거나 클라이언트를 식별할 수 없습니다.<br />-None. 가장 수준이 할당 되지 않습니다.<br /><br /> 기본값은 Identification입니다. 이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 다이제스트는 알고리즘과 입력 집합을 통해 확인되는 해시입니다. 인증자 및 인증된 사용자는 알고리즘에 동의하고 입력으로 사용된 데이터를 교환합니다. 클라이언트는 해시를 계산하여 서비스로 보냅니다. 서비스에서도 해시를 계산하여 값을 비교합니다. 값이 일치하면 클라이언트가 확인됩니다.  
  
 이 기능은 Windows 및 IIS(인터넷 정보 서비스)의 Active Directory를 통해 사용해야 합니다. 자세한 내용은 [IIS 6.0의 다이제스트 인증](https://go.microsoft.com/fwlink/?LinkId=88443)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
- [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
