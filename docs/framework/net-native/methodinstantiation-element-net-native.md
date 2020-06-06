---
title: <MethodInstantiation>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: f19bd3c20088431bcbbafac298398b82a664bee9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128323"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="52003-102">\<MethodInstantiation>요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="52003-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="52003-103">생성된 제네릭 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52003-104">구문</span><span class="sxs-lookup"><span data-stu-id="52003-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52003-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52003-105">Attributes and Elements</span></span>  
 <span data-ttu-id="52003-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52003-107">특성</span><span class="sxs-lookup"><span data-stu-id="52003-107">Attributes</span></span>  
  
|<span data-ttu-id="52003-108">attribute</span><span class="sxs-lookup"><span data-stu-id="52003-108">Attribute</span></span>|<span data-ttu-id="52003-109">특성 유형</span><span class="sxs-lookup"><span data-stu-id="52003-109">Attribute type</span></span>|<span data-ttu-id="52003-110">Description</span><span class="sxs-lookup"><span data-stu-id="52003-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="52003-111">일반</span><span class="sxs-lookup"><span data-stu-id="52003-111">General</span></span>|<span data-ttu-id="52003-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-112">Required attribute.</span></span> <span data-ttu-id="52003-113">메서드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="52003-114">일반</span><span class="sxs-lookup"><span data-stu-id="52003-114">General</span></span>|<span data-ttu-id="52003-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-115">Optional attribute.</span></span> <span data-ttu-id="52003-116">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="52003-117">명명된 매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="52003-118">`Signature` 특성은 오버로드된 메서드를 구별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52003-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="52003-119">일반</span><span class="sxs-lookup"><span data-stu-id="52003-119">General</span></span>|<span data-ttu-id="52003-120">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-120">Required attribute.</span></span> <span data-ttu-id="52003-121">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="52003-122">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="52003-123">반사</span><span class="sxs-lookup"><span data-stu-id="52003-123">Reflection</span></span>|<span data-ttu-id="52003-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-124">Optional attribute.</span></span> <span data-ttu-id="52003-125">메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52003-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="52003-126">반사</span><span class="sxs-lookup"><span data-stu-id="52003-126">Reflection</span></span>|<span data-ttu-id="52003-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-127">Optional attribute.</span></span> <span data-ttu-id="52003-128">동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="52003-129">이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52003-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="52003-130">Name 특성</span><span class="sxs-lookup"><span data-stu-id="52003-130">Name attribute</span></span>  
  
|<span data-ttu-id="52003-131">값</span><span class="sxs-lookup"><span data-stu-id="52003-131">Value</span></span>|<span data-ttu-id="52003-132">Description</span><span class="sxs-lookup"><span data-stu-id="52003-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52003-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="52003-133">*method_name*</span></span>|<span data-ttu-id="52003-134">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-134">The method name.</span></span> <span data-ttu-id="52003-135">메서드의 형식은 부모 [\<Type>](type-element-net-native.md) 또는 요소로 정의 됩니다 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="52003-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="52003-136">시그니처 특성</span><span class="sxs-lookup"><span data-stu-id="52003-136">Signature attribute</span></span>  
  
|<span data-ttu-id="52003-137">값</span><span class="sxs-lookup"><span data-stu-id="52003-137">Value</span></span>|<span data-ttu-id="52003-138">Description</span><span class="sxs-lookup"><span data-stu-id="52003-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52003-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="52003-139">*method_signature*</span></span>|<span data-ttu-id="52003-140">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="52003-141">매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="52003-142">인수 특성</span><span class="sxs-lookup"><span data-stu-id="52003-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="52003-143">값</span><span class="sxs-lookup"><span data-stu-id="52003-143">Value</span></span>|<span data-ttu-id="52003-144">Description</span><span class="sxs-lookup"><span data-stu-id="52003-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52003-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="52003-145">*method_arguments*</span></span>|<span data-ttu-id="52003-146">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="52003-147">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="52003-148">각 인수는 정규화된 형식 이름으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="52003-149">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="52003-149">All other attributes</span></span>  
  
|<span data-ttu-id="52003-150">값</span><span class="sxs-lookup"><span data-stu-id="52003-150">Value</span></span>|<span data-ttu-id="52003-151">Description</span><span class="sxs-lookup"><span data-stu-id="52003-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52003-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="52003-152">*policy_setting*</span></span>|<span data-ttu-id="52003-153">메서드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="52003-154">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="52003-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="52003-155">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52003-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52003-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52003-156">Child Elements</span></span>  
 <span data-ttu-id="52003-157">없음</span><span class="sxs-lookup"><span data-stu-id="52003-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52003-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52003-158">Parent Elements</span></span>  
  
|<span data-ttu-id="52003-159">요소</span><span class="sxs-lookup"><span data-stu-id="52003-159">Element</span></span>|<span data-ttu-id="52003-160">Description</span><span class="sxs-lookup"><span data-stu-id="52003-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="52003-161">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="52003-162">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52003-163">설명</span><span class="sxs-lookup"><span data-stu-id="52003-163">Remarks</span></span>  
 <span data-ttu-id="52003-164">`<MethodInstantiation>` 요소는 해당 개방형 제네릭 메서드의 런타임 리플렉션 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52003-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52003-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52003-165">See also</span></span>

- [<span data-ttu-id="52003-166">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="52003-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="52003-167">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="52003-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="52003-168">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="52003-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="52003-169">\<Method>요소인</span><span class="sxs-lookup"><span data-stu-id="52003-169">\<Method> Element</span></span>](method-element-net-native.md)
