---
title: <Subtypes>요소(.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: fb854070-248b-46cf-9dab-c322e2b4d624
ms.openlocfilehash: bb719449f3769c5dbbde6d05efdb865c18bb4ab2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180929"
---
# <a name="subtypes-element-net-native"></a><span data-ttu-id="0777b-102">\<하위 유형> 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="0777b-102">\<Subtypes> Element (.NET Native)</span></span>
<span data-ttu-id="0777b-103">포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-103">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0777b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0777b-104">Syntax</span></span>  
  
```xml  
<Subtypes Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0777b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0777b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0777b-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0777b-107">특성</span><span class="sxs-lookup"><span data-stu-id="0777b-107">Attributes</span></span>  
  
|<span data-ttu-id="0777b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0777b-108">Attribute</span></span>|<span data-ttu-id="0777b-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="0777b-109">Attribute type</span></span>|<span data-ttu-id="0777b-110">Description</span><span class="sxs-lookup"><span data-stu-id="0777b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="0777b-111">반사</span><span class="sxs-lookup"><span data-stu-id="0777b-111">Reflection</span></span>|<span data-ttu-id="0777b-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-112">Optional attribute.</span></span> <span data-ttu-id="0777b-113">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0777b-114">반사</span><span class="sxs-lookup"><span data-stu-id="0777b-114">Reflection</span></span>|<span data-ttu-id="0777b-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-115">Optional attribute.</span></span> <span data-ttu-id="0777b-116">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0777b-117">반사</span><span class="sxs-lookup"><span data-stu-id="0777b-117">Reflection</span></span>|<span data-ttu-id="0777b-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-118">Optional attribute.</span></span> <span data-ttu-id="0777b-119">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0777b-120">직렬화</span><span class="sxs-lookup"><span data-stu-id="0777b-120">Serialization</span></span>|<span data-ttu-id="0777b-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-121">Optional attribute.</span></span> <span data-ttu-id="0777b-122">Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0777b-123">직렬화</span><span class="sxs-lookup"><span data-stu-id="0777b-123">Serialization</span></span>|<span data-ttu-id="0777b-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-124">Optional attribute.</span></span> <span data-ttu-id="0777b-125"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0777b-126">직렬화</span><span class="sxs-lookup"><span data-stu-id="0777b-126">Serialization</span></span>|<span data-ttu-id="0777b-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-127">Optional attribute.</span></span> <span data-ttu-id="0777b-128"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0777b-129">직렬화</span><span class="sxs-lookup"><span data-stu-id="0777b-129">Serialization</span></span>|<span data-ttu-id="0777b-130">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-130">Optional attribute.</span></span> <span data-ttu-id="0777b-131"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0777b-132">Interop</span><span class="sxs-lookup"><span data-stu-id="0777b-132">Interop</span></span>|<span data-ttu-id="0777b-133">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-133">Optional attribute.</span></span> <span data-ttu-id="0777b-134">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0777b-135">Interop</span><span class="sxs-lookup"><span data-stu-id="0777b-135">Interop</span></span>|<span data-ttu-id="0777b-136">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-136">Optional attribute.</span></span> <span data-ttu-id="0777b-137">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0777b-138">Interop</span><span class="sxs-lookup"><span data-stu-id="0777b-138">Interop</span></span>|<span data-ttu-id="0777b-139">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-139">Optional attribute.</span></span> <span data-ttu-id="0777b-140">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="0777b-141">모든 특성</span><span class="sxs-lookup"><span data-stu-id="0777b-141">All attributes</span></span>  
  
|<span data-ttu-id="0777b-142">값</span><span class="sxs-lookup"><span data-stu-id="0777b-142">Value</span></span>|<span data-ttu-id="0777b-143">Description</span><span class="sxs-lookup"><span data-stu-id="0777b-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0777b-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0777b-144">*policy_setting*</span></span>|<span data-ttu-id="0777b-145">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="0777b-146">가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0777b-147">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0777b-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0777b-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0777b-148">Child Elements</span></span>  
 <span data-ttu-id="0777b-149">없음</span><span class="sxs-lookup"><span data-stu-id="0777b-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0777b-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0777b-150">Parent Elements</span></span>  
  
|<span data-ttu-id="0777b-151">요소</span><span class="sxs-lookup"><span data-stu-id="0777b-151">Element</span></span>|<span data-ttu-id="0777b-152">Description</span><span class="sxs-lookup"><span data-stu-id="0777b-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0777b-153">\<유형></span><span class="sxs-lookup"><span data-stu-id="0777b-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="0777b-154">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0777b-155">설명</span><span class="sxs-lookup"><span data-stu-id="0777b-155">Remarks</span></span>  
 <span data-ttu-id="0777b-156">`<Subtypes>` 요소는 포함 형식의 모든 하위 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-156">The `<Subtypes>` element applies policy to all the subtypes of its containing type.</span></span> <span data-ttu-id="0777b-157">파생 형식 및 해당 기본 클래스에 각기 다른 정책을 적용하려는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-157">You use it when you want to apply different policies to derived types and their base classes.</span></span>  
  
 <span data-ttu-id="0777b-158">리플렉션, serialization 및 interop 특성은 모두 선택적 항목이지만 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0777b-159">예제</span><span class="sxs-lookup"><span data-stu-id="0777b-159">Example</span></span>  
 <span data-ttu-id="0777b-160">다음 예제에서는 `BaseClass` 클래스와 `Derived1` 하위 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-160">The following example defines a class named `BaseClass` and a subclass named `Derived1`.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#4)]  
  
 <span data-ttu-id="0777b-161">다음 코드에 나와 있는 것처럼 런타임 지시문 파일은 명시적으로 `Dynamic`에 대한 `Activate` 및 `BaseClass` 정책을 `Excluded`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-161">As shown in the following code, the runtime directives file explicitly sets the `Dynamic` and `Activate` policies for `BaseClass` to `Excluded`.</span></span> <span data-ttu-id="0777b-162">이로 인해 `BaseClass` 형식의 개체를 동적으로 또는 `BaseClass` 클래스 생성자를 호출하여 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-162">Because of this, objects of type `BaseClass` cannot be instantiated dynamically or by calls to the `BaseClass` class constructor.</span></span> <span data-ttu-id="0777b-163">그러나 `<Subtypes>` 요소는 `BaseClass`에서 파생된 클래스를 동적으로/클래스 생성자를 호출하여 인스턴스화할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-163">However, the `<Subtypes>` element allows classes derived from `BaseClass` to be instantiated dynamically and through calls to their class constructors.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
   <Assembly Name="*Application*" Dynamic="Required All" />  
     <Type Name="Examples.Libraries.BaseClass" Activate ="Excluded" Dynamic="Excluded" >  
        <Subtypes Activate="Public" Dynamic ="Public"/>  
     </Type>  
  </Application>  
</Directives>  
```  
  
 <span data-ttu-id="0777b-164">이 `<Subtypes>` 지시문으로 인해 `Derived1` 메서드를 호출하여 <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> 인스턴스를 동적으로 인스턴스화하는 다음 코드는 정상적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-164">Because of the `<Subtypes>` directive, the following code that instantiates a `Derived1` instance dynamically by calling the <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> method executes successfully.</span></span>  <span data-ttu-id="0777b-165">여기서 블록 변수는 빈 Windows 스토어 앱의 <xref:System.Windows.Controls.TextBlock> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0777b-165">The block variable here is a <xref:System.Windows.Controls.TextBlock> object in a blank Windows Store app.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="0777b-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0777b-166">See also</span></span>

- [<span data-ttu-id="0777b-167">\<> 요소 유형</span><span class="sxs-lookup"><span data-stu-id="0777b-167">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="0777b-168">Runtime Directives (rd.xml) Configuration File Reference</span><span class="sxs-lookup"><span data-stu-id="0777b-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0777b-169">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="0777b-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="0777b-170">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0777b-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
