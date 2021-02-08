---
description: 다음에 대해 자세히 알아보세요. <tokenReplayDetection>
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a8a6b754a3282afe4f2932296b06b84c09fb6f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786540"
---
# \<tokenReplayDetection>

토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Type  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|사용|토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.|  
|expirationPeriod|<xref:System.TimeSpan>항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.  값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|서비스 수준 id 설정을 지정 합니다.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.|  
  
## <a name="remarks"></a>설명  

 요소는 요소 아래의 `<tokenReplayDetection>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` . 토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.  
  
 토큰 재생 캐시의 형식은 요소에 의해 지정 됩니다 [\<tokenReplayCache>](tokenreplaycache.md) .
