---
title: <defaultFtpCachePolicy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088435"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>\<defaultFtpCachePolicy > 요소 (네트워크 설정)
FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<requestCaching >** ](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultFtpCachePolicy >**

## <a name="syntax"></a>구문  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`policyLevel`|FTP 캐싱 정책을 지정 합니다. 기본값은 `Default`여야 합니다.|  
  
## <a name="policylevel-attribute"></a>policyLevel 특성  
  
|값|설명|  
|-----------|-----------------|  
|`Default`|리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.|  
|`BypassCache`|서버에서 리소스를 반환 합니다.|  
|`CacheOnly`|콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.|  
|`CacheIfAvailable`|콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.|  
|`Revalidate`|캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되 고 호출자에 게 반환 됩니다.|  
|`Reload`|서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.|  
|`NoCacheNoStore`|캐시 된 리소스가 있으면 삭제 됩니다. 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.|  
|`Revalidate`|타임 스탬프가 서버의 리소스 타임 스탬프와 동일한 경우 캐시 된 리소스 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 표시 되며 캐시에 저장 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Requestcaching>](requestcaching-element-network-settings.md)|네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="example"></a>예제  
 다음 예에서는 `NoCacheNoStore`FTP 캐싱 정책을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [네트워크 설정 스키마](index.md)
