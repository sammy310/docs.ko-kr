---
title: <AttributeImplies> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 4171345bb5337436142128623abc7d183c4477ff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288114"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="a23fd-102">\<AttributeImplies> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="a23fd-102">\<AttributeImplies> Element (.NET Native)</span></span>

<span data-ttu-id="a23fd-103">포함 특성이 적용되는 코드 요소에 대한 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a23fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="a23fd-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a23fd-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a23fd-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a23fd-107">특성</span><span class="sxs-lookup"><span data-stu-id="a23fd-107">Attributes</span></span>  
  
|<span data-ttu-id="a23fd-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a23fd-108">Attribute</span></span>|<span data-ttu-id="a23fd-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="a23fd-109">Attribute type</span></span>|<span data-ttu-id="a23fd-110">Description</span><span class="sxs-lookup"><span data-stu-id="a23fd-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="a23fd-111">반사</span><span class="sxs-lookup"><span data-stu-id="a23fd-111">Reflection</span></span>|<span data-ttu-id="a23fd-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-112">Optional attribute.</span></span> <span data-ttu-id="a23fd-113">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="a23fd-114">반사</span><span class="sxs-lookup"><span data-stu-id="a23fd-114">Reflection</span></span>|<span data-ttu-id="a23fd-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-115">Optional attribute.</span></span> <span data-ttu-id="a23fd-116">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="a23fd-117">반사</span><span class="sxs-lookup"><span data-stu-id="a23fd-117">Reflection</span></span>|<span data-ttu-id="a23fd-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-118">Optional attribute.</span></span> <span data-ttu-id="a23fd-119">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="a23fd-120">Serialization</span><span class="sxs-lookup"><span data-stu-id="a23fd-120">Serialization</span></span>|<span data-ttu-id="a23fd-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-121">Optional attribute.</span></span> <span data-ttu-id="a23fd-122">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="a23fd-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="a23fd-123">Serialization</span></span>|<span data-ttu-id="a23fd-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-124">Optional attribute.</span></span> <span data-ttu-id="a23fd-125"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="a23fd-126">Serialization</span><span class="sxs-lookup"><span data-stu-id="a23fd-126">Serialization</span></span>|<span data-ttu-id="a23fd-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-127">Optional attribute.</span></span> <span data-ttu-id="a23fd-128"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="a23fd-129">Serialization</span><span class="sxs-lookup"><span data-stu-id="a23fd-129">Serialization</span></span>|<span data-ttu-id="a23fd-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-130">Optional attribute.</span></span> <span data-ttu-id="a23fd-131"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="a23fd-132">Interop</span><span class="sxs-lookup"><span data-stu-id="a23fd-132">Interop</span></span>|<span data-ttu-id="a23fd-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-133">Optional attribute.</span></span> <span data-ttu-id="a23fd-134">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="a23fd-135">Interop</span><span class="sxs-lookup"><span data-stu-id="a23fd-135">Interop</span></span>|<span data-ttu-id="a23fd-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-136">Optional attribute.</span></span> <span data-ttu-id="a23fd-137">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="a23fd-138">Interop</span><span class="sxs-lookup"><span data-stu-id="a23fd-138">Interop</span></span>|<span data-ttu-id="a23fd-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-139">Optional attribute.</span></span> <span data-ttu-id="a23fd-140">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="a23fd-141">모든 특성</span><span class="sxs-lookup"><span data-stu-id="a23fd-141">All attributes</span></span>  
  
|<span data-ttu-id="a23fd-142">값</span><span class="sxs-lookup"><span data-stu-id="a23fd-142">Value</span></span>|<span data-ttu-id="a23fd-143">Description</span><span class="sxs-lookup"><span data-stu-id="a23fd-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a23fd-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="a23fd-144">*policy_setting*</span></span>|<span data-ttu-id="a23fd-145">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="a23fd-146">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="a23fd-147">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a23fd-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a23fd-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-148">Child Elements</span></span>  

 <span data-ttu-id="a23fd-149">없음</span><span class="sxs-lookup"><span data-stu-id="a23fd-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a23fd-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-150">Parent Elements</span></span>  
  
|<span data-ttu-id="a23fd-151">요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-151">Element</span></span>|<span data-ttu-id="a23fd-152">Description</span><span class="sxs-lookup"><span data-stu-id="a23fd-152">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="a23fd-153">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-153">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a23fd-154">설명</span><span class="sxs-lookup"><span data-stu-id="a23fd-154">Remarks</span></span>  

 <span data-ttu-id="a23fd-155">`<AttributeImplies>` 요소는 포함 형식이 특성(<xref:System.Attribute?displayProperty=nameWithType>에서 파생되는 클래스)인 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-155">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="a23fd-156">특성이 특정 프로그램 요소에 적용되면 `<AttributeImplies>` 요소로 정의된 정책이 해당 프로그램 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-156">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="a23fd-157">리플렉션, serialization 및 interop 특성은 모두 선택적 항목이지만 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23fd-157">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23fd-158">참조</span><span class="sxs-lookup"><span data-stu-id="a23fd-158">See also</span></span>

- [<span data-ttu-id="a23fd-159">\<Type> 요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-159">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="a23fd-160">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="a23fd-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="a23fd-161">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="a23fd-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="a23fd-162">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="a23fd-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
