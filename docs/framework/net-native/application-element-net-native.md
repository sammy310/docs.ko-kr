---
title: <Application>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
ms.openlocfilehash: e26826b3d8674b536ab0897182da58bc02cfd00b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128525"
---
# <a name="application-element-net-native"></a><span data-ttu-id="72519-102">\<Application>요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="72519-102">\<Application> Element (.NET Native)</span></span>
<span data-ttu-id="72519-103">런타임에 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버의 컨테이너로 사용되며, 앱의 모든 프로그램 요소에 대해 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-103">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time, and applies runtime reflection policy to all the program elements in an app.</span></span>  
  
 <span data-ttu-id="72519-104">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="72519-104">\<Directives> Element</span></span>  
<span data-ttu-id="72519-105">\<Application>요소 (rd .xml)</span><span class="sxs-lookup"><span data-stu-id="72519-105">\<Application> Element (rd.xml)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72519-106">구문</span><span class="sxs-lookup"><span data-stu-id="72519-106">Syntax</span></span>  
  
```xml  
<Application Activate="policy_setting"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72519-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="72519-107">Attributes and Elements</span></span>  
 <span data-ttu-id="72519-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-108">The following sections describe attributes, child elements, and parent elements.</span></span> <span data-ttu-id="72519-109">자식 요소 표에서 정책은 런타임에 특정 프로그램 요소에 대해 제공되는 메타데이터의 종류를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-109">In the Child Elements table, policy refers to the kind of metadata that is made available for particular program elements at run time.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72519-110">특성</span><span class="sxs-lookup"><span data-stu-id="72519-110">Attributes</span></span>  
  
|<span data-ttu-id="72519-111">attribute</span><span class="sxs-lookup"><span data-stu-id="72519-111">Attribute</span></span>|<span data-ttu-id="72519-112">특성 유형</span><span class="sxs-lookup"><span data-stu-id="72519-112">Attribute type</span></span>|<span data-ttu-id="72519-113">Description</span><span class="sxs-lookup"><span data-stu-id="72519-113">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="72519-114">반사</span><span class="sxs-lookup"><span data-stu-id="72519-114">Reflection</span></span>|<span data-ttu-id="72519-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-115">Optional attribute.</span></span> <span data-ttu-id="72519-116">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="72519-117">반사</span><span class="sxs-lookup"><span data-stu-id="72519-117">Reflection</span></span>|<span data-ttu-id="72519-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-118">Optional attribute.</span></span> <span data-ttu-id="72519-119">형식에 대한 정보 쿼리 또는 형식 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72519-119">Controls querying for information about or enumerating the types, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="72519-120">반사</span><span class="sxs-lookup"><span data-stu-id="72519-120">Reflection</span></span>|<span data-ttu-id="72519-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-121">Optional attribute.</span></span> <span data-ttu-id="72519-122">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="72519-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="72519-123">Serialization</span></span>|<span data-ttu-id="72519-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-124">Optional attribute.</span></span> <span data-ttu-id="72519-125">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="72519-126">Serialization</span><span class="sxs-lookup"><span data-stu-id="72519-126">Serialization</span></span>|<span data-ttu-id="72519-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-127">Optional Attribute.</span></span> <span data-ttu-id="72519-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="72519-129">Serialization</span><span class="sxs-lookup"><span data-stu-id="72519-129">Serialization</span></span>|<span data-ttu-id="72519-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-130">Optional Attribute.</span></span> <span data-ttu-id="72519-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="72519-132">Serialization</span><span class="sxs-lookup"><span data-stu-id="72519-132">Serialization</span></span>|<span data-ttu-id="72519-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-133">Optional Attribute.</span></span> <span data-ttu-id="72519-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="72519-135">Interop</span><span class="sxs-lookup"><span data-stu-id="72519-135">Interop</span></span>|<span data-ttu-id="72519-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-136">Optional Attribute.</span></span> <span data-ttu-id="72519-137">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="72519-138">Interop</span><span class="sxs-lookup"><span data-stu-id="72519-138">Interop</span></span>|<span data-ttu-id="72519-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-139">Optional Attribute.</span></span> <span data-ttu-id="72519-140">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="72519-141">Interop</span><span class="sxs-lookup"><span data-stu-id="72519-141">Interop</span></span>|<span data-ttu-id="72519-142">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-142">Optional Attribute.</span></span> <span data-ttu-id="72519-143">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="72519-144">모든 특성</span><span class="sxs-lookup"><span data-stu-id="72519-144">All attributes</span></span>  
  
|<span data-ttu-id="72519-145">값</span><span class="sxs-lookup"><span data-stu-id="72519-145">Value</span></span>|<span data-ttu-id="72519-146">Description</span><span class="sxs-lookup"><span data-stu-id="72519-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72519-147">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="72519-147">*policy_setting*</span></span>|<span data-ttu-id="72519-148">앱의 형식에 적용할 이 정책에 대한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-148">The setting for this policy to apply to the types in the app.</span></span> <span data-ttu-id="72519-149">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-149">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="72519-150">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72519-150">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72519-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="72519-151">Child Elements</span></span>  
  
|<span data-ttu-id="72519-152">요소</span><span class="sxs-lookup"><span data-stu-id="72519-152">Element</span></span>|<span data-ttu-id="72519-153">Description</span><span class="sxs-lookup"><span data-stu-id="72519-153">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="72519-154">특정 어셈블리의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-154">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="72519-155">특정 네임스페이스의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-155">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="72519-156">클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-156">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="72519-157">생성된 제네릭 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-157">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="72519-158">예를 들어 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 요소를 사용 하 여 형식에 대 한 정책을 정의할 수 있습니다 `List<String>` .</span><span class="sxs-lookup"><span data-stu-id="72519-158">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="72519-159">특정 형식에 대한 메서드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-159">Applies policy to a method on a particular type.</span></span>|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|<span data-ttu-id="72519-160">생성된 제네릭 메서드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-160">Applies policy to a constructed generic method.</span></span>|  
|[\<Property>](property-element-net-native.md)|<span data-ttu-id="72519-161">특정 형식에 대한 속성에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-161">Applies policy to a property on a particular type.</span></span>|  
|[\<Field>](field-element-net-native.md)|<span data-ttu-id="72519-162">특정 형식에 대한 필드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-162">Applies policy to a field on a particular type.</span></span>|  
|[\<Event>](event-element-net-native.md)|<span data-ttu-id="72519-163">특정 형식의 이벤트에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-163">Applies policy to an event on a particular type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72519-164">부모 요소</span><span class="sxs-lookup"><span data-stu-id="72519-164">Parent Elements</span></span>  
  
|<span data-ttu-id="72519-165">요소</span><span class="sxs-lookup"><span data-stu-id="72519-165">Element</span></span>|<span data-ttu-id="72519-166">Description</span><span class="sxs-lookup"><span data-stu-id="72519-166">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="72519-167">런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="72519-167">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72519-168">설명</span><span class="sxs-lookup"><span data-stu-id="72519-168">Remarks</span></span>  
 <span data-ttu-id="72519-169">[\<Directives>](directives-element-net-native.md)요소는 0 개 또는 한 개의 요소를 포함할 수 있습니다 `<Application>` .</span><span class="sxs-lookup"><span data-stu-id="72519-169">The [\<Directives>](directives-element-net-native.md) element can contain zero or one `<Application>` element.</span></span> <span data-ttu-id="72519-170">단일 리플렉션 지시문 파일에 여러 `<Application>` 요소를 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72519-170">Multiple `<Application>` elements in a single reflection directives file are not supported.</span></span>  
  
 <span data-ttu-id="72519-171">`<Application>` 요소는 다음 두 가지 방법 중 하나로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72519-171">The `<Application>` element can be used in one of two ways:</span></span>  
  
- <span data-ttu-id="72519-172">런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용.</span><span class="sxs-lookup"><span data-stu-id="72519-172">As a container to define the program elements whose metadata is needed at run time.</span></span> <span data-ttu-id="72519-173">이 경우에는 `<Application>` 요소에 특성이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72519-173">In this case, the `<Application>` element need not have any attributes.</span></span> <span data-ttu-id="72519-174">컴파일 타임에 컴파일러 도구는 .NET Framework 핵심 라이브러리를 비롯한 모든 라이브러리에서 `<Application>` 요소의 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="72519-174">At compile time, compiler tools search all libraries, including .NET Framework core libraries, for program elements identified by child elements of the `<Application>` element.</span></span> <span data-ttu-id="72519-175">반면, 컴파일러 도구는 요소로 지정 된 라이브러리 에서만 [\<Library>](library-element-net-native.md) 의 자식 요소로 식별 되는 프로그램 요소를 검색 합니다 [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="72519-175">In contrast, compiler tools search only the library designated by the [\<Library>](library-element-net-native.md) element for program elements identified by the child elements of [\<Library>](library-element-net-native.md).</span></span>  
  
- <span data-ttu-id="72519-176">리플렉션, serialization 및 interop에 대한 애플리케이션 수준 정책을 설정하는 요소로 사용.</span><span class="sxs-lookup"><span data-stu-id="72519-176">As an element that sets application-wide policy for reflection, serialization, and interop.</span></span> <span data-ttu-id="72519-177">요소의 특성은 `<Application>` 응용 프로그램 수준 정책을 정의 하며,이 정책은 또는 요소로 정의 된 자식 요소에 의해 재정의 될 수 있습니다 `<Application>` [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="72519-177">The attributes of the `<Application>` element define application-wide policy, which may be overridden by the child elements defined by the `<Application>` or [\<Library>](library-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72519-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72519-178">See also</span></span>

- [<span data-ttu-id="72519-179">\<Library>요소인</span><span class="sxs-lookup"><span data-stu-id="72519-179">\<Library> Element</span></span>](library-element-net-native.md)
- [<span data-ttu-id="72519-180">\<Directives>요소인</span><span class="sxs-lookup"><span data-stu-id="72519-180">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="72519-181">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="72519-181">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="72519-182">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="72519-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
