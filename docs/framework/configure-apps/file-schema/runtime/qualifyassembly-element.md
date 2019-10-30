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
ms.openlocfilehash: 17cfe9fc39d65f146beef5d02c701f5e3e2fbbe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115777"
---
# <a name="qualifyassembly-element"></a>\<B l y > 요소
부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md) \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<b l y >**  
  
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
|`partialName`|필수 특성입니다.<br /><br /> 코드에 표시 되는 어셈블리의 부분 이름을 지정 합니다.|  
|`fullName`|필수 특성입니다.<br /><br /> 전역 어셈블리 캐시에 표시 되는 어셈블리의 전체 이름을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>주의  
 부분 어셈블리 이름을 사용 하 여 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 호출 하면 공용 언어 런타임이 응용 프로그램 기본 디렉터리 에서만 어셈블리를 검색 합니다. 응용 프로그램 구성 파일의 **\<b l y >** 요소를 사용 하 여 전체 어셈블리 정보 (이름, 버전, 공개 키 토큰 및 문화권)를 제공 하 고 공용 언어 런타임에서 전역으로 어셈블리를 검색 합니다. 어셈블리 캐시.  
  
 **FullName** 특성에는 어셈블리 id의 네 가지 필드인 이름, 버전, 공개 키 토큰 및 문화권이 포함 되어야 합니다. **PartialName** 특성은 어셈블리를 부분적으로 참조 해야 합니다. 적어도 어셈블리의 텍스트 이름 (가장 일반적인 경우)을 지정 해야 하지만 버전, 공개 키 토큰 또는 문화권 (또는 4의 모든 조합)을 포함할 수도 있습니다. **PartialName** 은 호출에 지정 된 이름과 일치 해야 합니다. 예를 들어 `"math"`를 구성 파일에 **partialName** 특성으로 지정 하 고 코드에서 `Assembly.Load("math, Version=3.3.3.3")`를 호출할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 호출 `Assembly.Load("math")`를 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`으로 논리적으로 바꿉니다.  
  
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
  
## <a name="see-also"></a>참조

- [런타임 설정 스키마](index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../deployment/how-the-runtime-locates-assemblies.md)
- [부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
