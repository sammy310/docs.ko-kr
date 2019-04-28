---
title: 런타임 지시문 요소
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf692ff93a575858d1d1a89346611cb9c5957b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61867045"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="0633d-102">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="0633d-102">Runtime Directive Elements</span></span>
<span data-ttu-id="0633d-103">런타임 지시문(rd.xml) 파일 형식은 다음 지시문 런타임 요소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="0633d-104">계층적 표현에 대해서는 [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0633d-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="0633d-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="0633d-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="0633d-106">앱에서 사용하는 모든 형식에 런타임 리플렉션 정책을 적용합니다. 런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="0633d-107">이 요소는 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="0633d-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="0633d-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="0633d-109">런타임 정책을 어셈블리의 모든 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="0633d-110">이 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="0633d-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="0633d-112">포함 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 지시문이 특성이면 해당 특성이 적용되는 코드 요소에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="0633d-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="0633d-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="0633d-114">[!INCLUDE[net_native](../../../includes/net-native-md.md)]용 모든 런타임 지시문의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="0633d-115">해당 자식 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="0633d-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="0633d-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="0633d-117">런타임 정책을 이벤트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="0633d-118">이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="0633d-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="0633d-120">런타임 정책을 필드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="0633d-121">이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="0633d-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="0633d-123">제네릭 형식 또는 메서드의 매개 변수 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="0633d-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="0633d-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="0633d-125">포함 형식 또는 메서드에 런타임 정책이 적용된 경우 해당 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="0633d-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="0633d-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="0633d-127">런타임 정책을 어셈블리의 모든 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="0633d-128">이 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="0633d-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="0633d-130">런타임 정책을 메서드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="0633d-131">이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="0633d-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="0633d-133">생성된 제네릭 메서드에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="0633d-134">이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="0633d-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="0633d-136">네임스페이스의 모든 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="0633d-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="0633d-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="0633d-138">메서드에 전달된 인수의 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="0633d-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="0633d-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="0633d-140">런타임 정책을 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="0633d-141">이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="0633d-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="0633d-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="0633d-143">포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="0633d-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="0633d-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="0633d-145">런타임 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="0633d-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="0633d-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="0633d-147">생성된 제네릭 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="0633d-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="0633d-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="0633d-149">메서드로 전달된 <xref:System.Type> 인수가 나타내는 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0633d-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0633d-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="0633d-150">See also</span></span>

- [<span data-ttu-id="0633d-151">rd.xml 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="0633d-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
