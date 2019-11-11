---
title: <GenericParameter> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: d0b18211206a8f9d4365ab3affe6d1c376003348
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128428"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="5bcd8-102">\<GenericParameter > 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="5bcd8-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="5bcd8-103">제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcd8-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bcd8-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bcd8-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5bcd8-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bcd8-107">특성</span><span class="sxs-lookup"><span data-stu-id="5bcd8-107">Attributes</span></span>  
  
|<span data-ttu-id="5bcd8-108">특성</span><span class="sxs-lookup"><span data-stu-id="5bcd8-108">Attribute</span></span>|<span data-ttu-id="5bcd8-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="5bcd8-109">Attribute type</span></span>|<span data-ttu-id="5bcd8-110">설명</span><span class="sxs-lookup"><span data-stu-id="5bcd8-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="5bcd8-111">일반</span><span class="sxs-lookup"><span data-stu-id="5bcd8-111">General</span></span>|<span data-ttu-id="5bcd8-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-112">Required attribute.</span></span> <span data-ttu-id="5bcd8-113">제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-113">The name of the generic parameter.</span></span> <span data-ttu-id="5bcd8-114">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 런타임 정책을 대리자의 반환 값에 적용할 수 있도록 `Name` 특성의 값은 "TResult"입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="5bcd8-115">반사</span><span class="sxs-lookup"><span data-stu-id="5bcd8-115">Reflection</span></span>|<span data-ttu-id="5bcd8-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-116">Optional attribute.</span></span> <span data-ttu-id="5bcd8-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="5bcd8-118">반사</span><span class="sxs-lookup"><span data-stu-id="5bcd8-118">Reflection</span></span>|<span data-ttu-id="5bcd8-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-119">Optional attribute.</span></span> <span data-ttu-id="5bcd8-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="5bcd8-121">반사</span><span class="sxs-lookup"><span data-stu-id="5bcd8-121">Reflection</span></span>|<span data-ttu-id="5bcd8-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-122">Optional attribute.</span></span> <span data-ttu-id="5bcd8-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="5bcd8-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="5bcd8-124">Serialization</span></span>|<span data-ttu-id="5bcd8-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-125">Optional attribute.</span></span> <span data-ttu-id="5bcd8-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="5bcd8-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="5bcd8-127">Serialization</span></span>|<span data-ttu-id="5bcd8-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-128">Optional attribute.</span></span> <span data-ttu-id="5bcd8-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="5bcd8-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="5bcd8-130">Serialization</span></span>|<span data-ttu-id="5bcd8-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-131">Optional attribute.</span></span> <span data-ttu-id="5bcd8-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="5bcd8-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="5bcd8-133">Serialization</span></span>|<span data-ttu-id="5bcd8-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-134">Optional attribute.</span></span> <span data-ttu-id="5bcd8-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="5bcd8-136">Interop</span><span class="sxs-lookup"><span data-stu-id="5bcd8-136">Interop</span></span>|<span data-ttu-id="5bcd8-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-137">Optional attribute.</span></span> <span data-ttu-id="5bcd8-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="5bcd8-139">Interop</span><span class="sxs-lookup"><span data-stu-id="5bcd8-139">Interop</span></span>|<span data-ttu-id="5bcd8-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-140">Optional attribute.</span></span> <span data-ttu-id="5bcd8-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="5bcd8-142">Interop</span><span class="sxs-lookup"><span data-stu-id="5bcd8-142">Interop</span></span>|<span data-ttu-id="5bcd8-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-143">Optional attribute.</span></span> <span data-ttu-id="5bcd8-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="5bcd8-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="5bcd8-145">Name attribute</span></span>  
  
|<span data-ttu-id="5bcd8-146">값</span><span class="sxs-lookup"><span data-stu-id="5bcd8-146">Value</span></span>|<span data-ttu-id="5bcd8-147">설명</span><span class="sxs-lookup"><span data-stu-id="5bcd8-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5bcd8-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="5bcd8-148">*generic_parameter_name*</span></span>|<span data-ttu-id="5bcd8-149">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-149">Required attribute.</span></span> <span data-ttu-id="5bcd8-150">제네릭 형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-150">The name of the generic type parameter.</span></span> <span data-ttu-id="5bcd8-151">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 *generic_parameter_name*의 값이 “TResult”이면 런타임 정책이 대리자의 반환 값에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="5bcd8-152">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="5bcd8-152">All other attributes</span></span>  
  
|<span data-ttu-id="5bcd8-153">값</span><span class="sxs-lookup"><span data-stu-id="5bcd8-153">Value</span></span>|<span data-ttu-id="5bcd8-154">설명</span><span class="sxs-lookup"><span data-stu-id="5bcd8-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5bcd8-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="5bcd8-155">*policy_setting*</span></span>|<span data-ttu-id="5bcd8-156">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="5bcd8-157">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="5bcd8-158">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bcd8-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-159">Child Elements</span></span>  
 <span data-ttu-id="5bcd8-160">없음.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5bcd8-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-161">Parent Elements</span></span>  
  
|<span data-ttu-id="5bcd8-162">요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-162">Element</span></span>|<span data-ttu-id="5bcd8-163">설명</span><span class="sxs-lookup"><span data-stu-id="5bcd8-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bcd8-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="5bcd8-164">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="5bcd8-165">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="5bcd8-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="5bcd8-166">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="5bcd8-167">클래스 또는 구조체와 같은 특정 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bcd8-168">주의</span><span class="sxs-lookup"><span data-stu-id="5bcd8-168">Remarks</span></span>  
 <span data-ttu-id="5bcd8-169">`<GenericParameter>` 요소는 [\<Method>](method-element-net-native.md) 또는 [\<Type>](type-element-net-native.md) 요소의 자식이며, 제네릭 형식 또는 메서드 시그니처에서 해당 이름으로 지정되는 특정 제네릭 형식 매개 변수에 정책을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-169">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="5bcd8-170">`<GenericParameter>` 요소는 serializer와 함께 사용하면 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="5bcd8-171">다음 예제에서는 `<GenericParameter>` 요소를 사용하여 NewtonSoft JSON 직렬 변환기의 [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) 메서드 오버로드에 대한 호출에서 `T` 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bcd8-172">참조</span><span class="sxs-lookup"><span data-stu-id="5bcd8-172">See also</span></span>

- [<span data-ttu-id="5bcd8-173">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="5bcd8-174">\<형식 > 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-174">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="5bcd8-175">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="5bcd8-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="5bcd8-176">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5bcd8-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="5bcd8-177">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="5bcd8-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
