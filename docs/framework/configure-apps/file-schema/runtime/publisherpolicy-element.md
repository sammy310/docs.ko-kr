---
title: <publisherPolicy> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076291"
---
# <a name="publisherpolicy-element"></a>\<publisherPolicy > 요소
런타임이 게시자 정책을 적용할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<dependentAssembly>  
\<publisherPolicy>  
  
## <a name="syntax"></a>구문  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`apply`|게시자 정책을 적용할지 여부를 지정 합니다.|  
  
## <a name="apply-attribute"></a>특성 적용  
  
|값|설명|  
|-----------|-----------------|  
|`yes`|게시자 정책을 적용합니다. 이것이 기본 설정입니다.|  
|`no`|게시자 정책을 적용 되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 구성 요소 공급 업체는 새 버전의 어셈블리로 놓으면에 공급 업체 이제 이전 버전을 사용 하는 응용 프로그램이 새 버전을 사용 하므로 게시자 정책에 포함할 수 있습니다. 특정 어셈블리에 대 한 게시자 정책을 적용할지 여부를 지정 하려면 합니다  **\<publisherPolicy >** 요소에는  **\<dependentAssembly >** 요소입니다.  
  
 기본 설정을 합니다 **적용** 특성이 **예**합니다. 설정 합니다 **적용** 특성을 **없습니다** 모든 이전 재정의 **예** 어셈블리에 대 한 설정입니다.  
  
 명시적으로 사용 하 여 게시자 정책 무시 하려면 응용 프로그램에 권한이 필요 합니다 [ \<apply = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 응용 프로그램 구성 파일의 요소입니다. 설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> 플래그를 <xref:System.Security.Permissions.SecurityPermission>. 자세한 내용은 [어셈블리 바인딩 리디렉션 보안 권한](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리에 대 한 게시자 정책 해제 `myAssembly`합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
