---
title: <Namespace>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: 06d88a7b0f95c7c1dbe98818b847c92e08a57a19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180962"
---
# <a name="namespace-element-net-native"></a><span data-ttu-id="aab18-102">\<Namespace>요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="aab18-102">\<Namespace> Element (.NET Native)</span></span>
<span data-ttu-id="aab18-103">지정된 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-103">Applies runtime reflection policy to all the types in a specified namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab18-104">구문</span><span class="sxs-lookup"><span data-stu-id="aab18-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aab18-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aab18-105">Attributes and Elements</span></span>  
 <span data-ttu-id="aab18-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aab18-107">특성</span><span class="sxs-lookup"><span data-stu-id="aab18-107">Attributes</span></span>  
  
|<span data-ttu-id="aab18-108">attribute</span><span class="sxs-lookup"><span data-stu-id="aab18-108">Attribute</span></span>|<span data-ttu-id="aab18-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="aab18-109">Attribute type</span></span>|<span data-ttu-id="aab18-110">Description</span><span class="sxs-lookup"><span data-stu-id="aab18-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="aab18-111">일반</span><span class="sxs-lookup"><span data-stu-id="aab18-111">General</span></span>|<span data-ttu-id="aab18-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-112">Required attribute.</span></span> <span data-ttu-id="aab18-113">네임스페이스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-113">Specifies the name of the namespace.</span></span>|  
|`Activate`|<span data-ttu-id="aab18-114">반사</span><span class="sxs-lookup"><span data-stu-id="aab18-114">Reflection</span></span>|<span data-ttu-id="aab18-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-115">Optional attribute.</span></span> <span data-ttu-id="aab18-116">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="aab18-117">반사</span><span class="sxs-lookup"><span data-stu-id="aab18-117">Reflection</span></span>|<span data-ttu-id="aab18-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-118">Optional attribute.</span></span> <span data-ttu-id="aab18-119">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="aab18-120">반사</span><span class="sxs-lookup"><span data-stu-id="aab18-120">Reflection</span></span>|<span data-ttu-id="aab18-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-121">Optional attribute.</span></span> <span data-ttu-id="aab18-122">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="aab18-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="aab18-123">Serialization</span></span>|<span data-ttu-id="aab18-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-124">Optional attribute.</span></span> <span data-ttu-id="aab18-125">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="aab18-126">Serialization</span><span class="sxs-lookup"><span data-stu-id="aab18-126">Serialization</span></span>|<span data-ttu-id="aab18-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-127">Optional attribute.</span></span> <span data-ttu-id="aab18-128"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="aab18-129">Serialization</span><span class="sxs-lookup"><span data-stu-id="aab18-129">Serialization</span></span>|<span data-ttu-id="aab18-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-130">Optional attribute.</span></span> <span data-ttu-id="aab18-131"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="aab18-132">Serialization</span><span class="sxs-lookup"><span data-stu-id="aab18-132">Serialization</span></span>|<span data-ttu-id="aab18-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-133">Optional attribute.</span></span> <span data-ttu-id="aab18-134"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="aab18-135">Interop</span><span class="sxs-lookup"><span data-stu-id="aab18-135">Interop</span></span>|<span data-ttu-id="aab18-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-136">Optional attribute.</span></span> <span data-ttu-id="aab18-137">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="aab18-138">Interop</span><span class="sxs-lookup"><span data-stu-id="aab18-138">Interop</span></span>|<span data-ttu-id="aab18-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-139">Optional attribute.</span></span> <span data-ttu-id="aab18-140">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="aab18-141">Interop</span><span class="sxs-lookup"><span data-stu-id="aab18-141">Interop</span></span>|<span data-ttu-id="aab18-142">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-142">Optional attribute.</span></span> <span data-ttu-id="aab18-143">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="aab18-144">Name 특성</span><span class="sxs-lookup"><span data-stu-id="aab18-144">Name attribute</span></span>  
  
|<span data-ttu-id="aab18-145">값</span><span class="sxs-lookup"><span data-stu-id="aab18-145">Value</span></span>|<span data-ttu-id="aab18-146">Description</span><span class="sxs-lookup"><span data-stu-id="aab18-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aab18-147">*namespace_name*</span><span class="sxs-lookup"><span data-stu-id="aab18-147">*namespace_name*</span></span>|<span data-ttu-id="aab18-148">네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-148">The namespace name.</span></span> <span data-ttu-id="aab18-149">\<Namespace>요소가 [\<Application>](application-element-net-native.md) , 또는 요소의 자식인 경우 namespace_name는 정규화 [\<Library>](library-element-net-native.md) [\<Assembly>](assembly-element-net-native.md) 된 네임 스페이스 이름 *namespace_name* 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-149">If the \<Namespace> element is a child of an [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md), or [\<Assembly>](assembly-element-net-native.md) element, *namespace_name* must be a fully qualified namespace name.</span></span> <span data-ttu-id="aab18-150">\<Namespace>요소가 다른 요소의 자식인 경우 \<Namespace> *namespace_name* 은 상대 네임 스페이스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-150">If the \<Namespace> element is a child of another \<Namespace> element, *namespace_name* must be a relative namespace name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="aab18-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="aab18-151">All other attributes</span></span>  
  
|<span data-ttu-id="aab18-152">값</span><span class="sxs-lookup"><span data-stu-id="aab18-152">Value</span></span>|<span data-ttu-id="aab18-153">Description</span><span class="sxs-lookup"><span data-stu-id="aab18-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aab18-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="aab18-154">*policy_setting*</span></span>|<span data-ttu-id="aab18-155">네임스페이스의 모든 형식에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-155">The setting to apply to this policy type for all types in the namespace.</span></span> <span data-ttu-id="aab18-156">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="aab18-157">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab18-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aab18-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aab18-158">Child Elements</span></span>  
  
|<span data-ttu-id="aab18-159">요소</span><span class="sxs-lookup"><span data-stu-id="aab18-159">Element</span></span>|<span data-ttu-id="aab18-160">Description</span><span class="sxs-lookup"><span data-stu-id="aab18-160">Description</span></span>|  
|-------------|-----------------|  
|`<Namespace>`|<span data-ttu-id="aab18-161">부모 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-161">Applies runtime reflection policy to all types in a parent namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="aab18-162">형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-162">Applies reflection policy to a type.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="aab18-163">생성된 제네릭 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-163">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aab18-164">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aab18-164">Parent Elements</span></span>  
  
|<span data-ttu-id="aab18-165">요소</span><span class="sxs-lookup"><span data-stu-id="aab18-165">Element</span></span>|<span data-ttu-id="aab18-166">Description</span><span class="sxs-lookup"><span data-stu-id="aab18-166">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="aab18-167">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-167">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="aab18-168">요소에는 [\<Application>](application-element-net-native.md) 요소가 0 개, 1 개 또는 그 이상 있을 수 있습니다 [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="aab18-168">The [\<Application>](application-element-net-native.md) element can have zero, one, or more [\<Assembly>](assembly-element-net-native.md) elements.</span></span>|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="aab18-169">지정된 어셈블리의 모든 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-169">Applies runtime reflection policy to all the types in a specified assembly.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="aab18-170">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-170">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="aab18-171">[\<Library>](library-element-net-native.md)요소는 0 개 또는 한 개의 요소를 포함할 수 있습니다 [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="aab18-171">The [\<Library>](library-element-net-native.md) element can have zero or one [\<Assembly>](assembly-element-net-native.md) element.</span></span>|  
|`<Namespace>`|<span data-ttu-id="aab18-172">부모 네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-172">Applies reflection policy to all types in a parent namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aab18-173">설명</span><span class="sxs-lookup"><span data-stu-id="aab18-173">Remarks</span></span>  
 <span data-ttu-id="aab18-174">`Activate`, `Browse`, `Dynamic` 및 `Serialize` 특성은 모두 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-174">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="aab18-175">아무 특성도 없으면 `<Namespace>` 요소는 자식 요소의 컨테이너로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-175">If none are present, the `<Namespace>` element serves only as a container for child elements.</span></span> <span data-ttu-id="aab18-176">특성이 있으면 `<Namespace>` 요소가 지정된 네임스페이스의 모든 형식에 대해 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab18-176">If they are present, the `<Namespace>` element applies runtime reflection policy to all the types in the specified namespace.</span></span>  
  
 <span data-ttu-id="aab18-177">요소의 자식인 경우 요소 [\<Assembly>](assembly-element-net-native.md) 는 `<Namespace>` 요소에 정의 된 런타임 리플렉션 정책을 재정의 합니다 [\<Assembly>](assembly-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="aab18-177">When it is a child of the [\<Assembly>](assembly-element-net-native.md) element, the `<Namespace>` element overrides the runtime reflection policy defined by the  [\<Assembly>](assembly-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab18-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aab18-178">See also</span></span>

- [<span data-ttu-id="aab18-179">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="aab18-179">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="aab18-180">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="aab18-180">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="aab18-181">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="aab18-181">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
