---
title: <bypassTrustedAppStrongNames> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674209"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames> 요소
완전 신뢰에 로드 되는 완전 신뢰 어셈블리에 강력한 이름의 유효성 검사를 건너뛸지 여부를 지정 <xref:System.AppDomain>합니다.  
  
 \<configuration>  
\<runtime>  
\<bypassTrustedAppStrongNames>  
  
## <a name="syntax"></a>구문  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 완전 신뢰 어셈블리에 대 한 강력한 이름 유효성 검사를 건너뛰는 기능 사용 되는지 여부를 지정 합니다. 이 기능을 사용 하는 경우 강력한 이름 유효성이 검사 되지 않습니다 정확성에 대 한 어셈블리가 로드 되는 경우. 기본값은 `true`입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|완전 신뢰에는 어셈블리를 로드할 때 완전 신뢰 어셈블리에 강력한 이름 서명의 유효성이 검사 되지 않습니다 <xref:System.AppDomain>합니다. 이 값이 기본값입니다.|  
|`false`|완전 신뢰 어셈블리에 강력한 이름 서명의 유효성을 검사 완전 신뢰에는 어셈블리를 로드할 때 <xref:System.AppDomain>합니다. 강력한 이름 서명을 검사 하면 서명 정확성;에 대해서만 일치 하는 다른 강력한 이름으로는 비교 되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 강력한 이름 건너뛰기 기능 완전 신뢰 어셈블리의 강력한 이름 서명 확인 하는 오버 헤드를 방지할 수 있습니다.  
  
 건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.  
  
-   없이 완전 신뢰를 <xref:System.Security.Policy.StrongName> 증거 (예를 들어에 `MyComputer` 영역 증거가).  
  
-   완전히 신뢰할 수 있는 <xref:System.AppDomain>에 로드됨  
  
-   해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드됨  
  
-   서명이 연기되지 않음  
  
> [!NOTE]
>  건너뛰기 기능은 껐습니다 컴퓨터의 모든 응용 프로그램에 대 한 레지스트리 키를 사용 하 여,이 구성 파일 설정은 효과가 없습니다. 자세한 내용은 [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 완전 신뢰 어셈블리에 강력한 이름 서명의 유효성을 검사 하는 동작을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
