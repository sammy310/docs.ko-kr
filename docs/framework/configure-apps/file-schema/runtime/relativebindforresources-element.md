---
title: <relativeBindForResources> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98914f57c24dc51625564e266157731ff173337
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704572"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources > 요소
위성 어셈블리에 대한 프로브를 최적화합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<relativeBindForResources > 요소  
  
## <a name="syntax"></a>구문  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 공용 언어 런타임은 위성 어셈블리에 대 한 프로브를 최적화 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임은 위성 어셈블리에 대 한 프로브를 최적화 되지 않습니다. 기본값입니다.|  
|`true`|런타임은 위성 어셈블리에 대 한 프로브를 최적화합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 에 설명 된 대로 Resource Manager 리소스에 대 한 프로브 일반적으로 [리소스 패키징 및 배포](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) 항목입니다. 즉, Resource Manager 리소스의 지역화 된 특정 버전에 대 한 검색을 하는 경우이 수 전역 어셈블리 캐시 확인, 위성 어셈블리를 검색할 Windows Installer 응용 프로그램의 코드 베이스를 쿼리의 문화권별 폴더에 발생 합니다 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다. `<relativeBindForResources>` 요소는 Resource Manager 위성 어셈블리에 대 한 검색 하는 방식을 최적화 합니다. 다음 조건에서 리소스를 검색 하는 경우에 성능 향상 시킬 수 있습니다.  
  
- 경우 위성 어셈블리는 코드 어셈블리와 동일한 위치에 배포 됩니다. 즉, 코드 어셈블리는 전역 어셈블리 캐시에 설치 하는 경우 위성 어셈블리를 설치 해야 합니다도 있습니다. 응용 프로그램의 코드 베이스에서 코드 어셈블리가 설치 되어 있으면 위성 어셈블리를 코드 베이스의 문화권별 폴더에도 설치 해야 합니다.  
  
- Windows Installer를 사용 하지 않거나 드물게 사용 되 면 요청 시 위성 어셈블리 설치에 대 한 합니다.  
  
- 응용 프로그램 코드를 처리 하지 않습니다 경우는 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다.  
  
 설정 합니다 `enabled` 특성을 `<relativeBindForResources>` 요소를 `true` 위성 어셈블리에 대 한 다음과 같은 Resource Manager의 프로브를 최적화:  
  
- 부모 코드 어셈블리의 위치를 사용 하 여 위성 어셈블리에 대 한 프로브.  
  
- 위성 어셈블리에 대 한 Windows Installer 쿼리하지 않습니다.  
  
- 발생 하지 않습니다는 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다.  
  
## <a name="see-also"></a>참고자료

- [리소스 패키징 및 배포](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
