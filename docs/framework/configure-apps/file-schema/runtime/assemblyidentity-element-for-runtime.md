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
ms.openlocfilehash: d5766b76f18dce441cb260887a753dcf64642a6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674235"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<assemblyIdentity > 요소에 대 한 \<런타임 >
어셈블리에 대 한 식별 정보를 포함합니다.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<dependentAssembly>  
\<assemblyIdentity>  
  
## <a name="syntax"></a>구문  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 어셈블리의 이름|  
|`culture`|선택적 특성입니다.<br /><br /> 언어 및 국가/지역을 어셈블리를 지정 하는 문자열입니다.|  
|`publicKeyToken`|선택적 특성입니다.<br /><br /> 어셈블리의 강력한 이름을 지정 하는 16 진수 값입니다.|  
|`processorArchitecture`|선택적 특성입니다.<br /><br /> 중 값 "x86", "amd64", "msil" 또는 "ia64" 프로세서 특정 코드로 포함 된 어셈블리에 대 한 프로세서 아키텍처를 지정 합니다. 값은 대/소문자 구분 하지 않습니다. 특성에 다른 값을 전체 할당 된 경우 `<assemblyIdentity>` 요소는 무시 됩니다. <xref:System.Reflection.ProcessorArchitecture>을 참조하세요.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture 특성  
  
|값|설명|  
|-----------|-----------------|  
|`amd64`|AMD 64 x86 아키텍처에만 해당 합니다.|  
|`ia64`|Intel Itanium 아키텍처에만 해당 합니다.|  
|`msil`|프로세서 및 워드 당 비트에 대해 중립적입니다.|  
|`x86`|32 비트 x86 프로세서, 네이티브 또는 64 비트 플랫폼에서 Windows (WOW) 환경에서 Windows에서.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`dependentAssembly`|각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다. 하나를 사용 하 여 `<dependentAssembly>` 각 어셈블리에 대 한 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 모든  **\<dependentAssembly >** 요소가 하나 있어야  **\<assemblyIdentity >** 자식 요소입니다.  
  
 경우는 `processorArchitecture` 특성이 있는 경우는 `<assemblyIdentity>` 요소 해당 프로세서 아키텍처를 사용 하 여 어셈블리에만 적용 됩니다. 경우는 `processorArchitecture` 특성이 있는 `<assemblyIdentity>` 요소 모든 프로세서 아키텍처를 사용 하 여 어셈블리에 적용할 수 있습니다.  
  
 다음 예제에서는 두 개의 서로 다른 두 프로세서 아키텍처를 대상으로 하 고 버전이 유지 하지 동기화 같은 이름의 두 어셈블리에 대 한 구성 파일을 보여 줍니다. X86 응용 프로그램을 실행 하는 경우 첫 번째 플랫폼 `<assemblyIdentity>` 요소 적용 하 고 나머지는 무시 합니다. 응용 프로그램 이외의 x86 또는 ia64 플랫폼에서 실행 하는 경우 모두 무시 됩니다.  
  
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
  
 구성 파일을 포함 하는 경우는 `<assemblyIdentity>` 없는 요소에 `processorArchitecture` 특성을 포함 하 고 있지는 플랫폼에 없는 요소를 일치 하는 요소는 `processorArchitecture` 특성을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리에 대 한 정보를 제공 하는 방법을 보여 줍니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
