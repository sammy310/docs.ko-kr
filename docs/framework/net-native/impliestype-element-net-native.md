---
title: <ImpliesType> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 2f0ce1a1587e190627212cba07db298c12f4b30e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128386"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="41878-102">\<ImpliesType > 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="41878-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="41878-103">포함 형식 또는 메서드에 정책이 적용된 경우 해당 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41878-104">구문</span><span class="sxs-lookup"><span data-stu-id="41878-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41878-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="41878-105">Attributes and Elements</span></span>  
 <span data-ttu-id="41878-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41878-107">특성</span><span class="sxs-lookup"><span data-stu-id="41878-107">Attributes</span></span>  
  
|<span data-ttu-id="41878-108">특성</span><span class="sxs-lookup"><span data-stu-id="41878-108">Attribute</span></span>|<span data-ttu-id="41878-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="41878-109">Attribute type</span></span>|<span data-ttu-id="41878-110">설명</span><span class="sxs-lookup"><span data-stu-id="41878-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="41878-111">일반</span><span class="sxs-lookup"><span data-stu-id="41878-111">General</span></span>|<span data-ttu-id="41878-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-112">Required attribute.</span></span> <span data-ttu-id="41878-113">형식 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="41878-114">반사</span><span class="sxs-lookup"><span data-stu-id="41878-114">Reflection</span></span>|<span data-ttu-id="41878-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-115">Optional attribute.</span></span> <span data-ttu-id="41878-116">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="41878-117">반사</span><span class="sxs-lookup"><span data-stu-id="41878-117">Reflection</span></span>|<span data-ttu-id="41878-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-118">Optional attribute.</span></span> <span data-ttu-id="41878-119">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="41878-120">반사</span><span class="sxs-lookup"><span data-stu-id="41878-120">Reflection</span></span>|<span data-ttu-id="41878-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-121">Optional attribute.</span></span> <span data-ttu-id="41878-122">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="41878-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="41878-123">Serialization</span></span>|<span data-ttu-id="41878-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-124">Optional attribute.</span></span> <span data-ttu-id="41878-125">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="41878-126">Serialization</span><span class="sxs-lookup"><span data-stu-id="41878-126">Serialization</span></span>|<span data-ttu-id="41878-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-127">Optional attribute.</span></span> <span data-ttu-id="41878-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="41878-129">Serialization</span><span class="sxs-lookup"><span data-stu-id="41878-129">Serialization</span></span>|<span data-ttu-id="41878-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-130">Optional attribute.</span></span> <span data-ttu-id="41878-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="41878-132">Serialization</span><span class="sxs-lookup"><span data-stu-id="41878-132">Serialization</span></span>|<span data-ttu-id="41878-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-133">Optional attribute.</span></span> <span data-ttu-id="41878-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="41878-135">Interop</span><span class="sxs-lookup"><span data-stu-id="41878-135">Interop</span></span>|<span data-ttu-id="41878-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-136">Optional attribute.</span></span> <span data-ttu-id="41878-137">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="41878-138">Interop</span><span class="sxs-lookup"><span data-stu-id="41878-138">Interop</span></span>|<span data-ttu-id="41878-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-139">Optional attribute.</span></span> <span data-ttu-id="41878-140">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="41878-141">Interop</span><span class="sxs-lookup"><span data-stu-id="41878-141">Interop</span></span>|<span data-ttu-id="41878-142">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-142">Optional attribute.</span></span> <span data-ttu-id="41878-143">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="41878-144">Name 특성</span><span class="sxs-lookup"><span data-stu-id="41878-144">Name attribute</span></span>  
  
|<span data-ttu-id="41878-145">값</span><span class="sxs-lookup"><span data-stu-id="41878-145">Value</span></span>|<span data-ttu-id="41878-146">설명</span><span class="sxs-lookup"><span data-stu-id="41878-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41878-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="41878-147">*type_name*</span></span>|<span data-ttu-id="41878-148">형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-148">The type name.</span></span> <span data-ttu-id="41878-149">이 `<ImpliesType>` 요소가 나타내는 형식이 포함 `<Type>` 요소와 같은 네임스페이스에 있으면 *type_name*은 네임스페이스가 없는 형식 이름을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="41878-150">그러지 않으면 *type_name*은 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="41878-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="41878-151">All other attributes</span></span>  
  
|<span data-ttu-id="41878-152">값</span><span class="sxs-lookup"><span data-stu-id="41878-152">Value</span></span>|<span data-ttu-id="41878-153">설명</span><span class="sxs-lookup"><span data-stu-id="41878-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41878-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="41878-154">*policy_setting*</span></span>|<span data-ttu-id="41878-155">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="41878-156">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="41878-157">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41878-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41878-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="41878-158">Child Elements</span></span>  
 <span data-ttu-id="41878-159">없음.</span><span class="sxs-lookup"><span data-stu-id="41878-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41878-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="41878-160">Parent Elements</span></span>  
  
|<span data-ttu-id="41878-161">요소</span><span class="sxs-lookup"><span data-stu-id="41878-161">Element</span></span>|<span data-ttu-id="41878-162">설명</span><span class="sxs-lookup"><span data-stu-id="41878-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41878-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="41878-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="41878-164">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="41878-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="41878-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="41878-166">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="41878-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="41878-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="41878-168">메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41878-169">주의</span><span class="sxs-lookup"><span data-stu-id="41878-169">Remarks</span></span>  
 <span data-ttu-id="41878-170">`<ImpliesType>` 요소는 주로 라이브러리에서 사용되며</span><span class="sxs-lookup"><span data-stu-id="41878-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="41878-171">다음과 같은 시나리오를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="41878-172">형식 하나에 대해 루틴을 리플렉션해야 하면 두 번째 형식에 대해서도 루틴을 리플렉션해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="41878-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="41878-173">정적 분석에서 필요한 것으로 표시하지 않았기 때문에 두 번째 형식의 암시적 인스턴스화에 대한 메타데이터를 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="41878-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="41878-174">가장 일반적인 두 가지 형식은 공유 형식 인수가 있는 제네릭 인스턴스화입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="41878-175">`<ImpliesType>` 요소는 부모 요소에 의해 지정된 형식을 리플렉션해야 하는 경우 `<ImpliesType>` 요소에 의해 지정된 형식도 리플렉션해야 한다는 가정 하에 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="41878-176">예를 들어 다음 리플렉션 지시문은 `Explicit<T>` 및 `Implicit<T>`의 두 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41878-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="41878-177">이 지시문은 `Explicit`의 인스턴스화에 정의된 `Dynamic` 정책 설정이 없으면 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="41878-178">예를 들어 `Explicit<Int32>`의 경우 `Implicit<Int32>`는 공용 멤버가 루트에 있는 상태로 인스턴스화되며 동적 프로그래밍을 위해 해당 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="41878-179">다음은 하나 이상의 serializer에 적용되는 실제 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="41878-180">지시문은 `IList<`*something*`>`으로 형식화된 항목을 반영하는 동시에 애플리케이션별 주석이 없어도 해당 `List<`*something*`>` 형식도 반영해야 하는 요구 사항을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="41878-181">`<ImpliesType>` 요소는 `<Method>` 내에서도 나타날 수 있습니다. 경우에 따라 제네릭 메서드를 인스턴스화하면 형식 인스턴스화에 대한 리플렉션이 수행될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="41878-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="41878-182">예를 들어 지정 된 라이브러리가 연결 된 <xref:System.Collections.Generic.List%601> 및 <xref:System.Array> 형식과 함께 동적으로 액세스 하는 `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` 제네릭 메서드가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41878-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="41878-183">이 예는 다음 코드와 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41878-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41878-184">참조</span><span class="sxs-lookup"><span data-stu-id="41878-184">See also</span></span>

- [<span data-ttu-id="41878-185">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="41878-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="41878-186">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="41878-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="41878-187">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="41878-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
