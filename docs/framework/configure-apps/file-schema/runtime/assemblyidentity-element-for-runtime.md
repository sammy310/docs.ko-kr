---
title: <runtime>에 대한 <assemblyIdentity> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154311"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<어셈블리런타임 \<> 대한 어셈블리ID> 요소
어셈블리에 대한 식별 정보를 포함합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<어셈블리바인딩>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<종속어셈블리>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<어셈블리정체성>**  
  
## <a name="syntax"></a>구문  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 어셈블리의 이름|  
|`culture`|선택적 특성입니다.<br /><br /> 어셈블리의 언어 및 국가/지역을 지정하는 문자열입니다.|  
|`publicKeyToken`|선택적 특성입니다.<br /><br /> 어셈블리의 강력한 이름을 지정하는 육각형 값입니다.|  
|`processorArchitecture`|선택적 특성입니다.<br /><br /> 프로세서 별 코드를 포함하는 어셈블리의 프로세서 아키텍처를 지정하는 값 "x86", "amd64", "msil" 또는 "ia64"의 값 중 하나입니다. 값은 대/소문자를 구분하지 않습니다. 특성에 다른 값이 할당되면 전체 `<assemblyIdentity>` 요소가 무시됩니다. <xref:System.Reflection.ProcessorArchitecture>을 참조하세요.|  
  
## <a name="processorarchitecture-attribute"></a>프로세서아키텍처 속성  
  
|값|Description|  
|-----------|-----------------|  
|`amd64`|AMD x86-64 아키텍처전용입니다.|  
|`ia64`|인텔 이타늄 아키텍처만.|  
|`msil`|프로세서 및 워드 당 비트에 대해 중립적입니다.|  
|`x86`|64비트 플랫폼의 기본 또는 Windows(WOW) 환경에서 32비트 x86 프로세서입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`dependentAssembly`|각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다. 각 `<dependentAssembly>` 어셈블리에 대해 하나의 요소를 사용합니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 모든 ** \<종속어셈블리>** 요소에는 하나의 ** \<어셈블리가** 있어야 id>자식 요소입니다.  
  
 특성이 `processorArchitecture` 있는 경우 `<assemblyIdentity>` 요소는 해당 프로세서 아키텍처가 있는 어셈블리에만 적용됩니다. 특성이 `processorArchitecture` 없는 경우 `<assemblyIdentity>` 요소는 프로세서 아키텍처가 있는 어셈블리에 적용할 수 있습니다.  
  
 다음 예제에서는 두 개의 서로 다른 두 프로세서 아키텍처를 대상으로 하는 이름이 같은 두 어셈블리에 대한 구성 파일과 동기화된 버전이 유지되지 않은 구성 파일을 보여 주십니다. 응용 프로그램이 x86 플랫폼에서 실행되면 `<assemblyIdentity>` 첫 번째 요소가 적용되고 다른 요소는 무시됩니다. 응용 프로그램이 x86 또는 ia64 이외의 플랫폼에서 실행되는 경우 둘 다 무시됩니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 구성 파일에 특성이 `<assemblyIdentity>` 없는 `processorArchitecture` 요소가 포함되어 있고 플랫폼과 일치하는 요소가 없는 경우 `processorArchitecture` 특성이 없는 요소가 사용됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리에 대한 정보를 제공하는 방법을 보여 주며 있습니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [어셈블리 버전 리디렉션](../../redirect-assembly-versions.md)
