---
title: <Type> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
ms.openlocfilehash: e71df41c4a37206910d835ee85dc3d68b4cbad4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287711"
---
# <a name="type-element-net-native"></a><span data-ttu-id="1d723-102">\<Type> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="1d723-102">\<Type> Element (.NET Native)</span></span>

<span data-ttu-id="1d723-103">클래스 또는 구조체와 같은 특정 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-103">Applies runtime policy to a particular type, such as a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d723-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d723-104">Syntax</span></span>

```xml
<Type Name="type_name"
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

## <a name="attributes-and-elements"></a><span data-ttu-id="1d723-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1d723-105">Attributes and Elements</span></span>

<span data-ttu-id="1d723-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d723-107">특성</span><span class="sxs-lookup"><span data-stu-id="1d723-107">Attributes</span></span>

|<span data-ttu-id="1d723-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1d723-108">Attribute</span></span>|<span data-ttu-id="1d723-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="1d723-109">Attribute type</span></span>|<span data-ttu-id="1d723-110">Description</span><span class="sxs-lookup"><span data-stu-id="1d723-110">Description</span></span>|
|---------------|--------------------|-----------------|
|`Name`|<span data-ttu-id="1d723-111">일반</span><span class="sxs-lookup"><span data-stu-id="1d723-111">General</span></span>|<span data-ttu-id="1d723-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-112">Required attribute.</span></span> <span data-ttu-id="1d723-113">형식 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-113">Specifies the type name.</span></span>|
|`Activate`|<span data-ttu-id="1d723-114">반사</span><span class="sxs-lookup"><span data-stu-id="1d723-114">Reflection</span></span>|<span data-ttu-id="1d723-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-115">Optional attribute.</span></span> <span data-ttu-id="1d723-116">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-116">Controls runtime access to constructors to enable activation of instances.</span></span>|
|`Browse`|<span data-ttu-id="1d723-117">반사</span><span class="sxs-lookup"><span data-stu-id="1d723-117">Reflection</span></span>|<span data-ttu-id="1d723-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-118">Optional attribute.</span></span> <span data-ttu-id="1d723-119">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|
|`Dynamic`|<span data-ttu-id="1d723-120">반사</span><span class="sxs-lookup"><span data-stu-id="1d723-120">Reflection</span></span>|<span data-ttu-id="1d723-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-121">Optional attribute.</span></span> <span data-ttu-id="1d723-122">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|
|`Serialize`|<span data-ttu-id="1d723-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="1d723-123">Serialization</span></span>|<span data-ttu-id="1d723-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-124">Optional attribute.</span></span> <span data-ttu-id="1d723-125">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|
|`DataContractSerializer`|<span data-ttu-id="1d723-126">Serialization</span><span class="sxs-lookup"><span data-stu-id="1d723-126">Serialization</span></span>|<span data-ttu-id="1d723-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-127">Optional attribute.</span></span> <span data-ttu-id="1d723-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|
|`DataContractJsonSerializer`|<span data-ttu-id="1d723-129">Serialization</span><span class="sxs-lookup"><span data-stu-id="1d723-129">Serialization</span></span>|<span data-ttu-id="1d723-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-130">Optional attribute.</span></span> <span data-ttu-id="1d723-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|
|`XmlSerializer`|<span data-ttu-id="1d723-132">Serialization</span><span class="sxs-lookup"><span data-stu-id="1d723-132">Serialization</span></span>|<span data-ttu-id="1d723-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-133">Optional attribute.</span></span> <span data-ttu-id="1d723-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|
|`MarshalObject`|<span data-ttu-id="1d723-135">Interop</span><span class="sxs-lookup"><span data-stu-id="1d723-135">Interop</span></span>|<span data-ttu-id="1d723-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-136">Optional attribute.</span></span> <span data-ttu-id="1d723-137">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|
|`MarshalDelegate`|<span data-ttu-id="1d723-138">Interop</span><span class="sxs-lookup"><span data-stu-id="1d723-138">Interop</span></span>|<span data-ttu-id="1d723-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-139">Optional attribute.</span></span> <span data-ttu-id="1d723-140">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|
|`MarshalStructure`|<span data-ttu-id="1d723-141">Interop</span><span class="sxs-lookup"><span data-stu-id="1d723-141">Interop</span></span>|<span data-ttu-id="1d723-142">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-142">Optional attribute.</span></span> <span data-ttu-id="1d723-143">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-143">Controls policy for marshaling value types to native code.</span></span>|

## <a name="name-attribute"></a><span data-ttu-id="1d723-144">Name 특성</span><span class="sxs-lookup"><span data-stu-id="1d723-144">Name attribute</span></span>

|<span data-ttu-id="1d723-145">값</span><span class="sxs-lookup"><span data-stu-id="1d723-145">Value</span></span>|<span data-ttu-id="1d723-146">Description</span><span class="sxs-lookup"><span data-stu-id="1d723-146">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="1d723-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="1d723-147">*type_name*</span></span>|<span data-ttu-id="1d723-148">형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-148">The type name.</span></span> <span data-ttu-id="1d723-149">이 `<Type>` 요소가 [\<Namespace>](namespace-element-net-native.md) 요소 또는 다른 요소의 자식인 경우 `<Type>` 네임 스페이스 없이 형식의 이름을 포함할 수 *type_name* .</span><span class="sxs-lookup"><span data-stu-id="1d723-149">If this `<Type>` element is the child of either a [\<Namespace>](namespace-element-net-native.md) element or another `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="1d723-150">그러지 않으면 *type_name* 은 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|

## <a name="all-other-attributes"></a><span data-ttu-id="1d723-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="1d723-151">All other attributes</span></span>

|<span data-ttu-id="1d723-152">값</span><span class="sxs-lookup"><span data-stu-id="1d723-152">Value</span></span>|<span data-ttu-id="1d723-153">Description</span><span class="sxs-lookup"><span data-stu-id="1d723-153">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="1d723-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="1d723-154">*policy_setting*</span></span>|<span data-ttu-id="1d723-155">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="1d723-156">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="1d723-157">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d723-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1d723-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1d723-158">Child Elements</span></span>

|<span data-ttu-id="1d723-159">요소</span><span class="sxs-lookup"><span data-stu-id="1d723-159">Element</span></span>|<span data-ttu-id="1d723-160">Description</span><span class="sxs-lookup"><span data-stu-id="1d723-160">Description</span></span>|
|-------------|-----------------|
|[\<AttributeImplies>](attributeimplies-element-net-native.md)|<span data-ttu-id="1d723-161">포함 형식이 특성이면 해당 특성이 적용되는 코드 요소에 대해 런타임 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-161">If the containing type is an attribute, defines runtime policy for code elements to which the attribute is applied.</span></span>|
|[\<Event>](event-element-net-native.md)|<span data-ttu-id="1d723-162">이 형식에 속하는 이벤트에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-162">Applies reflection policy to an event belonging to this type.</span></span>|
|[\<Field>](field-element-net-native.md)|<span data-ttu-id="1d723-163">이 형식에 속하는 필드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-163">Applies reflection policy to a field belonging to this type.</span></span>|
|[\<GenericParameter>](genericparameter-element-net-native.md)|<span data-ttu-id="1d723-164">제네릭 형식의 매개 변수 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-164">Applies policy to the parameter type of a generic type.</span></span>|
|[\<ImpliesType>](impliestype-element-net-native.md)|<span data-ttu-id="1d723-165">포함 `<Type>` 요소가 나타내는 형식에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-165">Applies policy to a type, if that policy has been applied to the type represented by the containing `<Type>` element.</span></span>|
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="1d723-166">이 형식에 속하는 메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-166">Applies reflection policy to a method belonging to this type.</span></span>|
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|<span data-ttu-id="1d723-167">이 형식에 속하는 생성된 제네릭 메서드에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-167">Applies reflection policy to a constructed generic method belonging to this type.</span></span>|
|[\<Property>](property-element-net-native.md)|<span data-ttu-id="1d723-168">이 형식에 속하는 속성에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-168">Applies reflection policy to a property belonging to this type.</span></span>|
|[\<Subtypes>](subtypes-element-net-native.md)|<span data-ttu-id="1d723-169">포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-169">Applies runtime policy to all classes inherited from the containing type.</span></span>|
|`<Type>`|<span data-ttu-id="1d723-170">중첩된 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-170">Applies reflection policy to a nested type.</span></span>|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="1d723-171">생성된 제네릭 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-171">Applies reflection policy to a constructed generic type.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1d723-172">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1d723-172">Parent Elements</span></span>

|<span data-ttu-id="1d723-173">요소</span><span class="sxs-lookup"><span data-stu-id="1d723-173">Element</span></span>|<span data-ttu-id="1d723-174">Description</span><span class="sxs-lookup"><span data-stu-id="1d723-174">Description</span></span>|
|-------------|-----------------|
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="1d723-175">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-175">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span>|
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="1d723-176">지정된 어셈블리의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-176">Applies reflection policy to all the types in a specified assembly.</span></span>|
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="1d723-177">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-177">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>|
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="1d723-178">네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-178">Applies reflection policy to all the types in a namespace.</span></span>|
|`<Type>`|<span data-ttu-id="1d723-179">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-179">Applies reflection policy to a type and all its members.</span></span>|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="1d723-180">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-180">Applies reflection policy to a constructed generic type and all its members.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1d723-181">설명</span><span class="sxs-lookup"><span data-stu-id="1d723-181">Remarks</span></span>

<span data-ttu-id="1d723-182">리플렉션, serialization 및 interop 특성은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-182">The reflection, serialization, and interop attributes are all optional.</span></span> <span data-ttu-id="1d723-183">이러한 특성이 없으면 `<Type>` 요소는 하위 형식이 개별 멤버의 정책을 정의하는 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-183">If none are present, the `<Type>` element serves as a container whose child types define policy for individual members.</span></span>

<span data-ttu-id="1d723-184">`<Type>`요소가 [\<Assembly>](assembly-element-net-native.md) ,, 또는 요소의 자식인 경우 [\<Namespace>](namespace-element-net-native.md) `<Type>` [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 부모 요소에 의해 정의 된 정책 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-184">If a `<Type>` element is the child of an [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), `<Type>`, or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element, it overrides the policy settings defined by the parent element.</span></span>

<span data-ttu-id="1d723-185">제네릭 형식의 `<Type>` 요소는 자체 정책이 없는 모든 인스턴스화에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-185">A `<Type>` element of a generic type applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="1d723-186">생성 된 제네릭 형식의 정책은 요소에 의해 정의 됩니다 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="1d723-186">The policy of constructed generic types is defined by the [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>

<span data-ttu-id="1d723-187">제네릭 형식의 경우 해당 이름은 억음 악센트 기호(\`)와 제네릭 매개 변수의 수가 차례로 붙는 형식으로 데코레이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-187">If the type is a generic type, its name is decorated by a grave accent symbol (\`) followed by its number of generic parameters.</span></span> <span data-ttu-id="1d723-188">예를 들어 `Name` 클래스 `<Type>` 요소의 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 특성은 ``Name="System.Collections.Generic.List`1"``로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-188">For example, the `Name` attribute of a `<Type>` element for the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> class appears as ``Name="System.Collections.Generic.List`1"``.</span></span>

## <a name="example"></a><span data-ttu-id="1d723-189">예제</span><span class="sxs-lookup"><span data-stu-id="1d723-189">Example</span></span>

<span data-ttu-id="1d723-190">다음 예제에서는 리플렉션을 사용하여 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 클래스의 필드, 속성 및 메서드에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-190">The following example uses reflection to display information about the fields, properties, and methods of the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1d723-191">예제의 변수는 `b` <xref:Windows.UI.Xaml.Controls.TextBlock> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-191">The variable `b` in the example is a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span> <span data-ttu-id="1d723-192">이 예제에서는 형식 정보만 검색하므로 메타데이터 사용 가능 여부는 `Browse` 정책 설정에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-192">Because the example simply retrieves type information, the availability of metadata is controlled by the `Browse` policy setting.</span></span>

 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]

 <span data-ttu-id="1d723-193">클래스의 메타 데이터는 <xref:System.Collections.Generic.List%601> .NET 네이티브 도구 체인에 의해 자동으로 포함 되지 않기 때문에이 예제에서는 런타임에 요청 된 멤버 정보를 표시 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-193">Because metadata for the <xref:System.Collections.Generic.List%601> class isn't automatically included by the .NET Native tool chain, the example fails to display the requested member information at run time.</span></span> <span data-ttu-id="1d723-194">필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-194">To provide the necessary metadata, add the following `<Type>` element to the runtime directives file.</span></span> <span data-ttu-id="1d723-195">여기서는 부모 [<Namespace\>](namespace-element-net-native.md) 요소를 제공했으므로 `<Type>` 요소에 정규화된 형식 이름을 제공하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-195">Note that, because we've provided a parent [<Namespace\>](namespace-element-net-native.md) element, we don't have to provide a fully qualified type name in the `<Type>` element.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="*Application*" Dynamic="Required All" />
      <Namespace Name ="System.Collections.Generic" >
        <Type Name="List`1" Browse="Required All" />
     </Namespace>
   </Application>
</Directives>
```

## <a name="example"></a><span data-ttu-id="1d723-196">예제</span><span class="sxs-lookup"><span data-stu-id="1d723-196">Example</span></span>

 <span data-ttu-id="1d723-197">다음 예제에서는 리플렉션을 사용하여 <xref:System.Reflection.PropertyInfo> 속성을 나타내는 <xref:System.String.Chars%2A?displayProperty=nameWithType> 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-197">The following example uses reflection to retrieve a <xref:System.Reflection.PropertyInfo> object that represents the <xref:System.String.Chars%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1d723-198">그런 다음 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드를 사용하여 문자열에서 7번째 문자의 값을 검색하고 문자열의 모든 문자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-198">It then uses the <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> method to retrieve the value of the seventh character in a string, and to display all the characters in the string.</span></span> <span data-ttu-id="1d723-199">예제의 변수는 `b` <xref:Windows.UI.Xaml.Controls.TextBlock> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-199">The variable `b` in the example is a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>

 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]

 <span data-ttu-id="1d723-200">개체에 대 한 메타 데이터 <xref:System.String> 를 사용할 수 없기 때문에 메서드를 호출 하면 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> <xref:System.NullReferenceException> 런타임에 .NET 네이티브 도구 체인을 사용 하 여 컴파일할 때 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-200">Because metadata for the <xref:System.String> object isn't available, the call to the <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> method throws a <xref:System.NullReferenceException> exception at run time when compiled with the .NET Native tool chain.</span></span> <span data-ttu-id="1d723-201">예외를 방지하고 필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d723-201">To eliminate the exception and provide the necessary metadata, add the following `<Type>` element to the runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
    <Type Name="System.String" Dynamic="Required Public"/> -->
  </Application>
</Directives>
```

## <a name="see-also"></a><span data-ttu-id="1d723-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d723-202">See also</span></span>

- [<span data-ttu-id="1d723-203">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="1d723-203">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="1d723-204">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="1d723-204">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="1d723-205">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="1d723-205">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
