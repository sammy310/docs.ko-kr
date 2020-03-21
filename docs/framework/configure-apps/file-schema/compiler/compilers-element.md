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
ms.openlocfilehash: 09b1efe321c39402c9280eda0e9def9112462470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155416"
---
# <a name="compilers-element"></a><span data-ttu-id="fa40f-102">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-102">\<compilers> Element</span></span>
<span data-ttu-id="fa40f-103">컴파일러 구성 요소에 대한 컨테이너; 에는 0 개 이상의 [ \<컴파일러>](compiler-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

<span data-ttu-id="fa40f-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa40f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa40f-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa40f-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="fa40f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<컴파일러>**</span><span class="sxs-lookup"><span data-stu-id="fa40f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fa40f-107">구문</span><span class="sxs-lookup"><span data-stu-id="fa40f-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa40f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fa40f-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa40f-110">특성</span><span class="sxs-lookup"><span data-stu-id="fa40f-110">Attributes</span></span>  
 <span data-ttu-id="fa40f-111">없음</span><span class="sxs-lookup"><span data-stu-id="fa40f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa40f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-112">Child Elements</span></span>  
  
|<span data-ttu-id="fa40f-113">요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-113">Element</span></span>|<span data-ttu-id="fa40f-114">Description</span><span class="sxs-lookup"><span data-stu-id="fa40f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa40f-115">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-115">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="fa40f-116">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa40f-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fa40f-118">요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-118">Element</span></span>|<span data-ttu-id="fa40f-119">Description</span><span class="sxs-lookup"><span data-stu-id="fa40f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa40f-120">\<구성> 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="fa40f-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="fa40f-122">\<system.codedom> 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="fa40f-123">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa40f-124">설명</span><span class="sxs-lookup"><span data-stu-id="fa40f-124">Remarks</span></span>  
 <span data-ttu-id="fa40f-125">[ \<컴파일러>](compilers-element.md) 요소에는 컴퓨터의 언어 공급자에 대한 컴파일러 구성 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="fa40f-126">각 [ \<컴파일러>](compiler-element.md) 요소는 특정 언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="fa40f-127">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 및 언어 공급자 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="fa40f-128">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="fa40f-129"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="fa40f-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="fa40f-130">Configuration File</span></span>  
 <span data-ttu-id="fa40f-131">이 요소는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa40f-132">예제</span><span class="sxs-lookup"><span data-stu-id="fa40f-132">Example</span></span>  
 <span data-ttu-id="fa40f-133">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa40f-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa40f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa40f-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="fa40f-135">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fa40f-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fa40f-136">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fa40f-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fa40f-137">\<컴파일러> 요소</span><span class="sxs-lookup"><span data-stu-id="fa40f-137">\<compiler> Element</span></span>](compiler-element.md)
