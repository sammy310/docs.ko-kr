---
title: <providerOption> 요소
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088668"
---
# <a name="provideroption-element"></a><span data-ttu-id="2e268-102">\<providerOption > 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-102">\<providerOption> Element</span></span>
<span data-ttu-id="2e268-103">언어 공급자에 대 한 컴파일러 버전 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="2e268-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e268-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e268-105">&nbsp;&nbsp;[ **\<** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e268-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="2e268-106">&nbsp;&nbsp;&nbsp;\<[**컴파일러**](compilers-element.md) > &nbsp;</span><span class="sxs-lookup"><span data-stu-id="2e268-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="2e268-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<컴파일러 >** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e268-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="2e268-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption >**</span><span class="sxs-lookup"><span data-stu-id="2e268-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2e268-109">구문</span><span class="sxs-lookup"><span data-stu-id="2e268-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e268-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e268-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e268-112">특성</span><span class="sxs-lookup"><span data-stu-id="2e268-112">Attributes</span></span>  
  
|<span data-ttu-id="2e268-113">특성</span><span class="sxs-lookup"><span data-stu-id="2e268-113">Attribute</span></span>|<span data-ttu-id="2e268-114">설명</span><span class="sxs-lookup"><span data-stu-id="2e268-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2e268-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="2e268-116">옵션의 이름을 지정 합니다. 예를 들면 "찾고 compilerversion"입니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="2e268-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="2e268-118">옵션의 값을 지정 합니다. 예를 들면 "v 3.5"입니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e268-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-119">Child Elements</span></span>  
 <span data-ttu-id="2e268-120">없음.</span><span class="sxs-lookup"><span data-stu-id="2e268-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e268-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2e268-122">요소</span><span class="sxs-lookup"><span data-stu-id="2e268-122">Element</span></span>|<span data-ttu-id="2e268-123">설명</span><span class="sxs-lookup"><span data-stu-id="2e268-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e268-124">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="2e268-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="2e268-126">\<system.object > 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="2e268-127">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="2e268-128">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="2e268-129">컴파일러 구성 요소에 대 한 컨테이너입니다. `<compiler>` 요소를 0 개 이상 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="2e268-130">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="2e268-131">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e268-132">주의</span><span class="sxs-lookup"><span data-stu-id="2e268-132">Remarks</span></span>  
 <span data-ttu-id="2e268-133">.NET Framework 버전 3.5에서 CodeDOM (코드 문서 개체 모델) 코드 공급자는 `<providerOption>` 요소를 사용 하 여 공급자별 옵션을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="2e268-134">.NET Framework 3.5에는 업데이트 된 .NET Framework 2.0 어셈블리가 포함 되어 있으며 새 버전 3.5 어셈블리에는 새 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="2e268-135">Microsoft C# 및 Visual Basic 코드 공급자는 .NET Framework 2.0 어셈블리에 포함 되어 있지만 버전 3.5 컴파일러를 지원 하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="2e268-136">기본적으로 업데이트 된 코드 공급자는 버전 2.0 컴파일러에 대 한 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="2e268-137">`<providerOption>` 요소를 사용 하 여 대상 컴파일러 버전을 3.5으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="2e268-138">이렇게 하려면 `name` 특성에 대해 "찾고 compilerversion"를 지정 하 고 `value` 특성에는 "v 3.5"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="2e268-139">버전 번호 앞에는 소문자 "v"가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="2e268-140">.NET Framework 2.0 Machine.config 또는 루트 web.config 파일에 `<providerOption>` 요소를 추가 하 여 버전 사양을 전역적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="2e268-141">Machine.config 파일에서 기본 컴파일러 버전을 3.5로 업데이트 하는 경우 응용 프로그램 구성 파일의 `<providerOption>` 요소를 사용 하 여 응용 프로그램 별로 다시 2.0로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="2e268-142">CodeDOM 코드 공급자 구현자는 <xref:System.Collections.Generic.IDictionary%602>형식의 `providerOptions` 매개 변수를 사용 하는 생성자를 제공 하 여 사용자 지정 옵션을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e268-143">예제</span><span class="sxs-lookup"><span data-stu-id="2e268-143">Example</span></span>  
 <span data-ttu-id="2e268-144">다음 예제에서는 C# 코드 공급자의 버전 3.5을 사용 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e268-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e268-145">참조</span><span class="sxs-lookup"><span data-stu-id="2e268-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="2e268-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2e268-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2e268-147">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="2e268-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="2e268-148">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="2e268-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="2e268-149">[컴파일에 대 한 컴파일러의 컴파일러 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e268-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
