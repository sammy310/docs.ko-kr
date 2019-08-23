---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 7d868d84318db8c9fe188293154dc275060a3952
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933178"
---
# <a name="netpipe"></a>\<net.pipe>
명명된 파이프 연결의 수명을 관리하고 명명된 파이프을 통해 수신되는 활성화 요청을 처리하는 Named Pipe Activation Service의 구성 설정을 지정합니다.  
  
 \<system.serviceModel.activation>  
\<net.pipe>  
  
## <a name="syntax"></a>구문  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|Description|  
|---------------|-----------------|  
|`maxPendingAccepts`|공유 서비스에 대한 수신 엔드포인트에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다. 기본값은 2입니다.|  
|`maxPendingConnections`|디스패치를 대기할 수 있는 최대 연결 수를 지정하는 정수입니다. 기본값은 100입니다.|  
|`receiveTimeout`|프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 "00:00:10"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|WCF 서비스를 호스팅하고 공유 서비스에 대 `securityIdentifier` 한 연결 액세스 권한이 부여 된 프로세스의 사용자 계정을 지정 하는 특성을 포함 하는 구성 요소 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
