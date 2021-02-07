---
description: '자세히 알아보기: <ImpliesType> 요소 (.NET 네이티브)'
title: <ImpliesType> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 6476876f335788a276907fd2aef02d5623382699
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747688"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="d8419-103">\<ImpliesType> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="d8419-103">\<ImpliesType> Element (.NET Native)</span></span>

<span data-ttu-id="d8419-104">포함 형식 또는 메서드에 정책이 적용된 경우 해당 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-104">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8419-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8419-105">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8419-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d8419-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d8419-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8419-108">특성</span><span class="sxs-lookup"><span data-stu-id="d8419-108">Attributes</span></span>  
  
|<span data-ttu-id="d8419-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d8419-109">Attribute</span></span>|<span data-ttu-id="d8419-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="d8419-110">Attribute type</span></span>|<span data-ttu-id="d8419-111">설명</span><span class="sxs-lookup"><span data-stu-id="d8419-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d8419-112">일반</span><span class="sxs-lookup"><span data-stu-id="d8419-112">General</span></span>|<span data-ttu-id="d8419-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-113">Required attribute.</span></span> <span data-ttu-id="d8419-114">형식 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-114">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="d8419-115">반사</span><span class="sxs-lookup"><span data-stu-id="d8419-115">Reflection</span></span>|<span data-ttu-id="d8419-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-116">Optional attribute.</span></span> <span data-ttu-id="d8419-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="d8419-118">반사</span><span class="sxs-lookup"><span data-stu-id="d8419-118">Reflection</span></span>|<span data-ttu-id="d8419-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-119">Optional attribute.</span></span> <span data-ttu-id="d8419-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="d8419-121">반사</span><span class="sxs-lookup"><span data-stu-id="d8419-121">Reflection</span></span>|<span data-ttu-id="d8419-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-122">Optional attribute.</span></span> <span data-ttu-id="d8419-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="d8419-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="d8419-124">Serialization</span></span>|<span data-ttu-id="d8419-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-125">Optional attribute.</span></span> <span data-ttu-id="d8419-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="d8419-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="d8419-127">Serialization</span></span>|<span data-ttu-id="d8419-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-128">Optional attribute.</span></span> <span data-ttu-id="d8419-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="d8419-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="d8419-130">Serialization</span></span>|<span data-ttu-id="d8419-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-131">Optional attribute.</span></span> <span data-ttu-id="d8419-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="d8419-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="d8419-133">Serialization</span></span>|<span data-ttu-id="d8419-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-134">Optional attribute.</span></span> <span data-ttu-id="d8419-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="d8419-136">Interop</span><span class="sxs-lookup"><span data-stu-id="d8419-136">Interop</span></span>|<span data-ttu-id="d8419-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-137">Optional attribute.</span></span> <span data-ttu-id="d8419-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="d8419-139">Interop</span><span class="sxs-lookup"><span data-stu-id="d8419-139">Interop</span></span>|<span data-ttu-id="d8419-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-140">Optional attribute.</span></span> <span data-ttu-id="d8419-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="d8419-142">Interop</span><span class="sxs-lookup"><span data-stu-id="d8419-142">Interop</span></span>|<span data-ttu-id="d8419-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-143">Optional attribute.</span></span> <span data-ttu-id="d8419-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d8419-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="d8419-145">Name attribute</span></span>  
  
|<span data-ttu-id="d8419-146">값</span><span class="sxs-lookup"><span data-stu-id="d8419-146">Value</span></span>|<span data-ttu-id="d8419-147">설명</span><span class="sxs-lookup"><span data-stu-id="d8419-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d8419-148">*type_name*</span><span class="sxs-lookup"><span data-stu-id="d8419-148">*type_name*</span></span>|<span data-ttu-id="d8419-149">형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-149">The type name.</span></span> <span data-ttu-id="d8419-150">이 `<ImpliesType>` 요소가 나타내는 형식이 포함 `<Type>` 요소와 같은 네임스페이스에 있으면 *type_name* 은 네임스페이스가 없는 형식 이름을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-150">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="d8419-151">그러지 않으면 *type_name* 은 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-151">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d8419-152">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="d8419-152">All other attributes</span></span>  
  
|<span data-ttu-id="d8419-153">값</span><span class="sxs-lookup"><span data-stu-id="d8419-153">Value</span></span>|<span data-ttu-id="d8419-154">설명</span><span class="sxs-lookup"><span data-stu-id="d8419-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d8419-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d8419-155">*policy_setting*</span></span>|<span data-ttu-id="d8419-156">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="d8419-157">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-157">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="d8419-158">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8419-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8419-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d8419-159">Child Elements</span></span>  

 <span data-ttu-id="d8419-160">없음</span><span class="sxs-lookup"><span data-stu-id="d8419-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8419-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d8419-161">Parent Elements</span></span>  
  
|<span data-ttu-id="d8419-162">요소</span><span class="sxs-lookup"><span data-stu-id="d8419-162">Element</span></span>|<span data-ttu-id="d8419-163">설명</span><span class="sxs-lookup"><span data-stu-id="d8419-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="d8419-164">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-164">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="d8419-165">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-165">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="d8419-166">메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-166">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8419-167">설명</span><span class="sxs-lookup"><span data-stu-id="d8419-167">Remarks</span></span>  

 <span data-ttu-id="d8419-168">`<ImpliesType>` 요소는 주로 라이브러리에서 사용되며</span><span class="sxs-lookup"><span data-stu-id="d8419-168">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="d8419-169">다음과 같은 시나리오를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-169">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="d8419-170">형식 하나에 대해 루틴을 리플렉션해야 하면 두 번째 형식에 대해서도 루틴을 리플렉션해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="d8419-170">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="d8419-171">정적 분석에서 필요한 것으로 표시하지 않았기 때문에 두 번째 형식의 암시적 인스턴스화에 대한 메타데이터를 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d8419-171">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="d8419-172">가장 일반적인 두 가지 형식은 공유 형식 인수가 있는 제네릭 인스턴스화입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-172">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="d8419-173">`<ImpliesType>` 요소는 부모 요소에 의해 지정된 형식을 리플렉션해야 하는 경우 `<ImpliesType>` 요소에 의해 지정된 형식도 리플렉션해야 한다는 가정 하에 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-173">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="d8419-174">예를 들어 다음 리플렉션 지시문은 `Explicit<T>` 및 `Implicit<T>`의 두 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-174">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="d8419-175">이 지시문은 `Explicit`의 인스턴스화에 정의된 `Dynamic` 정책 설정이 없으면 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-175">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="d8419-176">예를 들어 `Explicit<Int32>`의 경우 `Implicit<Int32>`는 공용 멤버가 루트에 있는 상태로 인스턴스화되며 동적 프로그래밍을 위해 해당 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-176">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="d8419-177">다음은 하나 이상의 serializer에 적용되는 실제 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-177">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="d8419-178">지시문은 형식에 따라 형식이 지정 된 항목을 반영 하는 요구 사항을 캡처하여 `IList<`  `>` `List<`  `>` 응용 프로그램별 주석을 요구 하지 않고 해당 하는 항목을 반영 하는 것도 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-178">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="d8419-179">`<ImpliesType>` 요소는 `<Method>` 내에서도 나타날 수 있습니다. 경우에 따라 제네릭 메서드를 인스턴스화하면 형식 인스턴스화에 대한 리플렉션이 수행될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-179">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="d8419-180">지정한 라이브러리가 연결된  및  형식과 함께 동적으로 액세스하는 제네릭 메서드 `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)`<xref:System.Collections.Generic.List%601><xref:System.Array>의 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-180">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="d8419-181">이 예는 다음 코드와 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8419-181">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8419-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8419-182">See also</span></span>

- [<span data-ttu-id="d8419-183">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="d8419-183">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="d8419-184">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="d8419-184">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="d8419-185">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d8419-185">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
