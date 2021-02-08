---
description: '자세히 알아보기: <TypeInstantiation> 요소 (.NET 네이티브)'
title: <TypeInstantiation> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
ms.openlocfilehash: 8939767e016283ea525fbd74554fe30b1cca952a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801932"
---
# <a name="typeinstantiation-element-net-native"></a><span data-ttu-id="fa76d-103">\<TypeInstantiation> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="fa76d-103">\<TypeInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="fa76d-104">생성된 제네릭 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-104">Applies runtime reflection policy to a constructed generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa76d-105">구문</span><span class="sxs-lookup"><span data-stu-id="fa76d-105">Syntax</span></span>  
  
```xml  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
                   Activate="policy_type"  
                   Browse="policy_type"  
                   Dynamic="policy_type"  
                   Serialize="policy_type"  
                   DataContractSerializer="policy_setting"  
                   DataContractJsonSerializer="policy_setting"  
                   XmlSerializer="policy_setting"  
                   MarshalObject="policy_setting"  
                   MarshalDelegate="policy_setting"  
                   MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa76d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fa76d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa76d-108">특성</span><span class="sxs-lookup"><span data-stu-id="fa76d-108">Attributes</span></span>  
  
|<span data-ttu-id="fa76d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fa76d-109">Attribute</span></span>|<span data-ttu-id="fa76d-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="fa76d-110">Attribute type</span></span>|<span data-ttu-id="fa76d-111">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="fa76d-112">일반</span><span class="sxs-lookup"><span data-stu-id="fa76d-112">General</span></span>|<span data-ttu-id="fa76d-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-113">Required attribute.</span></span> <span data-ttu-id="fa76d-114">형식 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-114">Specifies the type name.</span></span>|  
|`Arguments`|<span data-ttu-id="fa76d-115">일반</span><span class="sxs-lookup"><span data-stu-id="fa76d-115">General</span></span>|<span data-ttu-id="fa76d-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-116">Required attribute.</span></span> <span data-ttu-id="fa76d-117">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-117">Specifies the generic type arguments.</span></span> <span data-ttu-id="fa76d-118">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-118">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Activate`|<span data-ttu-id="fa76d-119">반사</span><span class="sxs-lookup"><span data-stu-id="fa76d-119">Reflection</span></span>|<span data-ttu-id="fa76d-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-120">Optional attribute.</span></span> <span data-ttu-id="fa76d-121">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-121">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="fa76d-122">반사</span><span class="sxs-lookup"><span data-stu-id="fa76d-122">Reflection</span></span>|<span data-ttu-id="fa76d-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-123">Optional attribute.</span></span> <span data-ttu-id="fa76d-124">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-124">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="fa76d-125">반사</span><span class="sxs-lookup"><span data-stu-id="fa76d-125">Reflection</span></span>|<span data-ttu-id="fa76d-126">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-126">Optional attribute.</span></span> <span data-ttu-id="fa76d-127">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-127">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="fa76d-128">Serialization</span><span class="sxs-lookup"><span data-stu-id="fa76d-128">Serialization</span></span>|<span data-ttu-id="fa76d-129">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-129">Optional attribute.</span></span> <span data-ttu-id="fa76d-130">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-130">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="fa76d-131">Serialization</span><span class="sxs-lookup"><span data-stu-id="fa76d-131">Serialization</span></span>|<span data-ttu-id="fa76d-132">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-132">Optional attribute.</span></span> <span data-ttu-id="fa76d-133"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-133">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="fa76d-134">Serialization</span><span class="sxs-lookup"><span data-stu-id="fa76d-134">Serialization</span></span>|<span data-ttu-id="fa76d-135">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-135">Optional attribute.</span></span> <span data-ttu-id="fa76d-136"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-136">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="fa76d-137">Serialization</span><span class="sxs-lookup"><span data-stu-id="fa76d-137">Serialization</span></span>|<span data-ttu-id="fa76d-138">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-138">Optional attribute.</span></span> <span data-ttu-id="fa76d-139"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-139">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="fa76d-140">Interop</span><span class="sxs-lookup"><span data-stu-id="fa76d-140">Interop</span></span>|<span data-ttu-id="fa76d-141">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-141">Optional attribute.</span></span> <span data-ttu-id="fa76d-142">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-142">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="fa76d-143">Interop</span><span class="sxs-lookup"><span data-stu-id="fa76d-143">Interop</span></span>|<span data-ttu-id="fa76d-144">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-144">Optional attribute.</span></span> <span data-ttu-id="fa76d-145">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-145">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="fa76d-146">Interop</span><span class="sxs-lookup"><span data-stu-id="fa76d-146">Interop</span></span>|<span data-ttu-id="fa76d-147">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-147">Optional attribute.</span></span> <span data-ttu-id="fa76d-148">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-148">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="fa76d-149">Name 특성</span><span class="sxs-lookup"><span data-stu-id="fa76d-149">Name attribute</span></span>  
  
|<span data-ttu-id="fa76d-150">값</span><span class="sxs-lookup"><span data-stu-id="fa76d-150">Value</span></span>|<span data-ttu-id="fa76d-151">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa76d-152">*type_name*</span><span class="sxs-lookup"><span data-stu-id="fa76d-152">*type_name*</span></span>|<span data-ttu-id="fa76d-153">형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-153">The type name.</span></span> <span data-ttu-id="fa76d-154">이 `<TypeInstantiation>` 요소가 [\<Namespace>](namespace-element-net-native.md) 요소, [\<Type>](type-element-net-native.md) 요소 또는 다른 요소의 자식인 경우 `<TypeInstantiation>` 네임 스페이스 없이 형식의 이름을 지정할 수 *type_name* .</span><span class="sxs-lookup"><span data-stu-id="fa76d-154">If this `<TypeInstantiation>` element is the child of a [\<Namespace>](namespace-element-net-native.md) element, a [\<Type>](type-element-net-native.md) element, or another `<TypeInstantiation>` element, *type_name* can specify the name of the type without its namespace.</span></span> <span data-ttu-id="fa76d-155">그러지 않으면 *type_name* 은 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-155">Otherwise, *type_name* must include the fully qualified type name.</span></span> <span data-ttu-id="fa76d-156">형식 이름은 데코레이팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-156">The type name isn't decorated.</span></span> <span data-ttu-id="fa76d-157">예를 들어 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 개체의 `<TypeInstantiation>` 요소는 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-157">For example, for a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> object, the `<TypeInstantiation>` element might appear as follows:</span></span><br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="fa76d-158">인수 특성</span><span class="sxs-lookup"><span data-stu-id="fa76d-158">Arguments attribute</span></span>  
  
|<span data-ttu-id="fa76d-159">값</span><span class="sxs-lookup"><span data-stu-id="fa76d-159">Value</span></span>|<span data-ttu-id="fa76d-160">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa76d-161">*type_argument*</span><span class="sxs-lookup"><span data-stu-id="fa76d-161">*type_argument*</span></span>|<span data-ttu-id="fa76d-162">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-162">Specifies the generic type arguments.</span></span> <span data-ttu-id="fa76d-163">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-163">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="fa76d-164">각 인수는 정규화된 형식 이름으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-164">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="fa76d-165">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="fa76d-165">All other attributes</span></span>  
  
|<span data-ttu-id="fa76d-166">값</span><span class="sxs-lookup"><span data-stu-id="fa76d-166">Value</span></span>|<span data-ttu-id="fa76d-167">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-167">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa76d-168">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="fa76d-168">*policy_setting*</span></span>|<span data-ttu-id="fa76d-169">생성된 제네릭 형식에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-169">The setting to apply to this policy type for the constructed generic type.</span></span> <span data-ttu-id="fa76d-170">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-170">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="fa76d-171">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa76d-171">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa76d-172">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-172">Child Elements</span></span>  
  
|<span data-ttu-id="fa76d-173">요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-173">Element</span></span>|<span data-ttu-id="fa76d-174">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-174">Description</span></span>|  
|-------------|-----------------|  
|[\<Event>](event-element-net-native.md)|<span data-ttu-id="fa76d-175">이 형식에 속하는 이벤트에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-175">Applies reflection policy to an event belonging to this type.</span></span>|  
|[\<Field>](field-element-net-native.md)|<span data-ttu-id="fa76d-176">이 형식에 속하는 필드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-176">Applies reflection policy to a field belonging to this type.</span></span>|  
|[\<ImpliesType>](impliestype-element-net-native.md)|<span data-ttu-id="fa76d-177">포함 `<TypeInstantiation>` 요소가 나타내는 형식에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-177">Applies policy to a type, if that policy has been applied to the type represented by the containing `<TypeInstantiation>` element.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="fa76d-178">이 형식에 속하는 메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-178">Applies reflection policy to a method belonging to this type.</span></span>|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|<span data-ttu-id="fa76d-179">이 형식에 속하는 생성된 제네릭 메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-179">Applies reflection policy to a constructed generic method belonging to this type.</span></span>|  
|[\<Property>](property-element-net-native.md)|<span data-ttu-id="fa76d-180">이 형식에 속하는 속성에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-180">Applies reflection policy to a property belonging to this type.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="fa76d-181">중첩된 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-181">Applies reflection policy to a nested type.</span></span>|  
|`<TypeInstantiation>`|<span data-ttu-id="fa76d-182">생성된 중첩 제네릭 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-182">Applies reflection policy to a nested constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa76d-183">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-183">Parent Elements</span></span>  
  
|<span data-ttu-id="fa76d-184">요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-184">Element</span></span>|<span data-ttu-id="fa76d-185">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-185">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="fa76d-186">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-186">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span>|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="fa76d-187">지정된 어셈블리의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-187">Applies reflection policy to all the types in a specified assembly.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="fa76d-188">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-188">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="fa76d-189">네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-189">Applies reflection policy to all the types in a namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="fa76d-190">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-190">Applies reflection policy to a type and all its members.</span></span>|  
|`<TypeInstantiation>`|<span data-ttu-id="fa76d-191">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-191">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa76d-192">설명</span><span class="sxs-lookup"><span data-stu-id="fa76d-192">Remarks</span></span>  

 <span data-ttu-id="fa76d-193">리플렉션, serialization 및 interop 특성은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-193">The reflection, serialization, and interop attributes are all optional.</span></span> <span data-ttu-id="fa76d-194">그러나 이러한 특성이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-194">However, at least one must be present.</span></span>  
  
 <span data-ttu-id="fa76d-195">`<TypeInstantiation>`요소가 [\<Assembly>](assembly-element-net-native.md) , [\<Namespace>](namespace-element-net-native.md) 또는 요소의 자식인 경우 [\<Type>](type-element-net-native.md) 부모 요소에 의해 정의 된 정책 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-195">If a `<TypeInstantiation>` element is the child of an [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), or [\<Type>](type-element-net-native.md), element, it overrides the policy settings defined by the parent element.</span></span> <span data-ttu-id="fa76d-196">[\<Type>](type-element-net-native.md)요소가 해당 제네릭 형식 정의를 정의 하는 경우 `<TypeInstantiation>` 요소는 지정 된 생성 된 제네릭 형식의 인스턴스화에 대해서만 런타임 리플렉션 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-196">If a [\<Type>](type-element-net-native.md) element defines a corresponding generic type definition, the `<TypeInstantiation>` element overrides runtime reflection policy only for instantiations of the specified constructed generic type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa76d-197">예제</span><span class="sxs-lookup"><span data-stu-id="fa76d-197">Example</span></span>  

 <span data-ttu-id="fa76d-198">다음 예제에서는 리플렉션을 사용하여 생성된 <xref:System.Collections.Generic.Dictionary%602> 개체에서 제네릭 형식 정의를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-198">The following example uses reflection to retrieve the generic type definition from a constructed <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="fa76d-199">또한 리플렉션을 사용하여 생성된 제네릭 형식 및 제네릭 형식 정의를 나타내는 <xref:System.Type> 개체에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-199">It also uses reflection to display information about <xref:System.Type> objects that represent constructed generic types and generic type definitions.</span></span> <span data-ttu-id="fa76d-200">예제의 변수는 `b` <xref:Windows.UI.Xaml.Controls.TextBlock> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-200">The variable `b` in the example is a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 <span data-ttu-id="fa76d-201">.NET 네이티브 도구 체인을 사용 하 여 컴파일한 후 예제에서는 메서드를 호출 하는 줄에서 [MissingMetadataException](missingmetadataexception-class-net-native.md) 예외를 throw 합니다 <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fa76d-201">After compilation with the .NET Native tool chain, the example throws a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception on the line that calls the <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa76d-202">다음 `<TypeInstantiation>` 요소를 런타임 지시문 파일에 추가하면 예외를 방지하고 필요한 메타데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa76d-202">You can eliminate the exception and provide the necessary metadata by adding the following `<TypeInstantiation>` element to the runtime directives file:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa76d-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa76d-203">See also</span></span>

- [<span data-ttu-id="fa76d-204">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="fa76d-204">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="fa76d-205">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="fa76d-205">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="fa76d-206">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="fa76d-206">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
