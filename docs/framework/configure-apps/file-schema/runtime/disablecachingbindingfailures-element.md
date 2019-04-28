---
title: <disableCachingBindingFailures> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4893adaf528f1a9ef8fc8eab8027406fd8520cc2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704793"
---
# <a name="disablecachingbindingfailures-element"></a>\<disableCachingBindingFailures> Element
검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 비활성화할지 여부를 지정 합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<disableCachingBindingFailures>  
  
## <a name="syntax"></a>구문  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 비활성화할지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|0|검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 해제 하지 않습니다. 이.NET Framework 버전 2.0부터 기본 바인딩 동작입니다.|  
|1|검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 사용 하지 않도록 설정 합니다. 이 설정은.NET Framework 버전 1.1의 바인딩 동작으로 돌아갑니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 2.0부터 어셈블리 로드에 대 한 기본 동작 모든 바인딩 및 로드 실패를 캐시 하는 것입니다. 즉, 어셈블리를 로드 하려는 시도가 실패 하면 동일한 어셈블리를 로드 하는 후속 요청 즉시 없이 실패 어셈블리를 찾으려고 시도 합니다. 이 요소는 검색 경로에서 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패에 대 한 기본 동작을 해제 합니다. 이러한 오류를 throw <xref:System.IO.FileNotFoundException>합니다.  
  
 일부 바인딩 및 오류를 로드 합니다.이 요소에 의해 영향을 받지 않습니다 하 고 항상 캐시 된 합니다. 이러한 오류는 어셈블리를 찾았지만 로드할 수 없습니다 때문에 발생 합니다. Throw <xref:System.BadImageFormatException> 또는 <xref:System.IO.FileLoadException>합니다. 다음 목록은 이러한 오류의 몇 가지 예입니다.  
  
- 로드 하려는 파일이 유효한 어셈블리가 아닙니다 경우 올바른 어셈블리를 사용 하 여 잘못 된 파일은 대체 하는 경우에 어셈블리를 로드 하는 후속 하려고 하면 실패 합니다.  
  
- 파일 시스템에 의해 잠겨 있는 어셈블리를 로드 하려는 경우 파일 시스템에서 어셈블리를 해제 한 후에 이후에 어셈블리를 로드 하는 데 실패 합니다.  
  
- 하나 또는 여러 버전 로드 하려고 하는 어셈블리의 검색 경로 있지만 요청 하는 특정 버전 없는 그중에서 경우 올바른 버전 검색 경로로 이동 하는 경우에 이후에 해당 버전을 로드 하는 데 실패 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 어셈블리 바인딩 실패 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
