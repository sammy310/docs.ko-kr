---
title: <compiler> 요소
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 80eea3373e2f4b7e45ebeb31dd6552ea02c109e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659726"
---
# <a name="compiler-element"></a><span data-ttu-id="a0dce-102">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-102">\<compiler> Element</span></span>

<span data-ttu-id="a0dce-103">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="a0dce-104">\<configuration 요소 > \<system.object 요소 > \<컴파일러 요소 > \<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="a0dce-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0dce-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0dce-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-106">Attributes and Elements</span></span>

<span data-ttu-id="a0dce-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0dce-108">특성</span><span class="sxs-lookup"><span data-stu-id="a0dce-108">Attributes</span></span>

|<span data-ttu-id="a0dce-109">특성</span><span class="sxs-lookup"><span data-stu-id="a0dce-109">Attribute</span></span>|<span data-ttu-id="a0dce-110">설명</span><span class="sxs-lookup"><span data-stu-id="a0dce-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="a0dce-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a0dce-112">컴파일에 사용할 추가 컴파일러 관련 인수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="a0dce-113">`compilerOptions` 특성 값은 일반적으로 컴파일러에 대 한 컴파일러 옵션 항목에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="a0dce-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a0dce-115">언어 공급자의 소스 파일에 사용 되는 파일 이름 확장명을 세미콜론으로 구분한 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="a0dce-116">예를 들어, ".cs"입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="a0dce-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="a0dce-118">언어 공급자에서 지 원하는 언어 이름의 세미콜론으로 구분 된 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="a0dce-119">예를 들어, "C#;cs;csharp"입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="a0dce-120">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="a0dce-121">공급자 구현이 들어 있는 어셈블리의 이름을 포함 한 언어 공급자의 형식 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="a0dce-122">형식 이름은 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 정의 된 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="a0dce-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a0dce-124">기본 컴파일러 경고 수준을;를 지정합니다. 컴파일 경고를 오류로 언어 공급자는 처리 수준을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a0dce-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-125">Child Elements</span></span>

|<span data-ttu-id="a0dce-126">요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-126">Element</span></span>|<span data-ttu-id="a0dce-127">설명</span><span class="sxs-lookup"><span data-stu-id="a0dce-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0dce-128">\<providerOption > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-128">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="a0dce-129">언어 공급자에 대 한 컴파일러 버전 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0dce-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-130">Parent Elements</span></span>

|<span data-ttu-id="a0dce-131">요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-131">Element</span></span>|<span data-ttu-id="a0dce-132">설명</span><span class="sxs-lookup"><span data-stu-id="a0dce-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0dce-133">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-133">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="a0dce-134">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="a0dce-135">\<system.object > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-135">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="a0dce-136">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="a0dce-137">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-137">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="a0dce-138">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 `<compiler>` 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0dce-139">설명</span><span class="sxs-lookup"><span data-stu-id="a0dce-139">Remarks</span></span>

<span data-ttu-id="a0dce-140">각 `<compiler>` 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="a0dce-141">공급자는 특정 언어 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 에 대 한 클래스를 확장 합니다 `<compiler>` . 요소는 언어 공급자에 대 한 컴파일러 및 코드 생성기 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="a0dce-142">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="a0dce-143">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="a0dce-144"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="a0dce-145">응용 프로그램 또는 웹 구성 파일의 컴파일러 요소는 컴퓨터 구성 파일의 설정을 보완 하거나 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="a0dce-146">동일한 언어 이름 또는 동일한 파일 확장명에 대해 둘 이상의 공급자 구현이 구성 된 경우 마지막 일치 구성은 해당 언어 이름 또는 파일 확장명에 대해 이전에 구성 된 모든 공급자를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="a0dce-147">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a0dce-147">Configuration File</span></span>

<span data-ttu-id="a0dce-148">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="a0dce-149">예제</span><span class="sxs-lookup"><span data-stu-id="a0dce-149">Example</span></span>

<span data-ttu-id="a0dce-150">다음 예제에서는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0dce-150">The following example illustrates a typical compiler configuration element:</span></span>

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
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a0dce-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0dce-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="a0dce-152">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a0dce-152">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a0dce-153">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="a0dce-153">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="a0dce-154">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="a0dce-154">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="a0dce-155">[컴파일에 대 한 컴파일러의 컴파일러 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a0dce-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
