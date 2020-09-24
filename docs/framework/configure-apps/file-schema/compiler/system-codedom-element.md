---
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
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149571"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="dec58-102">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="dec58-102">\<system.codedom> Element</span></span>

<span data-ttu-id="dec58-103">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="dec58-104">구문</span><span class="sxs-lookup"><span data-stu-id="dec58-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dec58-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dec58-105">Attributes and Elements</span></span>  

 <span data-ttu-id="dec58-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dec58-107">특성</span><span class="sxs-lookup"><span data-stu-id="dec58-107">Attributes</span></span>  

 <span data-ttu-id="dec58-108">없음</span><span class="sxs-lookup"><span data-stu-id="dec58-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dec58-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dec58-109">Child Elements</span></span>  
  
|<span data-ttu-id="dec58-110">요소</span><span class="sxs-lookup"><span data-stu-id="dec58-110">Element</span></span>|<span data-ttu-id="dec58-111">설명</span><span class="sxs-lookup"><span data-stu-id="dec58-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="dec58-112">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 [\<compiler>](compiler-element.md) 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dec58-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dec58-113">Parent Elements</span></span>  
  
|<span data-ttu-id="dec58-114">요소</span><span class="sxs-lookup"><span data-stu-id="dec58-114">Element</span></span>|<span data-ttu-id="dec58-115">설명</span><span class="sxs-lookup"><span data-stu-id="dec58-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="dec58-116">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dec58-117">설명</span><span class="sxs-lookup"><span data-stu-id="dec58-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="dec58-118">.NET Framework 버전 2.0</span><span class="sxs-lookup"><span data-stu-id="dec58-118">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="dec58-119">요소에는 [\<system.codedom>](system-codedom-element.md) 및와 같은 .NET Framework와 함께 설치 되는 기본 공급자 외에도 컴퓨터에 설치 된 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다 <xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="dec58-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="dec58-120">[\<compilers>](compilers-element.md)요소는 0 개 이상의 요소를 포함 [\<compiler>](compiler-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="dec58-121">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="dec58-122">개발자와 컴파일러 공급 업체는 새 구현에 대 한 구성 설정을 컴퓨터 구성 파일 (Machine.config)에 추가할 수 있습니다 <xref:System.CodeDom.Compiler.CodeDomProvider> .</span><span class="sxs-lookup"><span data-stu-id="dec58-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="dec58-123">메서드를 사용 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 하 여 컴퓨터의 컴파일러 구성 설정으로 식별 되는 기본 언어 공급자와 언어 공급자를 프로그래밍 방식으로 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dec58-124">.NET Framework 버전 1.0 및 1.1에서는 .NET Framework에서 제공 하는 기본 언어 공급자가 요소에서 식별 됩니다 [\<compilers>](compilers-element.md) .</span><span class="sxs-lookup"><span data-stu-id="dec58-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="dec58-125">.NET Framework 버전 2.0에서 기본 언어 공급자는 요소에서 식별 되지 [\<compilers>](compilers-element.md) 않지만 메서드를 사용 하 여 열거할 수 있습니다 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="dec58-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="dec58-126">.NET Framework 버전 1.0 및 1.1</span><span class="sxs-lookup"><span data-stu-id="dec58-126">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="dec58-127">요소에는 [\<system.codedom>](system-codedom-element.md) 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="dec58-128">[\<compilers>](compilers-element.md)요소는 0 개 이상의 요소를 포함 [\<compiler>](compiler-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="dec58-129">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="dec58-130">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="dec58-131">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="dec58-132"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="dec58-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="dec58-133">Configuration File</span></span>  

 <span data-ttu-id="dec58-134">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dec58-135">예제</span><span class="sxs-lookup"><span data-stu-id="dec58-135">Example</span></span>  

 <span data-ttu-id="dec58-136">다음 예제에서는 일반적인 컴파일러 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dec58-136">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dec58-137">참조</span><span class="sxs-lookup"><span data-stu-id="dec58-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="dec58-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="dec58-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dec58-139">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="dec58-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dec58-140">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="dec58-140">\<compiler> Element</span></span>](compiler-element.md)
