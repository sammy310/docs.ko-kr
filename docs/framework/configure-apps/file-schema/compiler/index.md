---
title: 컴파일러 및 언어 공급자 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: fe08ac5dc0600e0861bb349ce99875af8658eb4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187449"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="bcb08-102">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bcb08-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="bcb08-103">컴파일러 및 언어 공급자 설정은 사용 가능한 언어 공급자에 대한 컴파일러 구성 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="bcb08-104">각 컴파일러 구성 요소는 코드 공급자 형식 이름, 컴파일러 매개 변수, 지원되는 언어 이름 및 지원되는 파일 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
 <span data-ttu-id="bcb08-105">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="bcb08-106">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="bcb08-107"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 [<span data-ttu-id="bcb08-108">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="bcb08-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="bcb08-109">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="bcb08-109">\<system.codedom></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [<span data-ttu-id="bcb08-110">\<compilers></span><span class="sxs-lookup"><span data-stu-id="bcb08-110">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [<span data-ttu-id="bcb08-111">\<compiler></span><span class="sxs-lookup"><span data-stu-id="bcb08-111">\<compiler></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|<span data-ttu-id="bcb08-112">요소</span><span class="sxs-lookup"><span data-stu-id="bcb08-112">Element</span></span>|<span data-ttu-id="bcb08-113">설명</span><span class="sxs-lookup"><span data-stu-id="bcb08-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcb08-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="bcb08-114">\<system.codedom></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="bcb08-115">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="bcb08-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="bcb08-116">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="bcb08-117">컴파일러 구성 요소용 컨테이너입니다. 0개 이상의 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-117">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="bcb08-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="bcb08-118">\<compiler></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="bcb08-119">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bcb08-120">예제</span><span class="sxs-lookup"><span data-stu-id="bcb08-120">Example</span></span>  
 <span data-ttu-id="bcb08-121">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcb08-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bcb08-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="bcb08-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="bcb08-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bcb08-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="bcb08-124">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="bcb08-124">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
