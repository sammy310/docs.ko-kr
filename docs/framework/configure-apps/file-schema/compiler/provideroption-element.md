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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155403"
---
# <a name="provideroption-element"></a><span data-ttu-id="c0f17-102">\<providerOption> 요소</span><span class="sxs-lookup"><span data-stu-id="c0f17-102">\<providerOption> Element</span></span>
<span data-ttu-id="c0f17-103">언어 공급자에 대 한 컴파일러 버전 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="c0f17-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0f17-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0f17-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0f17-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c0f17-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0f17-107">특성</span><span class="sxs-lookup"><span data-stu-id="c0f17-107">Attributes</span></span>  
  
|<span data-ttu-id="c0f17-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c0f17-108">Attribute</span></span>|<span data-ttu-id="c0f17-109">Description</span><span class="sxs-lookup"><span data-stu-id="c0f17-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="c0f17-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c0f17-111">옵션의 이름을 지정 합니다. 예를 들면 "찾고 compilerversion"입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="c0f17-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="c0f17-113">옵션의 값을 지정 합니다. 예를 들면 "v 3.5"입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0f17-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0f17-114">Child Elements</span></span>  
 <span data-ttu-id="c0f17-115">없음</span><span class="sxs-lookup"><span data-stu-id="c0f17-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0f17-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0f17-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c0f17-117">요소</span><span class="sxs-lookup"><span data-stu-id="c0f17-117">Element</span></span>|<span data-ttu-id="c0f17-118">Description</span><span class="sxs-lookup"><span data-stu-id="c0f17-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0f17-119">\<configuration>요소인</span><span class="sxs-lookup"><span data-stu-id="c0f17-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="c0f17-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="c0f17-121">\<system.codedom>요소인</span><span class="sxs-lookup"><span data-stu-id="c0f17-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="c0f17-122">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="c0f17-123">\<compilers>요소인</span><span class="sxs-lookup"><span data-stu-id="c0f17-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="c0f17-124">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 `<compiler>` 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="c0f17-125">\<compiler>요소인</span><span class="sxs-lookup"><span data-stu-id="c0f17-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="c0f17-126">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f17-127">설명</span><span class="sxs-lookup"><span data-stu-id="c0f17-127">Remarks</span></span>  
 <span data-ttu-id="c0f17-128">.NET Framework 버전 3.5에서 CodeDOM (코드 문서 개체 모델) 코드 공급자는 요소를 사용 하 여 공급자별 옵션을 지원할 수 있습니다 `<providerOption>` .</span><span class="sxs-lookup"><span data-stu-id="c0f17-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="c0f17-129">.NET Framework 3.5에는 업데이트 된 .NET Framework 2.0 어셈블리가 포함 되어 있으며 새 버전 3.5 어셈블리에는 새 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="c0f17-130">Microsoft c # 및 Visual Basic 코드 공급자는 .NET Framework 2.0 어셈블리에 포함 되어 있지만 버전 3.5 컴파일러를 지원 하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="c0f17-131">기본적으로 업데이트 된 코드 공급자는 버전 2.0 컴파일러에 대 한 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="c0f17-132">요소를 사용 `<providerOption>` 하 여 대상 컴파일러 버전을 3.5으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="c0f17-133">이렇게 하려면 특성에 대해 "찾고 compilerversion"를 지정 하 `name` 고 특성에는 "v 3.5"를 지정 `value` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="c0f17-134">버전 번호 앞에는 소문자 "v"가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="c0f17-135">`<providerOption>`.NET Framework 2.0 machine.config 또는 루트 web.config 파일에 요소를 추가 하 여 버전 사양을 전역적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="c0f17-136">Machine.config 파일에서 기본 컴파일러 버전을 3.5로 업데이트 하는 경우 `<providerOption>` 응용 프로그램 구성 파일의 요소를 사용 하 여 응용 프로그램 별로 다시 2.0로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="c0f17-137">CodeDOM 코드 공급자 구현자는 형식의 매개 변수를 사용 하는 생성자를 제공 하 여 사용자 지정 옵션을 처리할 수 있습니다 `providerOptions` <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="c0f17-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f17-138">예제</span><span class="sxs-lookup"><span data-stu-id="c0f17-138">Example</span></span>  
 <span data-ttu-id="c0f17-139">다음 예제에서는 c # 코드 공급자의 버전 3.5을 사용 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0f17-140">참조</span><span class="sxs-lookup"><span data-stu-id="c0f17-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="c0f17-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c0f17-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c0f17-142">\<compilers>요소인</span><span class="sxs-lookup"><span data-stu-id="c0f17-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="c0f17-143">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="c0f17-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="c0f17-144">[compilation 요소의 compilers 요소에 대한 compiler 요소(ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c0f17-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
