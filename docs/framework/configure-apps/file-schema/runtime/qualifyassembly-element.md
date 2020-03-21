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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153921"
---
# <a name="qualifyassembly-element"></a>\<검증어셈블리> 요소
부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<어셈블리바인딩>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<자격 어셈블리>**  
  
## <a name="syntax"></a>구문  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`partialName`|필수 특성입니다.<br /><br /> 코드에 나타나는 어셈블리의 부분 이름을 지정합니다.|  
|`fullName`|필수 특성입니다.<br /><br /> 전역 어셈블리 캐시에 나타나는 어셈블리의 전체 이름을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부분 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 어셈블리 이름을 사용하여 메서드를 호출하면 공통 언어 런타임이 응용 프로그램 기본 디렉터리에서만 어셈블리를 찾습니다. 응용 프로그램 구성 파일에서 ** \<qualifyAssembly>** 요소를 사용하여 전체 어셈블리 정보(이름, 버전, 공개 키 토큰 및 문화권)를 제공하고 공통 언어 런타임이 전역 어셈블리 캐시에서 어셈블리를 검색하도록 합니다.  
  
 **fullName** 특성에는 이름, 버전, 공개 키 토큰 및 문화권이라는 어셈블리 ID의 네 가지 필드가 포함되어야 합니다. **partialName** 특성은 어셈블리를 부분적으로 참조해야 합니다. 어셈블리의 텍스트 이름(가장 일반적인 경우)을 최소한 지정해야 하지만 버전, 공개 키 토큰 또는 문화권(또는 4개 모두 의 조합)을 포함할 수도 있습니다. **partialName은** 호출에 지정된 이름과 일치해야 합니다. 예를 들어 구성 `"math"` 파일에서 **partialName** 특성으로 지정하고 `Assembly.Load("math, Version=3.3.3.3")` 코드에서 호출할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 논리적으로 `Assembly.Load("math")` 호출을 로 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`바꿉니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [런타임에서 어셈블리를 찾는 방법](../../../deployment/how-the-runtime-locates-assemblies.md)
- [부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
