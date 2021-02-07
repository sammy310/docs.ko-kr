---
description: '자세히 알아보기: <Field> 요소 (.NET 네이티브)'
title: <Field> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 1f8c8b6720fb90bdc5855da7b17694253bbb7629
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747844"
---
# <a name="field-element-net-native"></a><span data-ttu-id="3ba48-103">\<Field> 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="3ba48-103">\<Field> Element (.NET Native)</span></span>

<span data-ttu-id="3ba48-104">런타임 리플렉션 정책을 필드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-104">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba48-105">구문</span><span class="sxs-lookup"><span data-stu-id="3ba48-105">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ba48-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3ba48-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3ba48-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ba48-108">특성</span><span class="sxs-lookup"><span data-stu-id="3ba48-108">Attributes</span></span>  
  
|<span data-ttu-id="3ba48-109">attribute</span><span class="sxs-lookup"><span data-stu-id="3ba48-109">Attribute</span></span>|<span data-ttu-id="3ba48-110">특성 유형</span><span class="sxs-lookup"><span data-stu-id="3ba48-110">Attribute type</span></span>|<span data-ttu-id="3ba48-111">설명</span><span class="sxs-lookup"><span data-stu-id="3ba48-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="3ba48-112">일반</span><span class="sxs-lookup"><span data-stu-id="3ba48-112">General</span></span>|<span data-ttu-id="3ba48-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-113">Required attribute.</span></span> <span data-ttu-id="3ba48-114">필드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-114">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="3ba48-115">반사</span><span class="sxs-lookup"><span data-stu-id="3ba48-115">Reflection</span></span>|<span data-ttu-id="3ba48-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-116">Optional attribute.</span></span> <span data-ttu-id="3ba48-117">필드에 대한 정보 쿼리 또는 필드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-117">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="3ba48-118">반사</span><span class="sxs-lookup"><span data-stu-id="3ba48-118">Reflection</span></span>|<span data-ttu-id="3ba48-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-119">Optional attribute.</span></span> <span data-ttu-id="3ba48-120">동적 프로그래밍을 수행할 수 있도록 필드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-120">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="3ba48-121">이 정책을 통해 런타임에 필드를 동적으로 설정하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-121">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="3ba48-122">Serialization</span><span class="sxs-lookup"><span data-stu-id="3ba48-122">Serialization</span></span>|<span data-ttu-id="3ba48-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-123">Optional attribute.</span></span> <span data-ttu-id="3ba48-124">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize하거나 데이터 바인딩에 사용할 수 있도록 필드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-124">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="3ba48-125">Name 특성</span><span class="sxs-lookup"><span data-stu-id="3ba48-125">Name attribute</span></span>  
  
|<span data-ttu-id="3ba48-126">값</span><span class="sxs-lookup"><span data-stu-id="3ba48-126">Value</span></span>|<span data-ttu-id="3ba48-127">설명</span><span class="sxs-lookup"><span data-stu-id="3ba48-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ba48-128">*method_name*</span><span class="sxs-lookup"><span data-stu-id="3ba48-128">*method_name*</span></span>|<span data-ttu-id="3ba48-129">필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-129">The field name.</span></span> <span data-ttu-id="3ba48-130">필드의 형식은 부모 [\<Type>](type-element-net-native.md) 또는 요소로 정의 됩니다 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="3ba48-130">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="3ba48-131">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="3ba48-131">All other attributes</span></span>  
  
|<span data-ttu-id="3ba48-132">값</span><span class="sxs-lookup"><span data-stu-id="3ba48-132">Value</span></span>|<span data-ttu-id="3ba48-133">설명</span><span class="sxs-lookup"><span data-stu-id="3ba48-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ba48-134">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="3ba48-134">*policy_setting*</span></span>|<span data-ttu-id="3ba48-135">필드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-135">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="3ba48-136">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-136">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="3ba48-137">자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ba48-137">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ba48-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3ba48-138">Child Elements</span></span>  

 <span data-ttu-id="3ba48-139">없음</span><span class="sxs-lookup"><span data-stu-id="3ba48-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ba48-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3ba48-140">Parent Elements</span></span>  
  
|<span data-ttu-id="3ba48-141">요소</span><span class="sxs-lookup"><span data-stu-id="3ba48-141">Element</span></span>|<span data-ttu-id="3ba48-142">설명</span><span class="sxs-lookup"><span data-stu-id="3ba48-142">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="3ba48-143">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-143">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="3ba48-144">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-144">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ba48-145">설명</span><span class="sxs-lookup"><span data-stu-id="3ba48-145">Remarks</span></span>  

 <span data-ttu-id="3ba48-146">필드의 정책이 명시적으로 정의되어 있지 않으면 부모 요소의 런타임 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="3ba48-146">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba48-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ba48-147">See also</span></span>

- [<span data-ttu-id="3ba48-148">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="3ba48-148">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="3ba48-149">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="3ba48-149">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="3ba48-150">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3ba48-150">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
