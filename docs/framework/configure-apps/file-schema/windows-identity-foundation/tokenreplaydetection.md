---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944292"
---
# <a name="tokenreplaydetection"></a>\<tokenReplayDetection>
토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<tokenReplayDetection>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>형식  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.|  
|expirationPeriod|항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.<xref:System.TimeSpan>  값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|서비스 수준 id 설정을 지정 합니다.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<tokenReplayDetection>` 토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.  
  
 토큰 재생 캐시의 유형은 [ \<tokenreplaycache >](tokenreplaycache.md) 요소에 의해 지정 됩니다.
