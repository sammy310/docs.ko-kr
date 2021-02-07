---
description: '다음에 대 한 자세한 정보: <providerOption> 요소'
title: <providerOption> 요소
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 1fdca58830e8563ef28cbca28857127252928fd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699040"
---
# <a name="provideroption-element"></a>\<providerOption> 요소

언어 공급자에 대 한 컴파일러 버전 특성을 지정 합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a>구문  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 옵션의 이름을 지정 합니다. 예를 들면 "찾고 compilerversion"입니다.|  
|`value`|필수 특성입니다.<br /><br /> 옵션의 값을 지정 합니다. 예를 들면 "v 3.5"입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<configuration> 요소](../configuration-element.md)|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|[\<system.codedom> 요소](system-codedom-element.md)|사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.|  
|[\<compilers> 요소](compilers-element.md)|컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 `<compiler>` 요소를 포함 합니다.|  
|[\<compiler> 요소](compiler-element.md)|언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.|  
  
## <a name="remarks"></a>설명  

 .NET Framework 버전 3.5에서 CodeDOM (코드 문서 개체 모델) 코드 공급자는 요소를 사용 하 여 공급자별 옵션을 지원할 수 있습니다 `<providerOption>` .  
  
 .NET Framework 3.5에는 업데이트 된 .NET Framework 2.0 어셈블리가 포함 되어 있으며 새 버전 3.5 어셈블리에는 새 형식이 포함 되어 있습니다. Microsoft c # 및 Visual Basic 코드 공급자는 .NET Framework 2.0 어셈블리에 포함 되어 있지만 버전 3.5 컴파일러를 지원 하도록 업데이트 되었습니다. 기본적으로 업데이트 된 코드 공급자는 버전 2.0 컴파일러에 대 한 코드를 생성 합니다. 요소를 사용 `<providerOption>` 하 여 대상 컴파일러 버전을 3.5으로 변경할 수 있습니다. 이렇게 하려면 특성에 대해 "찾고 compilerversion"를 지정 하 `name` 고 특성에는 "v 3.5"를 지정 `value` 합니다. 버전 번호 앞에는 소문자 "v"가와 야 합니다.  
  
 `<providerOption>`.NET Framework 2.0 Machine.config 또는 루트 Web.config 파일에 요소를 추가 하 여 버전 사양을 전역적으로 지정할 수 있습니다. Machine.config 파일에서 기본 컴파일러 버전을 3.5로 업데이트 하는 경우 `<providerOption>` 응용 프로그램 구성 파일의 요소를 사용 하 여 응용 프로그램 별로 2.0로 다시 변경할 수 있습니다.  
  
 CodeDOM 코드 공급자 구현자는 형식의 매개 변수를 사용 하는 생성자를 제공 하 여 사용자 지정 옵션을 처리할 수 있습니다 `providerOptions` <xref:System.Collections.Generic.IDictionary%602> .  
  
## <a name="example"></a>예제  

 다음 예제에서는 c # 코드 공급자의 버전 3.5을 사용 하도록 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [구성 파일 스키마](../index.md)
- [\<compilers> 요소](compilers-element.md)
- [정규화된 형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [compilation 요소의 compilers 요소에 대한 compiler 요소(ASP.NET 설정 스키마)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
