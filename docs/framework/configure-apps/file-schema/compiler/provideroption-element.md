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
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155403"
---
# <a name="provideroption-element"></a><span data-ttu-id="7477b-102">\<공급자옵션> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-102">\<providerOption> Element</span></span>
<span data-ttu-id="7477b-103">언어 공급자에 대한 컴파일러 버전 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="7477b-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7477b-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="7477b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<컴파일러>**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="7477b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<컴파일러>**](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="7477b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<공급자옵션>**</span><span class="sxs-lookup"><span data-stu-id="7477b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7477b-109">구문</span><span class="sxs-lookup"><span data-stu-id="7477b-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7477b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7477b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7477b-112">특성</span><span class="sxs-lookup"><span data-stu-id="7477b-112">Attributes</span></span>  
  
|<span data-ttu-id="7477b-113">attribute</span><span class="sxs-lookup"><span data-stu-id="7477b-113">Attribute</span></span>|<span data-ttu-id="7477b-114">Description</span><span class="sxs-lookup"><span data-stu-id="7477b-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7477b-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="7477b-116">옵션의 이름을 지정합니다. 예를 들어,"컴파일러버전".</span><span class="sxs-lookup"><span data-stu-id="7477b-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="7477b-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="7477b-118">옵션의 값을 지정합니다. 예를 들어 "v3.5"입니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7477b-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-119">Child Elements</span></span>  
 <span data-ttu-id="7477b-120">없음</span><span class="sxs-lookup"><span data-stu-id="7477b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7477b-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7477b-122">요소</span><span class="sxs-lookup"><span data-stu-id="7477b-122">Element</span></span>|<span data-ttu-id="7477b-123">Description</span><span class="sxs-lookup"><span data-stu-id="7477b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7477b-124">\<구성> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="7477b-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="7477b-126">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="7477b-127">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="7477b-128">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="7477b-129">컴파일러 구성 요소에 대한 컨테이너; 에는 0 `<compiler>` 개 이상의 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="7477b-130">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="7477b-131">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7477b-132">설명</span><span class="sxs-lookup"><span data-stu-id="7477b-132">Remarks</span></span>  
 <span data-ttu-id="7477b-133">.NET Framework 버전 3.5에서 코드 문서 개체 모델(CodeDOM) 코드 공급자는 `<providerOption>` 요소를 사용하여 공급자별 옵션을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="7477b-134">.NET Framework 3.5에는 업데이트된 .NET Framework 2.0 어셈블리가 포함되어 있으며 새 형식이 포함된 새 버전 3.5 어셈블리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="7477b-135">Microsoft C# 및 Visual Basic 코드 공급자는 .NET Framework 2.0 어셈블리에 포함되어 있지만 버전 3.5 컴파일러를 지원하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="7477b-136">기본적으로 업데이트된 코드 공급자는 버전 2.0 컴파일러에 대한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="7477b-137">`<providerOption>` 요소를 사용하여 대상 컴파일러 버전을 3.5로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="7477b-138">이렇게 하려면 특성에 대해 "컴파일러버전"을 지정하고 특성에 `name` `value` 대해 "v3.5"를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="7477b-139">소문자 "v"가 있는 버전 번호 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="7477b-140">.NET Framework 2.0 Machine.config 또는 root Web.config 파일에 `<providerOption>` 요소를 추가하여 버전 사양을 전역으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="7477b-141">Machine.config 파일에서 기본 컴파일러 버전을 3.5로 업데이트하는 경우 응용 프로그램 구성 파일의 `<providerOption>` 요소를 사용하여 응용 프로그램별로 2.0으로 다시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="7477b-142">CodeDOM 코드 공급자 구현자는 형식의 `providerOptions` <xref:System.Collections.Generic.IDictionary%602>매개 변수를 사용하는 생성자를 제공하여 사용자 지정 옵션을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7477b-143">예제</span><span class="sxs-lookup"><span data-stu-id="7477b-143">Example</span></span>  
 <span data-ttu-id="7477b-144">다음 예제에서는 C# 코드 공급자의 버전 3.5를 사용해야 하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7477b-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7477b-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7477b-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="7477b-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7477b-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7477b-147">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="7477b-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="7477b-148">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="7477b-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="7477b-149">[compilation 요소의 compilers 요소에 대한 compiler 요소(ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7477b-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
