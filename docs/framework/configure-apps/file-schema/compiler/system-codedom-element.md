---
description: 자세한 내용은 <> 요소를 확인 하세요.
title: <system.codedom> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 4761f971255b8ff7d60edfb8d9f5789c2e545aef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699014"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="7958a-103">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="7958a-103">\<system.codedom> Element</span></span>

<span data-ttu-id="7958a-104">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-104">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="7958a-105">구문</span><span class="sxs-lookup"><span data-stu-id="7958a-105">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7958a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7958a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7958a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7958a-108">특성</span><span class="sxs-lookup"><span data-stu-id="7958a-108">Attributes</span></span>  

 <span data-ttu-id="7958a-109">없음</span><span class="sxs-lookup"><span data-stu-id="7958a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7958a-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7958a-110">Child Elements</span></span>  
  
|<span data-ttu-id="7958a-111">요소</span><span class="sxs-lookup"><span data-stu-id="7958a-111">Element</span></span>|<span data-ttu-id="7958a-112">설명</span><span class="sxs-lookup"><span data-stu-id="7958a-112">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="7958a-113">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 [\<compiler>](compiler-element.md) 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-113">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7958a-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7958a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7958a-115">요소</span><span class="sxs-lookup"><span data-stu-id="7958a-115">Element</span></span>|<span data-ttu-id="7958a-116">설명</span><span class="sxs-lookup"><span data-stu-id="7958a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="7958a-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7958a-118">설명</span><span class="sxs-lookup"><span data-stu-id="7958a-118">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="7958a-119">.NET Framework 버전 2.0</span><span class="sxs-lookup"><span data-stu-id="7958a-119">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="7958a-120">요소에는 [\<system.codedom>](system-codedom-element.md) 및와 같은 .NET Framework와 함께 설치 되는 기본 공급자 외에도 컴퓨터에 설치 된 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다 <xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="7958a-120">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="7958a-121">[\<compilers>](compilers-element.md)요소는 0 개 이상의 요소를 포함 [\<compiler>](compiler-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-121">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="7958a-122">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-122">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="7958a-123">개발자와 컴파일러 공급 업체는 새 구현에 대 한 구성 설정을 컴퓨터 구성 파일 (Machine.config)에 추가할 수 있습니다 <xref:System.CodeDom.Compiler.CodeDomProvider> .</span><span class="sxs-lookup"><span data-stu-id="7958a-123">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="7958a-124">메서드를 사용 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 하 여 컴퓨터의 컴파일러 구성 설정으로 식별 되는 기본 언어 공급자와 언어 공급자를 프로그래밍 방식으로 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-124">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7958a-125">.NET Framework 버전 1.0 및 1.1에서는 .NET Framework에서 제공 하는 기본 언어 공급자가 요소에서 식별 됩니다 [\<compilers>](compilers-element.md) .</span><span class="sxs-lookup"><span data-stu-id="7958a-125">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="7958a-126">.NET Framework 버전 2.0에서 기본 언어 공급자는 요소에서 식별 되지 [\<compilers>](compilers-element.md) 않지만 메서드를 사용 하 여 열거할 수 있습니다 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="7958a-126">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="7958a-127">.NET Framework 버전 1.0 및 1.1</span><span class="sxs-lookup"><span data-stu-id="7958a-127">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="7958a-128">요소에는 [\<system.codedom>](system-codedom-element.md) 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-128">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="7958a-129">[\<compilers>](compilers-element.md)요소는 0 개 이상의 요소를 포함 [\<compiler>](compiler-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-129">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="7958a-130">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-130">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="7958a-131">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-131">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="7958a-132">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-132">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="7958a-133"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-133">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="7958a-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="7958a-134">Configuration File</span></span>  

 <span data-ttu-id="7958a-135">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-135">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7958a-136">예제</span><span class="sxs-lookup"><span data-stu-id="7958a-136">Example</span></span>  

 <span data-ttu-id="7958a-137">다음 예제에서는 일반적인 컴파일러 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7958a-137">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7958a-138">참조</span><span class="sxs-lookup"><span data-stu-id="7958a-138">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="7958a-139">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7958a-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7958a-140">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7958a-140">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7958a-141">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="7958a-141">\<compiler> Element</span></span>](compiler-element.md)
