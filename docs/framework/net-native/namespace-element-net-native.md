---
description: '자세히 알아보기: <Namespace> 요소 (.NET 네이티브)'
title: <Namespace> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: c24f78d8d9fd59258391e9dd5e59988675163b49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738613"
---
# <a name="namespace-element-net-native"></a><span data-ttu-id="dca07-103">\<Namespace> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="dca07-103">\<Namespace> Element (.NET Native)</span></span>

<span data-ttu-id="dca07-104">지정된 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-104">Applies runtime reflection policy to all the types in a specified namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca07-105">구문</span><span class="sxs-lookup"><span data-stu-id="dca07-105">Syntax</span></span>  
  
```xml  
<Namespace Name="namespace_name"
           Activate="policy_type"
           Browse="policy_type"  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dca07-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dca07-106">Attributes and Elements</span></span>  

 <span data-ttu-id="dca07-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dca07-108">특성</span><span class="sxs-lookup"><span data-stu-id="dca07-108">Attributes</span></span>  
  
|<span data-ttu-id="dca07-109">attribute</span><span class="sxs-lookup"><span data-stu-id="dca07-109">Attribute</span></span>|<span data-ttu-id="dca07-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="dca07-110">Attribute type</span></span>|<span data-ttu-id="dca07-111">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="dca07-112">일반</span><span class="sxs-lookup"><span data-stu-id="dca07-112">General</span></span>|<span data-ttu-id="dca07-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-113">Required attribute.</span></span> <span data-ttu-id="dca07-114">네임스페이스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-114">Specifies the name of the namespace.</span></span>|  
|`Activate`|<span data-ttu-id="dca07-115">반사</span><span class="sxs-lookup"><span data-stu-id="dca07-115">Reflection</span></span>|<span data-ttu-id="dca07-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-116">Optional attribute.</span></span> <span data-ttu-id="dca07-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="dca07-118">반사</span><span class="sxs-lookup"><span data-stu-id="dca07-118">Reflection</span></span>|<span data-ttu-id="dca07-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-119">Optional attribute.</span></span> <span data-ttu-id="dca07-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="dca07-121">반사</span><span class="sxs-lookup"><span data-stu-id="dca07-121">Reflection</span></span>|<span data-ttu-id="dca07-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-122">Optional attribute.</span></span> <span data-ttu-id="dca07-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="dca07-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="dca07-124">Serialization</span></span>|<span data-ttu-id="dca07-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-125">Optional attribute.</span></span> <span data-ttu-id="dca07-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="dca07-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="dca07-127">Serialization</span></span>|<span data-ttu-id="dca07-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-128">Optional attribute.</span></span> <span data-ttu-id="dca07-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="dca07-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="dca07-130">Serialization</span></span>|<span data-ttu-id="dca07-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-131">Optional attribute.</span></span> <span data-ttu-id="dca07-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="dca07-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="dca07-133">Serialization</span></span>|<span data-ttu-id="dca07-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-134">Optional attribute.</span></span> <span data-ttu-id="dca07-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="dca07-136">Interop</span><span class="sxs-lookup"><span data-stu-id="dca07-136">Interop</span></span>|<span data-ttu-id="dca07-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-137">Optional attribute.</span></span> <span data-ttu-id="dca07-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="dca07-139">Interop</span><span class="sxs-lookup"><span data-stu-id="dca07-139">Interop</span></span>|<span data-ttu-id="dca07-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-140">Optional attribute.</span></span> <span data-ttu-id="dca07-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="dca07-142">Interop</span><span class="sxs-lookup"><span data-stu-id="dca07-142">Interop</span></span>|<span data-ttu-id="dca07-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-143">Optional attribute.</span></span> <span data-ttu-id="dca07-144">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-144">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="dca07-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="dca07-145">Name attribute</span></span>  
  
|<span data-ttu-id="dca07-146">값</span><span class="sxs-lookup"><span data-stu-id="dca07-146">Value</span></span>|<span data-ttu-id="dca07-147">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dca07-148">*namespace_name*</span><span class="sxs-lookup"><span data-stu-id="dca07-148">*namespace_name*</span></span>|<span data-ttu-id="dca07-149">네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-149">The namespace name.</span></span> <span data-ttu-id="dca07-150">\<Namespace>요소가 [\<Application>](application-element-net-native.md) , 또는 요소의 자식인 경우 namespace_name는 정규화 [\<Library>](library-element-net-native.md) [\<Assembly>](assembly-element-net-native.md) 된 네임 스페이스 이름  이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-150">If the \<Namespace> element is a child of an [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md), or [\<Assembly>](assembly-element-net-native.md) element, *namespace_name* must be a fully qualified namespace name.</span></span> <span data-ttu-id="dca07-151">\<Namespace>요소가 다른 요소의 자식인 경우 \<Namespace> *namespace_name* 은 상대 네임 스페이스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-151">If the \<Namespace> element is a child of another \<Namespace> element, *namespace_name* must be a relative namespace name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="dca07-152">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="dca07-152">All other attributes</span></span>  
  
|<span data-ttu-id="dca07-153">값</span><span class="sxs-lookup"><span data-stu-id="dca07-153">Value</span></span>|<span data-ttu-id="dca07-154">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dca07-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="dca07-155">*policy_setting*</span></span>|<span data-ttu-id="dca07-156">네임스페이스의 모든 형식에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-156">The setting to apply to this policy type for all types in the namespace.</span></span> <span data-ttu-id="dca07-157">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-157">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="dca07-158">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dca07-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dca07-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dca07-159">Child Elements</span></span>  
  
|<span data-ttu-id="dca07-160">요소</span><span class="sxs-lookup"><span data-stu-id="dca07-160">Element</span></span>|<span data-ttu-id="dca07-161">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-161">Description</span></span>|  
|-------------|-----------------|  
|`<Namespace>`|<span data-ttu-id="dca07-162">부모 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-162">Applies runtime reflection policy to all types in a parent namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="dca07-163">형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-163">Applies reflection policy to a type.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="dca07-164">생성된 제네릭 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-164">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dca07-165">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dca07-165">Parent Elements</span></span>  
  
|<span data-ttu-id="dca07-166">요소</span><span class="sxs-lookup"><span data-stu-id="dca07-166">Element</span></span>|<span data-ttu-id="dca07-167">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-167">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="dca07-168">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-168">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="dca07-169">요소에는 [\<Application>](application-element-net-native.md) 요소가 0 개, 1 개 또는 그 이상 있을 수 있습니다 [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="dca07-169">The [\<Application>](application-element-net-native.md) element can have zero, one, or more [\<Assembly>](assembly-element-net-native.md) elements.</span></span>|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="dca07-170">지정된 어셈블리의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-170">Applies runtime reflection policy to all the types in a specified assembly.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="dca07-171">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-171">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="dca07-172">[\<Library>](library-element-net-native.md)요소는 0 개 또는 한 개의 요소를 포함할 수 있습니다 [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="dca07-172">The [\<Library>](library-element-net-native.md) element can have zero or one [\<Assembly>](assembly-element-net-native.md) element.</span></span>|  
|`<Namespace>`|<span data-ttu-id="dca07-173">부모 네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-173">Applies reflection policy to all types in a parent namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dca07-174">설명</span><span class="sxs-lookup"><span data-stu-id="dca07-174">Remarks</span></span>  

 <span data-ttu-id="dca07-175">`Activate`, `Browse`, `Dynamic` 및 `Serialize` 특성은 모두 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-175">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="dca07-176">아무 특성도 없으면 `<Namespace>` 요소는 자식 요소의 컨테이너로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-176">If none are present, the `<Namespace>` element serves only as a container for child elements.</span></span> <span data-ttu-id="dca07-177">특성이 있으면 `<Namespace>` 요소가 지정된 네임스페이스의 모든 형식에 대해 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca07-177">If they are present, the `<Namespace>` element applies runtime reflection policy to all the types in the specified namespace.</span></span>  
  
 <span data-ttu-id="dca07-178">요소의 자식인 경우 요소 [\<Assembly>](assembly-element-net-native.md) 는 `<Namespace>` 요소에 정의 된 런타임 리플렉션 정책을 재정의 합니다  [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="dca07-178">When it is a child of the [\<Assembly>](assembly-element-net-native.md) element, the `<Namespace>` element overrides the runtime reflection policy defined by the  [\<Assembly>](assembly-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca07-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dca07-179">See also</span></span>

- [<span data-ttu-id="dca07-180">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="dca07-180">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="dca07-181">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="dca07-181">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="dca07-182">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="dca07-182">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
