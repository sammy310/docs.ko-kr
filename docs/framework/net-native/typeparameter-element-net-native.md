---
title: <TypeParameter>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: c69b535f3a01c287d30189138130066fc10a77e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128918"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="b8c43-102">\<TypeParameter>요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="b8c43-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="b8c43-103">메서드로 전달된 Type 인수가 나타내는 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8c43-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8c43-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8c43-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8c43-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b8c43-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8c43-107">특성</span><span class="sxs-lookup"><span data-stu-id="b8c43-107">Attributes</span></span>  
  
|<span data-ttu-id="b8c43-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b8c43-108">Attribute</span></span>|<span data-ttu-id="b8c43-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="b8c43-109">Attribute type</span></span>|<span data-ttu-id="b8c43-110">Description</span><span class="sxs-lookup"><span data-stu-id="b8c43-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b8c43-111">일반</span><span class="sxs-lookup"><span data-stu-id="b8c43-111">General</span></span>|<span data-ttu-id="b8c43-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-112">Required attribute.</span></span> <span data-ttu-id="b8c43-113"><xref:System.Type> 형식의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b8c43-114">예를 들어 메서드 시그니처 `Type.GetInterfaceMap(Type interfaceType)`의 경우 `Name` 특성의 값은 "interfaceType"입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="b8c43-115">반사</span><span class="sxs-lookup"><span data-stu-id="b8c43-115">Reflection</span></span>|<span data-ttu-id="b8c43-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-116">Optional attribute.</span></span> <span data-ttu-id="b8c43-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b8c43-118">반사</span><span class="sxs-lookup"><span data-stu-id="b8c43-118">Reflection</span></span>|<span data-ttu-id="b8c43-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-119">Optional attribute.</span></span> <span data-ttu-id="b8c43-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b8c43-121">반사</span><span class="sxs-lookup"><span data-stu-id="b8c43-121">Reflection</span></span>|<span data-ttu-id="b8c43-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-122">Optional attribute.</span></span> <span data-ttu-id="b8c43-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b8c43-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="b8c43-124">Serialization</span></span>|<span data-ttu-id="b8c43-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-125">Optional attribute.</span></span> <span data-ttu-id="b8c43-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b8c43-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="b8c43-127">Serialization</span></span>|<span data-ttu-id="b8c43-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-128">Optional attribute.</span></span> <span data-ttu-id="b8c43-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b8c43-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="b8c43-130">Serialization</span></span>|<span data-ttu-id="b8c43-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-131">Optional attribute.</span></span> <span data-ttu-id="b8c43-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b8c43-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="b8c43-133">Serialization</span></span>|<span data-ttu-id="b8c43-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-134">Optional attribute.</span></span> <span data-ttu-id="b8c43-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b8c43-136">Interop</span><span class="sxs-lookup"><span data-stu-id="b8c43-136">Interop</span></span>|<span data-ttu-id="b8c43-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-137">Optional attribute.</span></span> <span data-ttu-id="b8c43-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b8c43-139">Interop</span><span class="sxs-lookup"><span data-stu-id="b8c43-139">Interop</span></span>|<span data-ttu-id="b8c43-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-140">Optional attribute.</span></span> <span data-ttu-id="b8c43-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b8c43-142">Interop</span><span class="sxs-lookup"><span data-stu-id="b8c43-142">Interop</span></span>|<span data-ttu-id="b8c43-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-143">Optional attribute.</span></span> <span data-ttu-id="b8c43-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b8c43-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="b8c43-145">Name attribute</span></span>  
  
|<span data-ttu-id="b8c43-146">값</span><span class="sxs-lookup"><span data-stu-id="b8c43-146">Value</span></span>|<span data-ttu-id="b8c43-147">Description</span><span class="sxs-lookup"><span data-stu-id="b8c43-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8c43-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b8c43-148">*parameter_name*</span></span>|<span data-ttu-id="b8c43-149"><xref:System.Type> 형식의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b8c43-150">예를 들어 메서드 시그니처 `Type.GetInterfaceMap(Type interfaceType)`의 경우 `Name` 특성의 값은 "interfaceType"입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b8c43-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="b8c43-151">All other attributes</span></span>  
  
|<span data-ttu-id="b8c43-152">값</span><span class="sxs-lookup"><span data-stu-id="b8c43-152">Value</span></span>|<span data-ttu-id="b8c43-153">Description</span><span class="sxs-lookup"><span data-stu-id="b8c43-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8c43-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b8c43-154">*policy_setting*</span></span>|<span data-ttu-id="b8c43-155">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="b8c43-156">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b8c43-157">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8c43-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8c43-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8c43-158">Child Elements</span></span>  
 <span data-ttu-id="b8c43-159">없음</span><span class="sxs-lookup"><span data-stu-id="b8c43-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8c43-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8c43-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b8c43-161">요소</span><span class="sxs-lookup"><span data-stu-id="b8c43-161">Element</span></span>|<span data-ttu-id="b8c43-162">Description</span><span class="sxs-lookup"><span data-stu-id="b8c43-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="b8c43-163">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8c43-164">설명</span><span class="sxs-lookup"><span data-stu-id="b8c43-164">Remarks</span></span>  
 <span data-ttu-id="b8c43-165">`<TypeParameter>`요소는 [\<Parameter>](parameter-element-net-native.md) 형식의 매개 변수에만 적용할 수 있다는 점을 제외 하 고 요소와 유사 합니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="b8c43-165">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="b8c43-166">이 요소는 `Name` 특성으로 지정된 형식 인수에 의해 런타임에 표시되는 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-166">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="b8c43-167">예를 들어 NewtonSoft JSON serializer는 정적 `JsonConvert.DeserializeObject(String value, Type type)` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-167">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="b8c43-168">다음 리플렉션 지시문은</span><span class="sxs-lookup"><span data-stu-id="b8c43-168">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="b8c43-169">`type` 인수가 나타내는 런타임 형식에 대한 메타데이터를 serialization에 사용할 수 있도록 제공해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-169">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="b8c43-170">이러한 런타임 지시문이 다음 소스 코드를 포함하는 프로젝트에 적용되는 경우</span><span class="sxs-lookup"><span data-stu-id="b8c43-170">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="b8c43-171">리플렉션 지시문은 런타임에 `StockQuote` 형식의 메타데이터를 NewtonSoft JSON serializer에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8c43-171">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c43-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8c43-172">See also</span></span>

- [<span data-ttu-id="b8c43-173">\<Method>요소인</span><span class="sxs-lookup"><span data-stu-id="b8c43-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="b8c43-174">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="b8c43-174">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b8c43-175">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b8c43-175">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="b8c43-176">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="b8c43-176">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
