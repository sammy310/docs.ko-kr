---
title: <Library>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc3c85ab99574c96d8a68d4221f218a1340e4122
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049640"
---
# <a name="library-element-net-native"></a><span data-ttu-id="586da-102">\<Library > 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="586da-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="586da-103">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="586da-104">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="586da-104">\<Directives> Element</span></span>  
<span data-ttu-id="586da-105">\<Library> 요소</span><span class="sxs-lookup"><span data-stu-id="586da-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586da-106">구문</span><span class="sxs-lookup"><span data-stu-id="586da-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="586da-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="586da-107">Attributes and Elements</span></span>  
 <span data-ttu-id="586da-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="586da-109">특성</span><span class="sxs-lookup"><span data-stu-id="586da-109">Attributes</span></span>  
  
|<span data-ttu-id="586da-110">특성</span><span class="sxs-lookup"><span data-stu-id="586da-110">Attribute</span></span>|<span data-ttu-id="586da-111">설명</span><span class="sxs-lookup"><span data-stu-id="586da-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="586da-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="586da-112">Required attribute.</span></span> <span data-ttu-id="586da-113">어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="586da-114">이 `<Library>` 요소의 자식 요소는 이 어셈블리에 있는 형식 및 형식 멤버에 대한 런타임 리플렉션 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="586da-115">Name 특성</span><span class="sxs-lookup"><span data-stu-id="586da-115">Name attribute</span></span>  
  
|<span data-ttu-id="586da-116">값</span><span class="sxs-lookup"><span data-stu-id="586da-116">Value</span></span>|<span data-ttu-id="586da-117">Description</span><span class="sxs-lookup"><span data-stu-id="586da-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="586da-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="586da-118">*assembly_name*</span></span>|<span data-ttu-id="586da-119">파일 확장명이 없는 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="586da-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="586da-120">이 특성은 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="586da-121">예를 들어 Extensions.dll 어셈블리의 이름은 "Extensions"입니다.</span><span class="sxs-lookup"><span data-stu-id="586da-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="586da-122">어셈블리에서 조건부 메타데이터 포함을 지원하는 특수 *assembly_name* 형식에 대한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="586da-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="586da-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="586da-123">Child Elements</span></span>  
  
|<span data-ttu-id="586da-124">요소</span><span class="sxs-lookup"><span data-stu-id="586da-124">Element</span></span>|<span data-ttu-id="586da-125">설명</span><span class="sxs-lookup"><span data-stu-id="586da-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="586da-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="586da-126">\<Assembly></span></span>](assembly-element-net-native.md)|<span data-ttu-id="586da-127">특정 어셈블리의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="586da-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="586da-128">\<Namespace></span></span>](namespace-element-net-native.md)|<span data-ttu-id="586da-129">특정 네임스페이스의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="586da-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="586da-130">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="586da-131">클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="586da-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="586da-132">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="586da-133">생성된 제네릭 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="586da-134">예를 들어 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 요소를 사용하면 `List<String>` 형식에 대한 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586da-134">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="586da-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="586da-135">Parent Elements</span></span>  
  
|<span data-ttu-id="586da-136">요소</span><span class="sxs-lookup"><span data-stu-id="586da-136">Element</span></span>|<span data-ttu-id="586da-137">설명</span><span class="sxs-lookup"><span data-stu-id="586da-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="586da-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="586da-138">\<Directives></span></span>](directives-element-net-native.md)|<span data-ttu-id="586da-139">런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="586da-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="586da-140">설명</span><span class="sxs-lookup"><span data-stu-id="586da-140">Remarks</span></span>  
 <span data-ttu-id="586da-141">[\<Directives>](directives-element-net-native.md) 요소는 `<Library>` 요소를 포함하지 않을 수도 있고 하나 이상 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586da-141">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="586da-142">`<Library>` 요소는 런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용되며 정책을 표현하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="586da-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="586da-143">컴파일 타임에 컴파일러 도구는 `<Library>` 요소로 지정된 라이브러리에서만 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="586da-144">반면 .NET Framework 핵심 라이브러리를 비롯한 모든 라이브러리에서 [\<Application>](application-element-net-native.md) 요소의 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="586da-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="586da-145">`<Library>` 지시문은 조건부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="586da-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="586da-146">`<Library>` 요소 이름이 별표 (\*)로 시작 하 고 끝나는 경우 지시문은 `<Library>` 별표 사이에 지정 된 어셈블리를 앱에서 참조 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="586da-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="586da-147">예를 들어 다음 런타임 지시어는 응용 프로그램에서 유틸리티 .dll 어셈블리를 참조 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="586da-147">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="586da-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="586da-148">See also</span></span>

- [<span data-ttu-id="586da-149">\<응용 프로그램 > 요소</span><span class="sxs-lookup"><span data-stu-id="586da-149">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="586da-150">\<지시문 > 요소</span><span class="sxs-lookup"><span data-stu-id="586da-150">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="586da-151">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="586da-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="586da-152">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="586da-152">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
