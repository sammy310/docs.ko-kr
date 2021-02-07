---
description: '자세한 정보: 런타임 지시문 요소'
title: 런타임 지시문 요소
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: 74ff6c7d782f48106e37b99187770d8e82926be4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738431"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="8e6ce-103">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="8e6ce-103">Runtime Directive Elements</span></span>

<span data-ttu-id="8e6ce-104">런타임 지시문(rd.xml) 파일 형식은 다음 지시문 런타임 요소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-104">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="8e6ce-105">계층적 표현에 대해서는 [런타임 지시문(rd.xml) 구성 파일 참조](runtime-directives-rd-xml-configuration-file-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-105">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="8e6ce-106">앱에서 사용하는 모든 형식에 런타임 리플렉션 정책을 적용합니다. 런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="8e6ce-107">이는 요소의 자식입니다 [\<Directives>](directives-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="8e6ce-108">런타임 정책을 어셈블리의 모든 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-108">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="8e6ce-109">이는 및 요소의 자식입니다 [\<Application>](application-element-net-native.md) [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-109">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="8e6ce-110">포함 하는 [\<Type>](type-element-net-native.md) 지시문이 특성이 면 해당 특성이 적용 되는 코드 요소에 런타임 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-110">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="8e6ce-111">.NET 네이티브에 대 한 모든 런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-111">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="8e6ce-112">해당 자식 요소는 [\<Application>](application-element-net-native.md) 및 [\<Library>](library-element-net-native.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-112">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="8e6ce-113">런타임 정책을 이벤트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-113">Applies runtime policy to an event.</span></span> <span data-ttu-id="8e6ce-114">이는 및 요소의 자식입니다 [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-114">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="8e6ce-115">런타임 정책을 필드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-115">Applies runtime policy to a field.</span></span> <span data-ttu-id="8e6ce-116">이는 및 요소의 자식입니다 [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-116">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="8e6ce-117">제네릭 형식 또는 메서드의 매개 변수 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-117">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="8e6ce-118">포함 형식 또는 메서드에 런타임 정책이 적용된 경우 해당 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-118">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="8e6ce-119">런타임 정책을 어셈블리의 모든 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-119">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="8e6ce-120">이는 및 요소의 자식입니다 [\<Application>](application-element-net-native.md) [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-120">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="8e6ce-121">런타임 정책을 메서드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-121">Applies runtime policy to a method.</span></span> <span data-ttu-id="8e6ce-122">이는 및 요소의 자식입니다 [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-122">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="8e6ce-123">생성된 제네릭 메서드에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-123">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="8e6ce-124">이는 및 요소의 자식입니다 [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-124">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="8e6ce-125">네임스페이스의 모든 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-125">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="8e6ce-126">메서드에 전달된 인수의 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-126">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="8e6ce-127">런타임 정책을 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-127">Applies runtime policy to a property.</span></span> <span data-ttu-id="8e6ce-128">이는 및 요소의 자식입니다 [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8e6ce-128">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="8e6ce-129">포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-129">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="8e6ce-130">런타임 정책을 형식에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-130">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="8e6ce-131">생성된 제네릭 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-131">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="8e6ce-132">메서드로 전달된 <xref:System.Type> 인수가 나타내는 형식에 런타임 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6ce-132">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6ce-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e6ce-133">See also</span></span>

- [<span data-ttu-id="8e6ce-134">rd.xml 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="8e6ce-134">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
