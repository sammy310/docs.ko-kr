---
title: <qualifyAssembly> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109450"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly > 요소
부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<qualifyAssembly>  
  
## <a name="syntax"></a>구문  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`partialName`|필수 특성입니다.<br /><br /> 코드에 표시 된 대로 어셈블리의 부분 이름을 지정 합니다.|  
|`fullName`|필수 특성입니다.<br /><br /> 전역 어셈블리 캐시에 표시 된 대로 어셈블리의 전체 이름을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 호출 된 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 부분 어셈블리 이름을 사용 하는 메서드를 사용 하면 응용 프로그램 기본 디렉터리에만 어셈블리에 대 한 확인을 공용 언어 런타임. 사용 된  **\<qualifyAssembly >** (이름, 버전, 공개 키 토큰 및 문화권)에 전체 어셈블리 정보를 제공 하 여 검색 하려면 공용 언어 런타임이 응용 프로그램 구성 파일의 요소 전역 어셈블리 캐시에서 어셈블리입니다.  
  
 합니다 **fullName** 특성의 어셈블리 id는 4 개의 필드를 포함 해야 합니다: 이름, 버전, 공개 키 토큰 및 문화권입니다. 합니다 **partialName** 특성 어셈블리를 부분적으로 참조 해야 합니다. 어셈블리의 텍스트 이름 (가장 일반적인 경우)를 하나 이상 지정 해야 하지만 버전, 공개 키 토큰 또는 culture (또는 일부 4의 조합)을 포함할 수도 있습니다. 합니다 **partialName** 호출에 지정 된 이름과 일치 해야 합니다. 예를 들어 지정할 수 없습니다 `"math"` 으로 **partialName** 호출 프로그램과 구성 파일의 특성 `Assembly.Load("math, Version=3.3.3.3")` 코드에서.  
  
## <a name="example"></a>예제  
 다음 예제에서는 호출을 논리적으로 변환 `Assembly.Load("math")` 에 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`입니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
