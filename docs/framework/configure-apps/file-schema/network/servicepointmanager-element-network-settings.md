---
title: <servicePointManager> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 407ed85de109a671030eccff8ddd92af91628014
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202211"
---
# <a name="servicepointmanager-element-network-settings"></a>\<servicePointManager > 요소 (네트워크 설정)
네트워크 리소스에 대 한 연결을 구성합니다.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<servicePointManager>  
  
## <a name="syntax"></a>구문  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`checkCertificateName`|시스템은 인증서의 이름과 인증서를 사용 하기 전에 서버 호스트 이름과 일치 하는지 확인 해야 하는지 여부를 지정 합니다. 기본값은 `true`입니다.|  
|`checkCertificateRevocationList`|시스템 인증서를 사용 하기 전에 인증서를 해지 되었는지 여부를 확인 해야 하는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
|`dnsRefreshTimeout`|밀리초 단위로 DNS 라운드 로빈 옵션을 함께 기간 서비스 DNS (도메인 이름) 해상도 캐시를 지정 합니다. 기본값은 120,000밀리초(2분)입니다.|  
|`enableDnsRoundRobin`|모든 주소 또는 하나의 항목만 반환 여러 IP (인터넷 프로토콜) 주소를 사용 하 여 호스트의 DNS 확인 이름을 여부를 지정 합니다. 기본값은 `false`입니다.|  
|`encryptionPolicy`|SSL/TLS 세션에 적용 된 암호화 정책을 지정을 <xref:System.Net.ServicePointManager> 인스턴스. 가능한 값은 값에 해당 하는 <xref:System.Net.Security.EncryptionPolicy> 열거형입니다. 사용 <xref:System.Security.Authentication.CipherAlgorithmType.Null> 암호화 정책으로 설정 된 경우 반드시 `NoEncryption`입니다. 기본값은 `RequireEncryption`입니다.|  
|`expect100Continue`|POST 메서드를 받을 예상 해야 하는지 여부를 지정 된 `100-continue` 서버에서 응답 합니다. 기본값은 `true`입니다.|  
|`useNagleAlgorithm`|서비스 지점 관리자에 의해 제어 되는 연결에 Nagle 알고리즘을 사용 하는지 여부를 지정 합니다. 기본값은 `true`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
