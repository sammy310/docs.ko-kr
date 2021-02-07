---
description: '자세히 알아보기: <MethodInstantiation> 요소 (.NET 네이티브)'
title: <MethodInstantiation> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: 985d522a559dbbce936a2f29a9983c89ebd18a48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747493"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="904a9-103">\<MethodInstantiation> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="904a9-103">\<MethodInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="904a9-104">생성된 제네릭 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-104">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="904a9-105">구문</span><span class="sxs-lookup"><span data-stu-id="904a9-105">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="904a9-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="904a9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="904a9-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="904a9-108">특성</span><span class="sxs-lookup"><span data-stu-id="904a9-108">Attributes</span></span>  
  
|<span data-ttu-id="904a9-109">attribute</span><span class="sxs-lookup"><span data-stu-id="904a9-109">Attribute</span></span>|<span data-ttu-id="904a9-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="904a9-110">Attribute type</span></span>|<span data-ttu-id="904a9-111">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="904a9-112">일반</span><span class="sxs-lookup"><span data-stu-id="904a9-112">General</span></span>|<span data-ttu-id="904a9-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-113">Required attribute.</span></span> <span data-ttu-id="904a9-114">메서드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-114">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="904a9-115">일반</span><span class="sxs-lookup"><span data-stu-id="904a9-115">General</span></span>|<span data-ttu-id="904a9-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-116">Optional attribute.</span></span> <span data-ttu-id="904a9-117">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-117">Specifies named parameters of the method.</span></span> <span data-ttu-id="904a9-118">명명된 매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-118">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="904a9-119">`Signature` 특성은 오버로드된 메서드를 구별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-119">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="904a9-120">일반</span><span class="sxs-lookup"><span data-stu-id="904a9-120">General</span></span>|<span data-ttu-id="904a9-121">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-121">Required attribute.</span></span> <span data-ttu-id="904a9-122">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-122">Specifies the generic type arguments.</span></span> <span data-ttu-id="904a9-123">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-123">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="904a9-124">반사</span><span class="sxs-lookup"><span data-stu-id="904a9-124">Reflection</span></span>|<span data-ttu-id="904a9-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-125">Optional attribute.</span></span> <span data-ttu-id="904a9-126">메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-126">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="904a9-127">반사</span><span class="sxs-lookup"><span data-stu-id="904a9-127">Reflection</span></span>|<span data-ttu-id="904a9-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-128">Optional attribute.</span></span> <span data-ttu-id="904a9-129">동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-129">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="904a9-130">이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-130">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="904a9-131">Name 특성</span><span class="sxs-lookup"><span data-stu-id="904a9-131">Name attribute</span></span>  
  
|<span data-ttu-id="904a9-132">값</span><span class="sxs-lookup"><span data-stu-id="904a9-132">Value</span></span>|<span data-ttu-id="904a9-133">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="904a9-134">*method_name*</span><span class="sxs-lookup"><span data-stu-id="904a9-134">*method_name*</span></span>|<span data-ttu-id="904a9-135">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-135">The method name.</span></span> <span data-ttu-id="904a9-136">메서드의 형식은 부모 [\<Type>](type-element-net-native.md) 또는 요소로 정의 됩니다 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="904a9-136">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="904a9-137">시그니처 특성</span><span class="sxs-lookup"><span data-stu-id="904a9-137">Signature attribute</span></span>  
  
|<span data-ttu-id="904a9-138">값</span><span class="sxs-lookup"><span data-stu-id="904a9-138">Value</span></span>|<span data-ttu-id="904a9-139">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="904a9-140">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="904a9-140">*method_signature*</span></span>|<span data-ttu-id="904a9-141">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-141">Specifies the named parameters of the method.</span></span> <span data-ttu-id="904a9-142">매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-142">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="904a9-143">인수 특성</span><span class="sxs-lookup"><span data-stu-id="904a9-143">Arguments attribute</span></span>  
  
|<span data-ttu-id="904a9-144">값</span><span class="sxs-lookup"><span data-stu-id="904a9-144">Value</span></span>|<span data-ttu-id="904a9-145">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="904a9-146">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="904a9-146">*method_arguments*</span></span>|<span data-ttu-id="904a9-147">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-147">Specifies the generic type arguments.</span></span> <span data-ttu-id="904a9-148">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-148">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="904a9-149">각 인수는 정규화된 형식 이름으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-149">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="904a9-150">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="904a9-150">All other attributes</span></span>  
  
|<span data-ttu-id="904a9-151">값</span><span class="sxs-lookup"><span data-stu-id="904a9-151">Value</span></span>|<span data-ttu-id="904a9-152">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="904a9-153">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="904a9-153">*policy_setting*</span></span>|<span data-ttu-id="904a9-154">메서드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-154">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="904a9-155">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-155">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="904a9-156">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="904a9-156">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="904a9-157">자식 요소</span><span class="sxs-lookup"><span data-stu-id="904a9-157">Child Elements</span></span>  

 <span data-ttu-id="904a9-158">없음</span><span class="sxs-lookup"><span data-stu-id="904a9-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="904a9-159">부모 요소</span><span class="sxs-lookup"><span data-stu-id="904a9-159">Parent Elements</span></span>  
  
|<span data-ttu-id="904a9-160">요소</span><span class="sxs-lookup"><span data-stu-id="904a9-160">Element</span></span>|<span data-ttu-id="904a9-161">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-161">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="904a9-162">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-162">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="904a9-163">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-163">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="904a9-164">설명</span><span class="sxs-lookup"><span data-stu-id="904a9-164">Remarks</span></span>  

 <span data-ttu-id="904a9-165">`<MethodInstantiation>` 요소는 해당 개방형 제네릭 메서드의 런타임 리플렉션 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="904a9-165">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904a9-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="904a9-166">See also</span></span>

- [<span data-ttu-id="904a9-167">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="904a9-167">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="904a9-168">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="904a9-168">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="904a9-169">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="904a9-169">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="904a9-170">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="904a9-170">\<Method> Element</span></span>](method-element-net-native.md)
