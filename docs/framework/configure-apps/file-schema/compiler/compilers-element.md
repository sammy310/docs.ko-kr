---
description: '다음에 대 한 자세한 정보: <compilers> 요소'
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
ms.openlocfilehash: 6ced6bc81bc7d829ccebab50e0a361985c970f5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699170"
---
# <a name="compilers-element"></a><span data-ttu-id="f22cc-103">\<compilers> 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-103">\<compilers> Element</span></span>

<span data-ttu-id="f22cc-104">컴파일러 구성 요소에 대 한 컨테이너입니다. 0 개 이상의 [\<compiler>](compiler-element.md) 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-104">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="f22cc-105">구문</span><span class="sxs-lookup"><span data-stu-id="f22cc-105">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f22cc-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f22cc-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f22cc-108">특성</span><span class="sxs-lookup"><span data-stu-id="f22cc-108">Attributes</span></span>  

 <span data-ttu-id="f22cc-109">없음</span><span class="sxs-lookup"><span data-stu-id="f22cc-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f22cc-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-110">Child Elements</span></span>  
  
|<span data-ttu-id="f22cc-111">요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-111">Element</span></span>|<span data-ttu-id="f22cc-112">설명</span><span class="sxs-lookup"><span data-stu-id="f22cc-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f22cc-113">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-113">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="f22cc-114">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-114">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f22cc-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f22cc-116">요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-116">Element</span></span>|<span data-ttu-id="f22cc-117">설명</span><span class="sxs-lookup"><span data-stu-id="f22cc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f22cc-118">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-118">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="f22cc-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="f22cc-120">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-120">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="f22cc-121">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-121">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f22cc-122">설명</span><span class="sxs-lookup"><span data-stu-id="f22cc-122">Remarks</span></span>  

 <span data-ttu-id="f22cc-123">요소에는 [\<compilers>](compilers-element.md) 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-123">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="f22cc-124">각 [\<compiler>](compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-124">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="f22cc-125">.NET Framework은 컴퓨터 구성 파일 (Machine.config)에서 초기 컴파일러 및 언어 공급자 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-125">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="f22cc-126">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-126">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="f22cc-127"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f22cc-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f22cc-128">Configuration File</span></span>  

 <span data-ttu-id="f22cc-129">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-129">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f22cc-130">예제</span><span class="sxs-lookup"><span data-stu-id="f22cc-130">Example</span></span>  

 <span data-ttu-id="f22cc-131">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f22cc-131">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f22cc-132">참조</span><span class="sxs-lookup"><span data-stu-id="f22cc-132">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="f22cc-133">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f22cc-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f22cc-134">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f22cc-134">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f22cc-135">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="f22cc-135">\<compiler> Element</span></span>](compiler-element.md)
