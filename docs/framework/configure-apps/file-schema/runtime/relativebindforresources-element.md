---
title: <relativeBindForResources> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153908"
---
# <a name="relativebindforresources-element"></a>\<상대빈빈드포리소스> 요소
위성 어셈블리에 대한 프로브를 최적화합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<상대빈빈드포리소>**  
  
## <a name="syntax"></a>구문  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 공통 언어 런타임이 위성 어셈블리에 대한 프로브를 최적화하는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|런타임은 위성 어셈블리에 대한 프로브를 최적화하지 않습니다. 이것은 기본값입니다.|  
|`true`|런타임은 위성 어셈블리에 대한 프로브를 최적화합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 리소스 관리자는 리소스 패키징 및 배포 항목에 설명된 대로 [리소스를 조사합니다.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) 즉, Resource Manager가 특정 지역화된 버전의 리소스를 검색할 때 전역 어셈블리 캐시에서 보고, 응용 프로그램의 코드 베이스에서 문화권 별 폴더를 보고, 위성 어셈블리에 대한 Windows Installer를 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 쿼리하고, 이벤트를 발생시킬 수 있습니다. 이 `<relativeBindForResources>` 요소는 리소스 관리자가 위성 어셈블리를 조사하는 방식을 최적화합니다. 다음 조건에서 리소스를 검색할 때 성능을 향상시킬 수 있습니다.  
  
- 위성 어셈블리가 코드 어셈블리와 동일한 위치에 배포되는 경우 즉, 코드 어셈블리가 전역 어셈블리 캐시에 설치된 경우 위성 어셈블리도 설치해야 합니다. 코드 어셈블리가 응용 프로그램의 코드 베이스에 설치된 경우 위성 어셈블리도 코드 베이스의 문화권 특정 폴더에 설치해야 합니다.  
  
- Windows 설치 프로그램이 사용되지 않거나 위성 어셈블리의 온디맨드 설치에 거의 사용되지 않는 경우  
  
- 응용 프로그램 코드가 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 처리하지 않는 경우.  
  
 요소의 `enabled` 특성을 설정하여 `true` 위성 어셈블리에 대한 리소스 관리자의 프로브를 다음과 같이 최적화합니다. `<relativeBindForResources>`  
  
- 상위 코드 어셈블리의 위치를 사용하여 위성 어셈블리를 프로브합니다.  
  
- 위성 어셈블리에 대 한 Windows 설치 관리자를 쿼리 하지 않습니다.  
  
- <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 발생시키지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
