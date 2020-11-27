---
title: <GenericParameter> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: 1400fb7029df533d54e87a1c534f4ac3b0a5fc68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288023"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="f7fae-102">\<GenericParameter> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="f7fae-102">\<GenericParameter> Element (.NET Native)</span></span>

<span data-ttu-id="f7fae-103">제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fae-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7fae-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7fae-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f7fae-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7fae-107">특성</span><span class="sxs-lookup"><span data-stu-id="f7fae-107">Attributes</span></span>  
  
|<span data-ttu-id="f7fae-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f7fae-108">Attribute</span></span>|<span data-ttu-id="f7fae-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="f7fae-109">Attribute type</span></span>|<span data-ttu-id="f7fae-110">Description</span><span class="sxs-lookup"><span data-stu-id="f7fae-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="f7fae-111">일반</span><span class="sxs-lookup"><span data-stu-id="f7fae-111">General</span></span>|<span data-ttu-id="f7fae-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-112">Required attribute.</span></span> <span data-ttu-id="f7fae-113">제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-113">The name of the generic parameter.</span></span> <span data-ttu-id="f7fae-114">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 런타임 정책을 대리자의 반환 값에 적용할 수 있도록 `Name` 특성의 값은 "TResult"입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="f7fae-115">반사</span><span class="sxs-lookup"><span data-stu-id="f7fae-115">Reflection</span></span>|<span data-ttu-id="f7fae-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-116">Optional attribute.</span></span> <span data-ttu-id="f7fae-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="f7fae-118">반사</span><span class="sxs-lookup"><span data-stu-id="f7fae-118">Reflection</span></span>|<span data-ttu-id="f7fae-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-119">Optional attribute.</span></span> <span data-ttu-id="f7fae-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="f7fae-121">반사</span><span class="sxs-lookup"><span data-stu-id="f7fae-121">Reflection</span></span>|<span data-ttu-id="f7fae-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-122">Optional attribute.</span></span> <span data-ttu-id="f7fae-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="f7fae-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="f7fae-124">Serialization</span></span>|<span data-ttu-id="f7fae-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-125">Optional attribute.</span></span> <span data-ttu-id="f7fae-126">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="f7fae-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="f7fae-127">Serialization</span></span>|<span data-ttu-id="f7fae-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-128">Optional attribute.</span></span> <span data-ttu-id="f7fae-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="f7fae-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="f7fae-130">Serialization</span></span>|<span data-ttu-id="f7fae-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-131">Optional attribute.</span></span> <span data-ttu-id="f7fae-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="f7fae-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="f7fae-133">Serialization</span></span>|<span data-ttu-id="f7fae-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-134">Optional attribute.</span></span> <span data-ttu-id="f7fae-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="f7fae-136">Interop</span><span class="sxs-lookup"><span data-stu-id="f7fae-136">Interop</span></span>|<span data-ttu-id="f7fae-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-137">Optional attribute.</span></span> <span data-ttu-id="f7fae-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="f7fae-139">Interop</span><span class="sxs-lookup"><span data-stu-id="f7fae-139">Interop</span></span>|<span data-ttu-id="f7fae-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-140">Optional attribute.</span></span> <span data-ttu-id="f7fae-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="f7fae-142">Interop</span><span class="sxs-lookup"><span data-stu-id="f7fae-142">Interop</span></span>|<span data-ttu-id="f7fae-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-143">Optional attribute.</span></span> <span data-ttu-id="f7fae-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="f7fae-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="f7fae-145">Name attribute</span></span>  
  
|<span data-ttu-id="f7fae-146">값</span><span class="sxs-lookup"><span data-stu-id="f7fae-146">Value</span></span>|<span data-ttu-id="f7fae-147">Description</span><span class="sxs-lookup"><span data-stu-id="f7fae-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7fae-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="f7fae-148">*generic_parameter_name*</span></span>|<span data-ttu-id="f7fae-149">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-149">Required attribute.</span></span> <span data-ttu-id="f7fae-150">제네릭 형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-150">The name of the generic type parameter.</span></span> <span data-ttu-id="f7fae-151">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 *generic_parameter_name* 의 값이 “TResult”이면 런타임 정책이 대리자의 반환 값에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="f7fae-152">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="f7fae-152">All other attributes</span></span>  
  
|<span data-ttu-id="f7fae-153">값</span><span class="sxs-lookup"><span data-stu-id="f7fae-153">Value</span></span>|<span data-ttu-id="f7fae-154">Description</span><span class="sxs-lookup"><span data-stu-id="f7fae-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7fae-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="f7fae-155">*policy_setting*</span></span>|<span data-ttu-id="f7fae-156">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="f7fae-157">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="f7fae-158">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7fae-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7fae-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-159">Child Elements</span></span>  

 <span data-ttu-id="f7fae-160">없음</span><span class="sxs-lookup"><span data-stu-id="f7fae-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7fae-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-161">Parent Elements</span></span>  
  
|<span data-ttu-id="f7fae-162">요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-162">Element</span></span>|<span data-ttu-id="f7fae-163">Description</span><span class="sxs-lookup"><span data-stu-id="f7fae-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="f7fae-164">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="f7fae-165">클래스 또는 구조체와 같은 특정 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-165">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7fae-166">설명</span><span class="sxs-lookup"><span data-stu-id="f7fae-166">Remarks</span></span>  

 <span data-ttu-id="f7fae-167">`<GenericParameter>`요소는 [\<Method>](method-element-net-native.md) 또는 요소의 자식 [\<Type>](type-element-net-native.md) 이며, 제네릭 형식 또는 메서드 시그니처에서 해당 이름으로 지정 되는 특정 제네릭 형식 매개 변수에 정책을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-167">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="f7fae-168">`<GenericParameter>` 요소는 serializer와 함께 사용하면 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-168">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="f7fae-169">다음 예제에서는 요소를 사용 하 여 `<GenericParameter>` `T` newtonsoft.json JSON Serializer의 [JsonConvert .는 deserializeobject \<T> (String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) 메서드 오버 로드에 대 한 호출에서 형식에 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fae-169">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7fae-170">참조</span><span class="sxs-lookup"><span data-stu-id="f7fae-170">See also</span></span>

- [<span data-ttu-id="f7fae-171">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-171">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="f7fae-172">\<Type> 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-172">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="f7fae-173">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="f7fae-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="f7fae-174">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="f7fae-174">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="f7fae-175">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="f7fae-175">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
