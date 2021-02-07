---
description: '자세히 알아보기: <Application> 요소 (.NET 네이티브)'
title: <Application> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
ms.openlocfilehash: ebbc6292b5936e6b7d54666070b33df2da80f57f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747948"
---
# <a name="application-element-net-native"></a><span data-ttu-id="2f2c0-103">\<Application> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="2f2c0-103">\<Application> Element (.NET Native)</span></span>

<span data-ttu-id="2f2c0-104">런타임에 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버의 컨테이너로 사용되며, 앱의 모든 프로그램 요소에 대해 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-104">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time, and applies runtime reflection policy to all the program elements in an app.</span></span>  
  
 <span data-ttu-id="2f2c0-105">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-105">\<Directives> Element</span></span>  
<span data-ttu-id="2f2c0-106">\<Application> 요소 (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="2f2c0-106">\<Application> Element (rd.xml)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2c0-107">구문</span><span class="sxs-lookup"><span data-stu-id="2f2c0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f2c0-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-108">Attributes and Elements</span></span>  

 <span data-ttu-id="2f2c0-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-109">The following sections describe attributes, child elements, and parent elements.</span></span> <span data-ttu-id="2f2c0-110">자식 요소 표에서 정책은 런타임에 특정 프로그램 요소에 대해 제공되는 메타데이터의 종류를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-110">In the Child Elements table, policy refers to the kind of metadata that is made available for particular program elements at run time.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f2c0-111">특성</span><span class="sxs-lookup"><span data-stu-id="2f2c0-111">Attributes</span></span>  
  
|<span data-ttu-id="2f2c0-112">attribute</span><span class="sxs-lookup"><span data-stu-id="2f2c0-112">Attribute</span></span>|<span data-ttu-id="2f2c0-113">특성 유형</span><span class="sxs-lookup"><span data-stu-id="2f2c0-113">Attribute type</span></span>|<span data-ttu-id="2f2c0-114">설명</span><span class="sxs-lookup"><span data-stu-id="2f2c0-114">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="2f2c0-115">반사</span><span class="sxs-lookup"><span data-stu-id="2f2c0-115">Reflection</span></span>|<span data-ttu-id="2f2c0-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-116">Optional attribute.</span></span> <span data-ttu-id="2f2c0-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="2f2c0-118">반사</span><span class="sxs-lookup"><span data-stu-id="2f2c0-118">Reflection</span></span>|<span data-ttu-id="2f2c0-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-119">Optional attribute.</span></span> <span data-ttu-id="2f2c0-120">형식에 대한 정보 쿼리 또는 형식 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-120">Controls querying for information about or enumerating the types, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="2f2c0-121">반사</span><span class="sxs-lookup"><span data-stu-id="2f2c0-121">Reflection</span></span>|<span data-ttu-id="2f2c0-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-122">Optional attribute.</span></span> <span data-ttu-id="2f2c0-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="2f2c0-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="2f2c0-124">Serialization</span></span>|<span data-ttu-id="2f2c0-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-125">Optional attribute.</span></span> <span data-ttu-id="2f2c0-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="2f2c0-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="2f2c0-127">Serialization</span></span>|<span data-ttu-id="2f2c0-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-128">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="2f2c0-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="2f2c0-130">Serialization</span></span>|<span data-ttu-id="2f2c0-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-131">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="2f2c0-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="2f2c0-133">Serialization</span></span>|<span data-ttu-id="2f2c0-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-134">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="2f2c0-136">Interop</span><span class="sxs-lookup"><span data-stu-id="2f2c0-136">Interop</span></span>|<span data-ttu-id="2f2c0-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-137">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="2f2c0-139">Interop</span><span class="sxs-lookup"><span data-stu-id="2f2c0-139">Interop</span></span>|<span data-ttu-id="2f2c0-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-140">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="2f2c0-142">Interop</span><span class="sxs-lookup"><span data-stu-id="2f2c0-142">Interop</span></span>|<span data-ttu-id="2f2c0-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-143">Optional Attribute.</span></span> <span data-ttu-id="2f2c0-144">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-144">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="2f2c0-145">모든 특성</span><span class="sxs-lookup"><span data-stu-id="2f2c0-145">All attributes</span></span>  
  
|<span data-ttu-id="2f2c0-146">값</span><span class="sxs-lookup"><span data-stu-id="2f2c0-146">Value</span></span>|<span data-ttu-id="2f2c0-147">설명</span><span class="sxs-lookup"><span data-stu-id="2f2c0-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f2c0-148">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2f2c0-148">*policy_setting*</span></span>|<span data-ttu-id="2f2c0-149">앱의 형식에 적용할 이 정책에 대한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-149">The setting for this policy to apply to the types in the app.</span></span> <span data-ttu-id="2f2c0-150">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-150">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="2f2c0-151">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-151">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f2c0-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-152">Child Elements</span></span>  
  
|<span data-ttu-id="2f2c0-153">요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-153">Element</span></span>|<span data-ttu-id="2f2c0-154">설명</span><span class="sxs-lookup"><span data-stu-id="2f2c0-154">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="2f2c0-155">특정 어셈블리의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-155">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="2f2c0-156">특정 네임스페이스의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-156">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="2f2c0-157">클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-157">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="2f2c0-158">생성된 제네릭 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-158">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="2f2c0-159">예를 들어 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 요소를 사용 하 여 형식에 대 한 정책을 정의할 수 있습니다 `List<String>` .</span><span class="sxs-lookup"><span data-stu-id="2f2c0-159">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="2f2c0-160">특정 형식에 대한 메서드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-160">Applies policy to a method on a particular type.</span></span>|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|<span data-ttu-id="2f2c0-161">생성된 제네릭 메서드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-161">Applies policy to a constructed generic method.</span></span>|  
|[\<Property>](property-element-net-native.md)|<span data-ttu-id="2f2c0-162">특정 형식에 대한 속성에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-162">Applies policy to a property on a particular type.</span></span>|  
|[\<Field>](field-element-net-native.md)|<span data-ttu-id="2f2c0-163">특정 형식에 대한 필드에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-163">Applies policy to a field on a particular type.</span></span>|  
|[\<Event>](event-element-net-native.md)|<span data-ttu-id="2f2c0-164">특정 형식의 이벤트에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-164">Applies policy to an event on a particular type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f2c0-165">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-165">Parent Elements</span></span>  
  
|<span data-ttu-id="2f2c0-166">요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-166">Element</span></span>|<span data-ttu-id="2f2c0-167">설명</span><span class="sxs-lookup"><span data-stu-id="2f2c0-167">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="2f2c0-168">런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-168">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f2c0-169">설명</span><span class="sxs-lookup"><span data-stu-id="2f2c0-169">Remarks</span></span>  

 <span data-ttu-id="2f2c0-170">[\<Directives>](directives-element-net-native.md)요소는 0 개 또는 한 개의 요소를 포함할 수 있습니다 `<Application>` .</span><span class="sxs-lookup"><span data-stu-id="2f2c0-170">The [\<Directives>](directives-element-net-native.md) element can contain zero or one `<Application>` element.</span></span> <span data-ttu-id="2f2c0-171">단일 리플렉션 지시문 파일에 여러 `<Application>` 요소를 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-171">Multiple `<Application>` elements in a single reflection directives file are not supported.</span></span>  
  
 <span data-ttu-id="2f2c0-172">`<Application>` 요소는 다음 두 가지 방법 중 하나로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-172">The `<Application>` element can be used in one of two ways:</span></span>  
  
- <span data-ttu-id="2f2c0-173">런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-173">As a container to define the program elements whose metadata is needed at run time.</span></span> <span data-ttu-id="2f2c0-174">이 경우에는 `<Application>` 요소에 특성이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-174">In this case, the `<Application>` element need not have any attributes.</span></span> <span data-ttu-id="2f2c0-175">컴파일 타임에 컴파일러 도구는 .NET Framework 핵심 라이브러리를 비롯한 모든 라이브러리에서 `<Application>` 요소의 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-175">At compile time, compiler tools search all libraries, including .NET Framework core libraries, for program elements identified by child elements of the `<Application>` element.</span></span> <span data-ttu-id="2f2c0-176">반면, 컴파일러 도구는 요소로 지정 된 라이브러리 에서만 [\<Library>](library-element-net-native.md) 의 자식 요소로 식별 되는 프로그램 요소를 검색 합니다 [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="2f2c0-176">In contrast, compiler tools search only the library designated by the [\<Library>](library-element-net-native.md) element for program elements identified by the child elements of [\<Library>](library-element-net-native.md).</span></span>  
  
- <span data-ttu-id="2f2c0-177">리플렉션, serialization 및 interop에 대한 애플리케이션 수준 정책을 설정하는 요소로 사용.</span><span class="sxs-lookup"><span data-stu-id="2f2c0-177">As an element that sets application-wide policy for reflection, serialization, and interop.</span></span> <span data-ttu-id="2f2c0-178">요소의 특성은 `<Application>` 응용 프로그램 수준 정책을 정의 하며,이 정책은 또는 요소로 정의 된 자식 요소에 의해 재정의 될 수 있습니다 `<Application>` [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="2f2c0-178">The attributes of the `<Application>` element define application-wide policy, which may be overridden by the child elements defined by the `<Application>` or [\<Library>](library-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2c0-179">참조</span><span class="sxs-lookup"><span data-stu-id="2f2c0-179">See also</span></span>

- [<span data-ttu-id="2f2c0-180">\<Library> 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-180">\<Library> Element</span></span>](library-element-net-native.md)
- [<span data-ttu-id="2f2c0-181">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-181">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="2f2c0-182">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="2f2c0-182">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="2f2c0-183">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="2f2c0-183">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
