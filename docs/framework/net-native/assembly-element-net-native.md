---
description: '자세히 알아보기: <Assembly> 요소 (.NET 네이티브)'
title: <Assembly> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
ms.openlocfilehash: 567a30a6a77e9de03635a9dfaae6bb28c9d728f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747922"
---
# <a name="assembly-element-net-native"></a><span data-ttu-id="91432-103">\<Assembly> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="91432-103">\<Assembly> Element (.NET Native)</span></span>

<span data-ttu-id="91432-104">지정된 어셈블리의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-104">Applies runtime reflection policy to all the types in a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91432-105">구문</span><span class="sxs-lookup"><span data-stu-id="91432-105">Syntax</span></span>  
  
```xml  
<Assembly Name="assembly_name"
          Activate="policy_setting"  
          Browse="policy_setting"  
          Dynamic="policy_setting"  
          Serialize="policy_setting"  
          DataContractSerializer="policy_setting"  
          DataContractJsonSerializer="policy_setting"  
          XmlSerializer="policy_setting"  
          MarshalObject="policy_setting"  
          MarshalDelegate="policy_setting"  
          MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91432-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91432-106">Attributes and Elements</span></span>  

 <span data-ttu-id="91432-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91432-108">특성</span><span class="sxs-lookup"><span data-stu-id="91432-108">Attributes</span></span>  
  
|<span data-ttu-id="91432-109">attribute</span><span class="sxs-lookup"><span data-stu-id="91432-109">Attribute</span></span>|<span data-ttu-id="91432-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="91432-110">Attribute type</span></span>|<span data-ttu-id="91432-111">설명</span><span class="sxs-lookup"><span data-stu-id="91432-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="91432-112">일반</span><span class="sxs-lookup"><span data-stu-id="91432-112">General</span></span>|<span data-ttu-id="91432-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-113">Required attribute.</span></span> <span data-ttu-id="91432-114">어셈블리의 단순한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-114">Specifies the simple name of an assembly.</span></span>|  
|`Activate`|<span data-ttu-id="91432-115">반사</span><span class="sxs-lookup"><span data-stu-id="91432-115">Reflection</span></span>|<span data-ttu-id="91432-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-116">Optional attribute.</span></span> <span data-ttu-id="91432-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="91432-118">반사</span><span class="sxs-lookup"><span data-stu-id="91432-118">Reflection</span></span>|<span data-ttu-id="91432-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-119">Optional attribute.</span></span> <span data-ttu-id="91432-120">어셈블리의 형식에 대한 정보 쿼리 또는 형식 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91432-120">Controls querying for information about or enumerating the types in the assembly, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="91432-121">반사</span><span class="sxs-lookup"><span data-stu-id="91432-121">Reflection</span></span>|<span data-ttu-id="91432-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-122">Optional attribute.</span></span> <span data-ttu-id="91432-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="91432-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="91432-124">Serialization</span></span>|<span data-ttu-id="91432-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-125">Optional attribute.</span></span> <span data-ttu-id="91432-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="91432-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="91432-127">Serialization</span></span>|<span data-ttu-id="91432-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-128">Optional attribute.</span></span> <span data-ttu-id="91432-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="91432-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="91432-130">Serialization</span></span>|<span data-ttu-id="91432-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-131">Optional attribute.</span></span> <span data-ttu-id="91432-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="91432-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="91432-133">Serialization</span></span>|<span data-ttu-id="91432-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-134">Optional attribute.</span></span> <span data-ttu-id="91432-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="91432-136">Interop</span><span class="sxs-lookup"><span data-stu-id="91432-136">Interop</span></span>|<span data-ttu-id="91432-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-137">Optional attribute.</span></span> <span data-ttu-id="91432-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="91432-139">Interop</span><span class="sxs-lookup"><span data-stu-id="91432-139">Interop</span></span>|<span data-ttu-id="91432-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-140">Optional attribute.</span></span> <span data-ttu-id="91432-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="91432-142">Interop</span><span class="sxs-lookup"><span data-stu-id="91432-142">Interop</span></span>|<span data-ttu-id="91432-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-143">Optional attribute.</span></span> <span data-ttu-id="91432-144">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-144">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="91432-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="91432-145">Name attribute</span></span>  
  
|<span data-ttu-id="91432-146">값</span><span class="sxs-lookup"><span data-stu-id="91432-146">Value</span></span>|<span data-ttu-id="91432-147">설명</span><span class="sxs-lookup"><span data-stu-id="91432-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91432-148">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="91432-148">*assembly_name*</span></span>|<span data-ttu-id="91432-149">파일 확장명이 없는 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-149">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="91432-150">이 특성은 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-150">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="91432-151">예를 들어 Extensions.dll 어셈블리의 이름은 "Extensions"입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-151">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span><br /><br /> <span data-ttu-id="91432-152">리터럴 문자열 `*Application*`을 지정하여 어셈블리 로드 여부에 관계없이 앱 패키지의 모든 어셈블리에 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91432-152">You can also specify the literal string `*Application*` to apply policy to all assemblies in your app package, whether those assemblies are loaded or not.</span></span> <span data-ttu-id="91432-153">`*Application*`을 사용하는 경우 정책이 .NET Framework 어셈블리에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91432-153">`*Application*` never applies policy to .NET Framework assemblies.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="91432-154">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="91432-154">All other attributes</span></span>  
  
|<span data-ttu-id="91432-155">값</span><span class="sxs-lookup"><span data-stu-id="91432-155">Value</span></span>|<span data-ttu-id="91432-156">설명</span><span class="sxs-lookup"><span data-stu-id="91432-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91432-157">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="91432-157">*policy_setting*</span></span>|<span data-ttu-id="91432-158">어셈블리의 모든 형식에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-158">The setting to apply to this policy type for all types in the assembly.</span></span> <span data-ttu-id="91432-159">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-159">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="91432-160">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91432-160">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91432-161">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91432-161">Child Elements</span></span>  
  
|<span data-ttu-id="91432-162">요소</span><span class="sxs-lookup"><span data-stu-id="91432-162">Element</span></span>|<span data-ttu-id="91432-163">설명</span><span class="sxs-lookup"><span data-stu-id="91432-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="91432-164">자식 네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-164">Applies reflection policy to all types in a child namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="91432-165">형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-165">Applies reflection policy to a type.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="91432-166">생성된 제네릭 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-166">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91432-167">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91432-167">Parent Elements</span></span>  
  
|<span data-ttu-id="91432-168">요소</span><span class="sxs-lookup"><span data-stu-id="91432-168">Element</span></span>|<span data-ttu-id="91432-169">설명</span><span class="sxs-lookup"><span data-stu-id="91432-169">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="91432-170">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91432-170">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="91432-171">요소에는 [\<Application>](application-element-net-native.md) 요소가 0 개, 1 개 또는 그 이상 있을 수 있습니다 `<Assembly>` .</span><span class="sxs-lookup"><span data-stu-id="91432-171">The [\<Application>](application-element-net-native.md) element can have zero, one, or more `<Assembly>` elements.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="91432-172">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-172">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="91432-173">[\<Library>](library-element-net-native.md)요소는 0 개 또는 한 개의 요소를 포함할 수 있습니다 `<Assembly>` .</span><span class="sxs-lookup"><span data-stu-id="91432-173">The [\<Library>](library-element-net-native.md) element can have zero or one `<Assembly>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91432-174">설명</span><span class="sxs-lookup"><span data-stu-id="91432-174">Remarks</span></span>  

 <span data-ttu-id="91432-175">`<Assembly>` 요소는 어셈블리의 모든 형식에 대한 런타임 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-175">The `<Assembly>` element defines runtime policy for all the types in an assembly.</span></span> <span data-ttu-id="91432-176">이 [\<Library>](library-element-net-native.md) 요소는 라이브러리를 지정 하지만 해당 자식 요소에 의존 하 여 런타임 리플렉션 정책을 정의 하는 요소와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="91432-176">It differs from the [\<Library>](library-element-net-native.md) element, which specifies a library but depends on its child elements to define runtime reflection policy.</span></span> <span data-ttu-id="91432-177">`<Assembly>` 요소는 자식 요소에 의해 재정의되지 않으면 어셈블리의 모든 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91432-177">The `<Assembly>` element applies to all the types in an assembly unless they are overridden by a child element.</span></span>  
  
 <span data-ttu-id="91432-178">다음 예제에서는 `Name` 특성에 “\*Application\*” 값을 할당하여 앱 패키지 내 어셈블리의 모든 형식에 대해 런타임 정책을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91432-178">The following example shows how you can apply runtime policy to all the types in assemblies within your app package by assigning the `Name` attribute a value of "\*Application\*".</span></span> <span data-ttu-id="91432-179">`<Assembly>`요소는 요소의 자식 이어야 합니다 [\<Application>](application-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="91432-179">The `<Assembly>` element must be a child of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>  
```  
  
 <span data-ttu-id="91432-180">`Activate`, `Browse`, `Dynamic` 및 `Serialize` 특성은 모두 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="91432-180">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="91432-181">그러나 `<Assembly>` 요소는 이러한 특성을 하나 이상 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91432-181">However, the `<Assembly>` element must contain at least one of these attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91432-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91432-182">See also</span></span>

- [<span data-ttu-id="91432-183">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="91432-183">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="91432-184">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="91432-184">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="91432-185">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="91432-185">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
