---
title: <Library>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: f94bfe047fa7a95b6f24264bae0b27112c589dfd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128361"
---
# <a name="library-element-net-native"></a><span data-ttu-id="28a92-102">\<Library>요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="28a92-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="28a92-103">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="28a92-104">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-104">\<Directives> Element</span></span>  
<span data-ttu-id="28a92-105">\<Library> 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a92-106">구문</span><span class="sxs-lookup"><span data-stu-id="28a92-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28a92-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-107">Attributes and Elements</span></span>  
 <span data-ttu-id="28a92-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28a92-109">특성</span><span class="sxs-lookup"><span data-stu-id="28a92-109">Attributes</span></span>  
  
|<span data-ttu-id="28a92-110">attribute</span><span class="sxs-lookup"><span data-stu-id="28a92-110">Attribute</span></span>|<span data-ttu-id="28a92-111">Description</span><span class="sxs-lookup"><span data-stu-id="28a92-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="28a92-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-112">Required attribute.</span></span> <span data-ttu-id="28a92-113">어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="28a92-114">이 `<Library>` 요소의 자식 요소는 이 어셈블리에 있는 형식 및 형식 멤버에 대한 런타임 리플렉션 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="28a92-115">Name 특성</span><span class="sxs-lookup"><span data-stu-id="28a92-115">Name attribute</span></span>  
  
|<span data-ttu-id="28a92-116">값</span><span class="sxs-lookup"><span data-stu-id="28a92-116">Value</span></span>|<span data-ttu-id="28a92-117">Description</span><span class="sxs-lookup"><span data-stu-id="28a92-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28a92-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="28a92-118">*assembly_name*</span></span>|<span data-ttu-id="28a92-119">파일 확장명이 없는 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="28a92-120">이 특성은 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="28a92-121">예를 들어 Extensions.dll 어셈블리의 이름은 "Extensions"입니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="28a92-122">어셈블리에서 조건부 메타데이터 포함을 지원하는 특수 *assembly_name* 형식에 대한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28a92-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28a92-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-123">Child Elements</span></span>  
  
|<span data-ttu-id="28a92-124">요소</span><span class="sxs-lookup"><span data-stu-id="28a92-124">Element</span></span>|<span data-ttu-id="28a92-125">Description</span><span class="sxs-lookup"><span data-stu-id="28a92-125">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="28a92-126">특정 어셈블리의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-126">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="28a92-127">특정 네임스페이스의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-127">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="28a92-128">클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-128">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="28a92-129">생성된 제네릭 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-129">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="28a92-130">예를 들어 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 요소를 사용 하 여 형식에 대 한 정책을 정의할 수 있습니다 `List<String>` .</span><span class="sxs-lookup"><span data-stu-id="28a92-130">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28a92-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-131">Parent Elements</span></span>  
  
|<span data-ttu-id="28a92-132">요소</span><span class="sxs-lookup"><span data-stu-id="28a92-132">Element</span></span>|<span data-ttu-id="28a92-133">Description</span><span class="sxs-lookup"><span data-stu-id="28a92-133">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="28a92-134">런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-134">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28a92-135">설명</span><span class="sxs-lookup"><span data-stu-id="28a92-135">Remarks</span></span>  
 <span data-ttu-id="28a92-136">요소는 0 개 이상의 [\<Directives>](directives-element-net-native.md) 요소를 포함할 수 있습니다 `<Library>` .</span><span class="sxs-lookup"><span data-stu-id="28a92-136">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="28a92-137">`<Library>` 요소는 런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용되며 정책을 표현하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-137">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="28a92-138">컴파일 타임에 컴파일러 도구는 `<Library>` 요소로 지정된 라이브러리에서만 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-138">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="28a92-139">반면, 컴파일러 도구는 요소의 자식 요소로 식별 되는 프로그램 요소에 대 한 모든 라이브러리 including.NET Framework core 라이브러리를 검색 [\<Application>](application-element-net-native.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-139">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="28a92-140">`<Library>` 지시문은 조건부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-140">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="28a92-141">`<Library>`요소 이름이 별표 ()로 시작 하 고 끝나는 경우 \* `<Library>` 지시문은 별표 사이에 지정 된 어셈블리를 앱에서 참조 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-141">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="28a92-142">예를 들어 다음 런타임 지시어는 응용 프로그램에서 유틸리티 .dll 어셈블리를 참조 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28a92-142">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28a92-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28a92-143">See also</span></span>

- [<span data-ttu-id="28a92-144">\<Application>요소인</span><span class="sxs-lookup"><span data-stu-id="28a92-144">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="28a92-145">\<Directives>요소인</span><span class="sxs-lookup"><span data-stu-id="28a92-145">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="28a92-146">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="28a92-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="28a92-147">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="28a92-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
