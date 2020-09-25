---
title: <compilers> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 1aa096e185ae7f5957f173c03e221a31f30d5200
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172946"
---
# <a name="compilers-element"></a><span data-ttu-id="74b14-102">\<compilers> 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-102">\<compilers> Element</span></span>

<span data-ttu-id="74b14-103">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 [\<compiler>](compiler-element.md) 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="74b14-104">구문</span><span class="sxs-lookup"><span data-stu-id="74b14-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74b14-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-105">Attributes and Elements</span></span>  

 <span data-ttu-id="74b14-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74b14-107">특성</span><span class="sxs-lookup"><span data-stu-id="74b14-107">Attributes</span></span>  

 <span data-ttu-id="74b14-108">없음</span><span class="sxs-lookup"><span data-stu-id="74b14-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74b14-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-109">Child Elements</span></span>  
  
|<span data-ttu-id="74b14-110">요소</span><span class="sxs-lookup"><span data-stu-id="74b14-110">Element</span></span>|<span data-ttu-id="74b14-111">설명</span><span class="sxs-lookup"><span data-stu-id="74b14-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74b14-112">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="74b14-113">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74b14-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-114">Parent Elements</span></span>  
  
|<span data-ttu-id="74b14-115">요소</span><span class="sxs-lookup"><span data-stu-id="74b14-115">Element</span></span>|<span data-ttu-id="74b14-116">설명</span><span class="sxs-lookup"><span data-stu-id="74b14-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74b14-117">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="74b14-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="74b14-119">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="74b14-120">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74b14-121">설명</span><span class="sxs-lookup"><span data-stu-id="74b14-121">Remarks</span></span>  

 <span data-ttu-id="74b14-122">요소에는 [\<compilers>](compilers-element.md) 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="74b14-123">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="74b14-124">.NET Framework은 컴퓨터 구성 파일 (Machine.config)에서 초기 컴파일러 및 언어 공급자 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="74b14-125">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="74b14-126"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="74b14-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="74b14-127">Configuration File</span></span>  

 <span data-ttu-id="74b14-128">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74b14-129">예제</span><span class="sxs-lookup"><span data-stu-id="74b14-129">Example</span></span>  

 <span data-ttu-id="74b14-130">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74b14-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler
          language="c#;cs;csharp"
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74b14-131">참조</span><span class="sxs-lookup"><span data-stu-id="74b14-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="74b14-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="74b14-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="74b14-133">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="74b14-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="74b14-134">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="74b14-134">\<compiler> Element</span></span>](compiler-element.md)
