---
title: 사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432985"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a><span data-ttu-id="0887f-102">사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="0887f-102">XAML-related CLR attributes for custom types and libraries</span></span>

<span data-ttu-id="0887f-103">이 항목에서는 .NET XAML 서비스에서 정의하는 CLR(공통 언어 런타임) 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-103">This topic describes the common language runtime (CLR) attributes that are defined by .NET XAML Services.</span></span> <span data-ttu-id="0887f-104">또한 어셈블리 또는 형식에 대한 응용 프로그램에 대한 XAML 관련 시나리오가 있는 .NET에 정의된 다른 CLR 특성에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-104">It also describes other CLR attributes that are defined in .NET that have a XAML-related scenario for application to assemblies or types.</span></span> <span data-ttu-id="0887f-105">이러한 CLR 특성을 사용하여 어셈블리, 형식 또는 멤버를 어트리뷰션하면 형식과 관련된 XAML 형식 시스템 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-105">Attributing assemblies, types, or members with these CLR attributes provides XAML type system information related to your types.</span></span> <span data-ttu-id="0887f-106">정보는 직접 또는 전용 XAML 판독기 및 XAML 기록기를 통해 XAML 노드 스트림을 처리하기 위해 .NET XAML 서비스를 사용하는 모든 XAML 소비자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-106">Information is provided to any XAML consumer that uses .NET XAML Services for processing the XAML node stream directly or through the dedicated XAML readers and XAML writers.</span></span>

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a><span data-ttu-id="0887f-107">사용자 지정 형식 및 사용자 지정 멤버에 대한 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="0887f-107">XAML-Related CLR Attributes for Custom Types and Custom Members</span></span>

<span data-ttu-id="0887f-108">CLR 특성을 사용하면 전체 CLR을 사용하여 형식을 정의하는 것이 수반되며 그렇지 않으면 이러한 특성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-108">Using CLR attributes entails that you are using the overall CLR to define your types, otherwise such attributes are not available.</span></span> <span data-ttu-id="0887f-109">CLR을 사용하여 형식 백업을 정의하는 경우 .NET XAML 서비스 XAML 작성자가 사용하는 기본 XAML 스키마 컨텍스트는 백업 어셈블리에 대한 리플렉션을 통해 CLR 기여도를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-109">If you use the CLR to define type backing, then the default XAML schema context used by .NET XAML Services XAML writers can read CLR attribution through reflection against backing assemblies.</span></span>

<span data-ttu-id="0887f-110">다음 섹션에서는 사용자 지정 형식 또는 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-110">The following sections describe the XAML-related attributes that you can apply to custom types or custom members.</span></span> <span data-ttu-id="0887f-111">각 CLR 특성은 XAML 형식 시스템과 관련된 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-111">Each CLR attribute communicates information that is relevant to a XAML type system.</span></span> <span data-ttu-id="0887f-112">로드 경로에서 특성정보는 XAML 판독기가 유효한 XAML 노드 스트림을 형성하는 데 도움이 되거나 XAML 작성기가 유효한 개체 그래프를 생성하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-112">In the load path, the attributed information either helps the XAML reader form a valid XAML node stream, or it helps the XAML writer produce a valid object graph.</span></span> <span data-ttu-id="0887f-113">저장 경로에서 특성 정보는 XAML 판독기가 XAML 형식 시스템 정보를 재구성하는 유효한 XAML 노드 스트림을 형성하는 데 도움이 됩니다. 또는 XAML 기록기 또는 기타 XAML 소비자에 대한 직렬화 힌트 또는 요구 사항을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-113">In the save path, the attributed information either helps the XAML reader form a valid XAML node stream that reconstitutes XAML type system information; or it declares serialization hints or requirements for the XAML writer or other XAML consumers.</span></span>

### <a name="ambientattribute"></a><span data-ttu-id="0887f-114">앰비언트 특성</span><span class="sxs-lookup"><span data-stu-id="0887f-114">AmbientAttribute</span></span>

<span data-ttu-id="0887f-115">**참조 문서:**<xref:System.Windows.Markup.AmbientAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-115">**Reference Documentation:** <xref:System.Windows.Markup.AmbientAttribute></span></span>

<span data-ttu-id="0887f-116">**다음에 적용됩니다.** 첨부 가능한 속성을 `get` 지원하는 클래스, 속성 또는 접근자 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-116">**Applies to:** Class, property, or `get` accessor members that support attachable properties.</span></span>

<span data-ttu-id="0887f-117">**인수:** 없음</span><span class="sxs-lookup"><span data-stu-id="0887f-117">**Arguments:** None</span></span>

<span data-ttu-id="0887f-118"><xref:System.Windows.Markup.AmbientAttribute>는 속성 또는 특성 형식을 취하는 모든 속성이 XAML의 주변 속성 개념에 따라 해석되어야 음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-118"><xref:System.Windows.Markup.AmbientAttribute> indicates that the property, or all properties that take the attributed type, should be interpreted under the ambient property concept in XAML.</span></span> <span data-ttu-id="0887f-119">앰비언트 개념은 XAML 프로세서가 멤버의 형식 소유자를 결정하는 방법과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-119">The ambient concept relates to how XAML processors determine type owners of members.</span></span> <span data-ttu-id="0887f-120">앰비언트 속성은 개체 그래프를 만들 때 파서 컨텍스트에서 값을 사용할 수 있어야 하지만 생성되는 즉시 XAML 노드 집합에 대해 일반적인 형식 멤버 조회가 일시 중단되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-120">An ambient property is a property where the value is expected to be available in the parser context when creating an object graph, but where typical type-member lookup is suspended for the immediate XAML node set being created.</span></span>

<span data-ttu-id="0887f-121">주변 개념은 CLR 기여가 정의하는 방식에서 속성으로 표현되지 않는 연결 가능한 멤버에 적용할 <xref:System.AttributeTargets>수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-121">The ambient concept can be applied to attachable members, which are not represented as properties in terms of how CLR attribution defines <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="0887f-122">메서드 기여 사용은 XAML에 대한 첨부 `get` 가능한 사용을 지원하는 접근자에 대해서만 적용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-122">The method attribution usage should be applied only for a `get` accessor that supports attachable usage for XAML.</span></span>

### <a name="constructorargumentattribute"></a><span data-ttu-id="0887f-123">생성자 인수 특성</span><span class="sxs-lookup"><span data-stu-id="0887f-123">ConstructorArgumentAttribute</span></span>

<span data-ttu-id="0887f-124">**참조 문서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-124">**Reference Documentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span></span>

<span data-ttu-id="0887f-125">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-125">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-126">**인수:** 단일 생성자 인수와 일치하는 속성의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-126">**Arguments:** A string that specifies the name of the property that matches a single constructor argument.</span></span>

<span data-ttu-id="0887f-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute>매개 변수가 없는 생성자 구문을 사용하여 개체를 초기화할 수 있고 지정된 이름의 속성이 구성 정보를 제공한다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> specifies that an object can be initialized by using a non-parameterless constructor syntax, and that a property of the specified name supplies construction information.</span></span> <span data-ttu-id="0887f-128">이 정보는 주로 XAML serialization용입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-128">This information is primarily for XAML serialization.</span></span> <span data-ttu-id="0887f-129">자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0887f-129">For more information, see <xref:System.Windows.Markup.ConstructorArgumentAttribute>.</span></span>

### <a name="contentpropertyattribute"></a><span data-ttu-id="0887f-130">콘텐츠속성 속성</span><span class="sxs-lookup"><span data-stu-id="0887f-130">ContentPropertyAttribute</span></span>

<span data-ttu-id="0887f-131">**참조 문서:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-131">**Reference Documentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span></span>

<span data-ttu-id="0887f-132">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-132">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-133">**인수:** 특성이 있는 형식의 멤버 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-133">**Arguments:** A string that specifies the name of a member of the attributed type.</span></span>

<span data-ttu-id="0887f-134"><xref:System.Windows.Markup.ContentPropertyAttribute>는 인수에 의해 명명 된 속성이 해당 형식에 대한 XAML 콘텐츠 속성으로 제공되어야 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-134"><xref:System.Windows.Markup.ContentPropertyAttribute> indicates that the property as named by the argument should serve as the XAML content property for that type.</span></span> <span data-ttu-id="0887f-135">XAML 콘텐츠 속성 정의 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-135">The XAML content property definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="0887f-136">특정 파생 형식에 적용하여 <xref:System.Windows.Markup.ContentPropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-136">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.ContentPropertyAttribute> on the specific derived type.</span></span>

<span data-ttu-id="0887f-137">XAML 콘텐츠 속성 역할을 하는 속성의 경우 속성에 대한 속성 요소 태그 지정은 XAML 사용에서 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-137">For the property that serves as the XAML content property, property element tagging for the property can be omitted in the XAML usage.</span></span> <span data-ttu-id="0887f-138">일반적으로 콘텐츠 및 제약 모델에 대해 간소화된 XAML 태그를 승격하는 XAML 콘텐츠 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-138">Typically, you designate XAML content properties that promote a streamlined XAML markup for your content and containment models.</span></span> <span data-ttu-id="0887f-139">한 멤버만 XAML 콘텐츠 속성으로 지정할 수 있으므로 형식의 여러 컨테이너 속성 중 어떤 것을 XAML 콘텐츠 속성으로 지정해야 하는지 에 대해 선택할 수 있는 디자인이 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-139">Because only one member can be designated as the XAML content property, you sometimes have design choices to make regarding which of several container properties of a type should be designated as the XAML content property.</span></span> <span data-ttu-id="0887f-140">다른 컨테이너 속성은 명시적 속성 요소와 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-140">The other container properties must be used with explicit property elements.</span></span>

<span data-ttu-id="0887f-141">XAML 노드 스트림에서 XAML 콘텐츠 `StartMember` 속성은 여전히 에 대한 속성 의 이름을 사용하여 생성 및 `EndMember` 노드를 <xref:System.Xaml.XamlMember>생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-141">In the XAML node stream, XAML content properties still produce `StartMember` and `EndMember` nodes, using the name of the property for the <xref:System.Xaml.XamlMember>.</span></span> <span data-ttu-id="0887f-142">멤버가 XAML 콘텐츠 속성인지 여부를 확인하려면 <xref:System.Xaml.XamlType> `StartObject` 위치에서 값을 검사하고 <xref:System.Xaml.XamlType.ContentProperty%2A>의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-142">To determine whether a member is the XAML content property, examine the <xref:System.Xaml.XamlType> value from the `StartObject` position and obtain the value of <xref:System.Xaml.XamlType.ContentProperty%2A>.</span></span>

### <a name="contentwrapperattribute"></a><span data-ttu-id="0887f-143">콘텐츠래퍼속성</span><span class="sxs-lookup"><span data-stu-id="0887f-143">ContentWrapperAttribute</span></span>

<span data-ttu-id="0887f-144">**참조 문서:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-144">**Reference Documentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span></span>

<span data-ttu-id="0887f-145">**다음에 적용됩니다.** 클래스, 특히 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-145">**Applies to:** Class, specifically collection types.</span></span>

<span data-ttu-id="0887f-146">**인수:** 외부 <xref:System.Type> 콘텐츠의 콘텐츠 래퍼 유형으로 사용할 형식을 지정하는 A입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-146">**Arguments:** A <xref:System.Type> that specifies the type to use as the content wrapper type for foreign content.</span></span>

<span data-ttu-id="0887f-147"><xref:System.Windows.Markup.ContentWrapperAttribute>외부 콘텐츠를 래핑하는 데 사용할 관련 컬렉션 형식에 하나 이상의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-147"><xref:System.Windows.Markup.ContentWrapperAttribute> specifies one or more types on the associated collection type that will be used to wrap foreign content.</span></span> <span data-ttu-id="0887f-148">외부 콘텐츠는 콘텐츠 속성형식에 대한 형식 시스템 제약 조건이 소유 형식에 대한 XAML 사용이 지원하는 가능한 모든 콘텐츠 사례를 캡처하지 않는 경우를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-148">Foreign content refers to cases where the type system constraints on the type of the content property do not capture all of the possible content cases that XAML usage for the owning type would support.</span></span> <span data-ttu-id="0887f-149">예를 들어 특정 형식의 콘텐츠에 대한 XAML 지원은 강력하게 <xref:System.Collections.ObjectModel.Collection%601>형식이 있는 제네릭의 문자열을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-149">For example, XAML support for content of a particular type might support strings in a strongly typed generic <xref:System.Collections.ObjectModel.Collection%601>.</span></span> <span data-ttu-id="0887f-150">콘텐츠 래퍼는 텍스트 관련 콘텐츠 모델 마이그레이션과 같은 컬렉션에 할당 가능한 값의 XAML 개념으로 기존 태그 규칙을 마이그레이션하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-150">Content wrappers are useful for migrating pre-existing markup conventions into XAML's conception of assignable values for collections, such as migrating text-related content models.</span></span>

<span data-ttu-id="0887f-151">두 개 이상의 콘텐츠 래퍼 유형을 지정하려면 특성을 여러 번 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-151">To specify more than one content wrapper type, apply the attribute multiple times.</span></span>

### <a name="dependsonattribute"></a><span data-ttu-id="0887f-152">종속 속성</span><span class="sxs-lookup"><span data-stu-id="0887f-152">DependsOnAttribute</span></span>

<span data-ttu-id="0887f-153">**참조 문서:**  <xref:System.Windows.Markup.DependsOnAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-153">**Reference Documentation:**  <xref:System.Windows.Markup.DependsOnAttribute></span></span>

<span data-ttu-id="0887f-154">**다음에 적용됩니다.** 속성</span><span class="sxs-lookup"><span data-stu-id="0887f-154">**Applies to:** Property</span></span>

<span data-ttu-id="0887f-155">**인수:** 특성이 있는 형식의 다른 멤버의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-155">**Arguments:** A string that specifies the name of another member of the attributed type.</span></span>

<span data-ttu-id="0887f-156"><xref:System.Windows.Markup.DependsOnAttribute>는 특성 속성이 다른 속성의 값에 종속되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-156"><xref:System.Windows.Markup.DependsOnAttribute> indicates that the attributed property depends on the value of another property.</span></span> <span data-ttu-id="0887f-157">속성 정의에 이 특성을 적용하면 종속 속성이 XAML 개체 쓰기에서 먼저 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-157">Applying this attribute to a property definition ensures that the dependent properties are processed first in XAML object writing.</span></span> <span data-ttu-id="0887f-158">유효한 개체 <xref:System.Windows.Markup.DependsOnAttribute> 를 만들기 위해 특정 구문 분석 순서를 따라야 하는 형식에 속성의 예외적인 경우를 지정 하는 사용 법입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-158">Usages of <xref:System.Windows.Markup.DependsOnAttribute> specify the exceptional cases of properties on types where a specific order of parsing must be followed for valid object creation.</span></span>

<span data-ttu-id="0887f-159">속성 정의에 <xref:System.Windows.Markup.DependsOnAttribute> 여러 사례를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-159">You can apply multiple <xref:System.Windows.Markup.DependsOnAttribute> cases to a property definition.</span></span>

### <a name="markupextensionreturntypeattribute"></a><span data-ttu-id="0887f-160">마크업익스텐션리턴트특성</span><span class="sxs-lookup"><span data-stu-id="0887f-160">MarkupExtensionReturnTypeAttribute</span></span>

<span data-ttu-id="0887f-161">**참조 문서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-161">**Reference Documentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span></span>

<span data-ttu-id="0887f-162">**다음에 적용됩니다.** <xref:System.Windows.Markup.MarkupExtension> 파생 된 형식이 될 것으로 예상 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-162">**Applies to:** Class, which is expected to be a <xref:System.Windows.Markup.MarkupExtension> derived type.</span></span>

<span data-ttu-id="0887f-163">**인수:** 특성의 <xref:System.Type> `ProvideValue` 결과로 기대할 수 있는 가장 정확한 형식을 지정하는 <xref:System.Windows.Markup.MarkupExtension>A.</span><span class="sxs-lookup"><span data-stu-id="0887f-163">**Arguments:** A <xref:System.Type> that specifies the most precise type to expect as the `ProvideValue` result of the attributed <xref:System.Windows.Markup.MarkupExtension>.</span></span>

<span data-ttu-id="0887f-164">자세한 내용은 [XAML 개요에 대한 마크업 확장을](markup-extensions-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0887f-164">For more information, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

### <a name="namescopepropertyattribute"></a><span data-ttu-id="0887f-165">네임스코프속성속성</span><span class="sxs-lookup"><span data-stu-id="0887f-165">NameScopePropertyAttribute</span></span>

<span data-ttu-id="0887f-166">**참조 문서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-166">**Reference Documentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span></span>

<span data-ttu-id="0887f-167">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-167">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-168">**인수:** 두 가지 형태의 기여를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-168">**Arguments:** Supports two forms of attribution:</span></span>

- <span data-ttu-id="0887f-169">특성형식의 속성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-169">A string that specifies the name of a property on the attributed type.</span></span>

- <span data-ttu-id="0887f-170">속성의 이름을 지정하는 문자열과 명명된 <xref:System.Type> 속성을 정의하는 형식에 대한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-170">A string that specifies the name of a property, and a <xref:System.Type> for the type that defines the named property.</span></span> <span data-ttu-id="0887f-171">이 양식은 연결할 수 있는 멤버를 XAML 네임스코프 속성으로 지정하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-171">This form is for specifying an attachable member as the XAML namescope property.</span></span>

<span data-ttu-id="0887f-172"><xref:System.Windows.Markup.NameScopePropertyAttribute>특성이 있는 클래스에 대한 XAML 네임스코프 값을 제공하는 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> specifies a property that provides the XAML namescope value for the attributed class.</span></span> <span data-ttu-id="0887f-173">XAML namescope 속성은 실제 XAML <xref:System.Windows.Markup.INameScope> 네임스코프, 해당 저장소 및 해당 동작을 구현하고 보유하는 개체를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-173">The XAML namescope property is expected to reference an object that implements <xref:System.Windows.Markup.INameScope> and holds the actual XAML namescope, its store, and its behavior.</span></span>

### <a name="runtimenamepropertyattribute"></a><span data-ttu-id="0887f-174">런타임네임속성속성</span><span class="sxs-lookup"><span data-stu-id="0887f-174">RuntimeNamePropertyAttribute</span></span>

<span data-ttu-id="0887f-175">**참조 문서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-175">**Reference Documentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span></span>

<span data-ttu-id="0887f-176">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-176">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-177">**인수:** 특성형식의 런타임 name 속성의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-177">**Arguments:** A string that specifies the name of the run-time name property on the attributed type.</span></span>

<span data-ttu-id="0887f-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute>XAML [x:Name 지시문에](xname-directive.md)매핑되는 특성 형식의 속성을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> reports a property of the attributed type that maps to the XAML [x:Name Directive](xname-directive.md).</span></span> <span data-ttu-id="0887f-179">속성은 형식이어야 <xref:System.String> 하며 읽기/쓰기여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-179">The property must be of type <xref:System.String> and must be read/write.</span></span>

<span data-ttu-id="0887f-180">정의는 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-180">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="0887f-181">특정 파생 형식에 적용하여 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-181">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> on the specific derived type.</span></span>

### <a name="trimsurroundingwhitespaceattribute"></a><span data-ttu-id="0887f-182">트림주변화이트스페이스속성</span><span class="sxs-lookup"><span data-stu-id="0887f-182">TrimSurroundingWhitespaceAttribute</span></span>

<span data-ttu-id="0887f-183">**참조 문서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-183">**Reference Documentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span></span>

<span data-ttu-id="0887f-184">**다음에 적용됩니다.** 형식</span><span class="sxs-lookup"><span data-stu-id="0887f-184">**Applies to:** Types</span></span>

<span data-ttu-id="0887f-185">**인수:** 없음.</span><span class="sxs-lookup"><span data-stu-id="0887f-185">**Arguments:** None.</span></span>

<span data-ttu-id="0887f-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>공백 중요한 콘텐츠(컬렉션이 보유한 콘텐츠) 내에서 자식 요소로 나타날 수 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>있는 특정 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is applied to specific types that might appear as child elements within white-space significant content (content held by a collection that has <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>).</span></span> <span data-ttu-id="0887f-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>저장 경로와 주로 관련이 있지만 로드 경로의 XAML 형식 시스템에서 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>검사하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is mainly relevant to the save path, but is available in the XAML type system in the load path by examining <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0887f-188">자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0887f-188">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="typeconverterattribute"></a><span data-ttu-id="0887f-189">TypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="0887f-189">TypeConverterAttribute</span></span>

<span data-ttu-id="0887f-190">**참조 문서:**  <xref:System.ComponentModel.TypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-190">**Reference Documentation:**  <xref:System.ComponentModel.TypeConverterAttribute></span></span>

<span data-ttu-id="0887f-191">**다음에 적용됩니다.** 클래스, 속성, 메서드(유일한 XAML 유효한 메서드 `get` 사례는 연결 가능한 멤버를 지원하는 접근자).</span><span class="sxs-lookup"><span data-stu-id="0887f-191">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="0887f-192">**인수:** 의 <xref:System.Type> <xref:System.ComponentModel.TypeConverter>의</span><span class="sxs-lookup"><span data-stu-id="0887f-192">**Arguments:** The <xref:System.Type> of the <xref:System.ComponentModel.TypeConverter>.</span></span>

<span data-ttu-id="0887f-193"><xref:System.ComponentModel.TypeConverterAttribute>XAML 컨텍스트에서 사용자 <xref:System.ComponentModel.TypeConverter>지정 을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-193"><xref:System.ComponentModel.TypeConverterAttribute> in a XAML context references a custom <xref:System.ComponentModel.TypeConverter>.</span></span> <span data-ttu-id="0887f-194">이렇게 <xref:System.ComponentModel.TypeConverter> 하면 사용자 지정 형식 또는 해당 형식의 멤버에 대한 형식 변환 동작이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-194">This <xref:System.ComponentModel.TypeConverter> provides type conversion behavior for custom types, or members of that type.</span></span>

<span data-ttu-id="0887f-195">형식 <xref:System.ComponentModel.TypeConverterAttribute> 변환기 구현을 참조하여 형식에 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-195">Apply the <xref:System.ComponentModel.TypeConverterAttribute> attribute to your type, referencing your type converter implementation.</span></span> <span data-ttu-id="0887f-196">클래스, 구조 또는 인터페이스에서 XAML에 대한 형식 변환기를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-196">You can define type converters for XAML on classes, structures, or interfaces.</span></span> <span data-ttu-id="0887f-197">열거형에 대한 형식 변환을 제공할 필요가 없으며 해당 변환은 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-197">You do not need to provide type conversion for enumerations, that conversion is enabled natively.</span></span>

<span data-ttu-id="0887f-198">형식 변환기는 태그의 특성 또는 초기화 텍스트에 사용되는 문자열에서 의도한 대상 유형으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-198">Your type converter should be able to convert from a string that is used for attributes or initialization text in markup, into your intended destination type.</span></span> <span data-ttu-id="0887f-199">자세한 내용은 [TypeConverters 및 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0887f-199">For more information, see [TypeConverters and XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).</span></span>

<span data-ttu-id="0887f-200">형식의 모든 값에 적용하는 대신 XAML에 대한 형식 변환기 동작을 특정 속성에 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-200">Rather than applying to all values of a type, a type converter behavior for XAML can also be established on a specific property.</span></span> <span data-ttu-id="0887f-201">이 경우 속성 <xref:System.ComponentModel.TypeConverterAttribute> 정의(특정 `get` 정의 및 `set` 정의가 아닌 외부 정의)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-201">In this case, you apply <xref:System.ComponentModel.TypeConverterAttribute> to the property definition (the outer definition, not the specific `get` and `set` definitions).</span></span>

<span data-ttu-id="0887f-202">사용자 지정 연결 가능한 멤버의 XAML 사용에 대 한 형식 <xref:System.ComponentModel.TypeConverterAttribute> 변환기 동작 XAML 사용을 지 원하는 `get` 메서드 접근자에 적용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-202">A type converter behavior for XAML usage of a custom attachable member can be assigned by applying <xref:System.ComponentModel.TypeConverterAttribute> to the `get` method accessor that supports the XAML usage.</span></span>

<span data-ttu-id="0887f-203">와 <xref:System.ComponentModel.TypeConverter>유사합니다 .NET <xref:System.ComponentModel.TypeConverterAttribute> XAML이 존재 하기 전에 존재 하 고 형식 변환기 모델 다른 목적을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-203">Similar to <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existed in .NET prior to the existence of XAML, and the type converter model served other purposes.</span></span> <span data-ttu-id="0887f-204">을 참조하고 사용하려면 <xref:System.ComponentModel.TypeConverterAttribute>완전히 자격을 갖추거나 `using` 에 <xref:System.ComponentModel>대한 설명서를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-204">In order to reference and use <xref:System.ComponentModel.TypeConverterAttribute>, you must fully qualify it or provide a `using` statement for <xref:System.ComponentModel>.</span></span> <span data-ttu-id="0887f-205">또한 프로젝트에 시스템 어셈블리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-205">Also include the System assembly in your project.</span></span>

### <a name="uidpropertyattribute"></a><span data-ttu-id="0887f-206">UidProperty속성</span><span class="sxs-lookup"><span data-stu-id="0887f-206">UidPropertyAttribute</span></span>

<span data-ttu-id="0887f-207">**참조 문서:**  <xref:System.Windows.Markup.UidPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-207">**Reference Documentation:**  <xref:System.Windows.Markup.UidPropertyAttribute></span></span>

<span data-ttu-id="0887f-208">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-208">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-209">**인수:** 이름으로 관련 속성을 참조 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-209">**Arguments:** A string that references the relevant property by name.</span></span>

<span data-ttu-id="0887f-210">[x:Uid 지시문을](xuid-directive.md)별칭으로 하는 클래스의 CLR 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-210">Indicates the CLR property of a class that aliases the [x:Uid Directive](xuid-directive.md).</span></span>

### <a name="usableduringinitializationattribute"></a><span data-ttu-id="0887f-211">사용 가능한 초기화특성 동안</span><span class="sxs-lookup"><span data-stu-id="0887f-211">UsableDuringInitializationAttribute</span></span>

<span data-ttu-id="0887f-212">**참조 문서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-212">**Reference Documentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span></span>

<span data-ttu-id="0887f-213">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-213">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-214">**인수:** 부울.</span><span class="sxs-lookup"><span data-stu-id="0887f-214">**Arguments:** A Boolean.</span></span> <span data-ttu-id="0887f-215">특성의 의도된 용도에 사용되는 경우 값을 로 `true`설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-215">If used for the attribute's intended purpose, the value should be set to `true`.</span></span>

<span data-ttu-id="0887f-216">XAML 개체 그래프 를 만드는 동안 형식이 하향식으로 빌드되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-216">Indicates whether the type is built top-down during XAML object graph creation.</span></span> <span data-ttu-id="0887f-217">이 개념은 프로그래밍 모델의 정의와 밀접한 관련이 있는 고급 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-217">This is an advanced concept, which is probably closely related to the definition of your programming model.</span></span> <span data-ttu-id="0887f-218">자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0887f-218">For more information, see <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.</span></span>

### <a name="valueserializerattribute"></a><span data-ttu-id="0887f-219">값 직렬화기특성</span><span class="sxs-lookup"><span data-stu-id="0887f-219">ValueSerializerAttribute</span></span>

<span data-ttu-id="0887f-220">**참조 문서:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-220">**Reference Documentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span></span>

<span data-ttu-id="0887f-221">**다음에 적용됩니다.** 클래스, 속성, 메서드(유일한 XAML 유효한 메서드 `get` 사례는 연결 가능한 멤버를 지원하는 접근자).</span><span class="sxs-lookup"><span data-stu-id="0887f-221">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="0887f-222">**인수:** 특성이 있는 형식 또는 특정 특성 속성의 모든 속성을 직렬화할 때 사용할 값 serializer 지원 클래스를 지정하는 A입니다. <xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="0887f-222">**Arguments:** A <xref:System.Type> that specifies the value serializer support class to use when serializing all properties of the attributed type, or the specific attributed property.</span></span>

<span data-ttu-id="0887f-223"><xref:System.Windows.Markup.ValueSerializer>는 보다 더 많은 상태 및 컨텍스트를 필요로 <xref:System.ComponentModel.TypeConverter> 하는 값 직렬화 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-223"><xref:System.Windows.Markup.ValueSerializer> specifies a value serialization class that requires more state and context than a <xref:System.ComponentModel.TypeConverter> does.</span></span> <span data-ttu-id="0887f-224"><xref:System.Windows.Markup.ValueSerializer>연결 가능한 멤버에 대한 정적 <xref:System.Windows.Markup.ValueSerializerAttribute> `get` 접근자 메서드에 특성을 적용하여 연결할 수 있는 멤버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-224"><xref:System.Windows.Markup.ValueSerializer> can be associated with an attachable member by applying the <xref:System.Windows.Markup.ValueSerializerAttribute> attribute on the static `get` accessor method for the attachable member.</span></span> <span data-ttu-id="0887f-225">값 직렬화는 열거형, 인터페이스 및 구조에도 적용되지만 대리자에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-225">Value serialization is also applicable for enumerations, interfaces, and structures, but not for delegates.</span></span>

### <a name="whitespacesignificantcollectionattribute"></a><span data-ttu-id="0887f-226">화이트스페이스하한컬렉션속성</span><span class="sxs-lookup"><span data-stu-id="0887f-226">WhitespaceSignificantCollectionAttribute</span></span>

<span data-ttu-id="0887f-227">**참조 문서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-227">**Reference Documentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span></span>

<span data-ttu-id="0887f-228">**다음에 적용됩니다.** 개체 요소 주위의 공백이 UI 표현에 중요할 수 있는 혼합 콘텐츠를 호스트할 것으로 예상되는 클래스, 특히 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-228">**Applies to:** Class, specifically collection types that are expected to host mixed content, where white space around object elements might be significant for UI representation.</span></span>

<span data-ttu-id="0887f-229">**인수:** 없음.</span><span class="sxs-lookup"><span data-stu-id="0887f-229">**Arguments:** None.</span></span>

<span data-ttu-id="0887f-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>는 컬렉션 형식이 XAML 프로세서에 의해 중요한 공백으로 처리되어야 하며, 이는 컬렉션 내에서 XAML 노드 스트림의 값 노드 구성에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicates that a collection type should be processed as white-space significant by a XAML processor, which influences the construction of the XAML node stream's value nodes within the collection.</span></span> <span data-ttu-id="0887f-231">자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0887f-231">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="xamldeferloadattribute"></a><span data-ttu-id="0887f-232">XamlDefer로드특성</span><span class="sxs-lookup"><span data-stu-id="0887f-232">XamlDeferLoadAttribute</span></span>

<span data-ttu-id="0887f-233">**참조 문서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-233">**Reference Documentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span></span>

<span data-ttu-id="0887f-234">**다음에 적용됩니다.** 클래스, 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-234">**Applies to:** Class, property.</span></span>

<span data-ttu-id="0887f-235">**인수:** 두 어트리뷰트 폼 형식을 문자열로 지원하거나 <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="0887f-235">**Arguments:** Supports two attribution forms types as strings, or types as <xref:System.Type>.</span></span> <span data-ttu-id="0887f-236"><xref:System.Windows.Markup.XamlDeferLoadAttribute>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0887f-236">See <xref:System.Windows.Markup.XamlDeferLoadAttribute>.</span></span>

<span data-ttu-id="0887f-237">클래스 또는 속성에 XAML에 대한 지연된 로드 사용(예: 템플릿 동작)이 있음을 나타내고 지연 동작 및 해당 대상/콘텐츠 형식을 사용하도록 설정하는 클래스를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-237">Indicates that a class or property has a deferred load usage for XAML (such as a template behavior), and reports the class that enables the deferring behavior and its destination/content type.</span></span>

### <a name="xamlsetmarkupextensionattribute"></a><span data-ttu-id="0887f-238">XamlSetMarkup확장특성</span><span class="sxs-lookup"><span data-stu-id="0887f-238">XamlSetMarkupExtensionAttribute</span></span>

<span data-ttu-id="0887f-239">**참조 문서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-239">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span></span>

<span data-ttu-id="0887f-240">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-240">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-241">**인수:** 콜백 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-241">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="0887f-242">클래스가 태그 확장을 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내고 클래스의 모든 속성에서 태그 확장 집합 작업을 수행하기 전에 XAML 작성자가 호출해야 하는 처리기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-242">Indicates that a class can use a markup extension to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a markup extension set operation on any property of the class.</span></span>

### <a name="xamlsettypeconverterattribute"></a><span data-ttu-id="0887f-243">XamlSetType변환기속성</span><span class="sxs-lookup"><span data-stu-id="0887f-243">XamlSetTypeConverterAttribute</span></span>

<span data-ttu-id="0887f-244">**참조 문서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-244">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span></span>

<span data-ttu-id="0887f-245">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-245">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-246">**인수:** 콜백 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-246">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="0887f-247">클래스는 형식 변환기를 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내고 클래스의 모든 속성에서 형식 변환기 집합 작업을 수행하기 전에 XAML 작성자가 호출해야 하는 처리기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-247">Indicates that a class can use a type converter to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a type converter set operation on any property of the class.</span></span>

### <a name="xmllangpropertyattribute"></a><span data-ttu-id="0887f-248">XmlLang속성</span><span class="sxs-lookup"><span data-stu-id="0887f-248">XmlLangPropertyAttribute</span></span>

<span data-ttu-id="0887f-249">**참조 문서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-249">**Reference Documentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span></span>

<span data-ttu-id="0887f-250">**다음에 적용됩니다.** 클래스</span><span class="sxs-lookup"><span data-stu-id="0887f-250">**Applies to:** Class</span></span>

<span data-ttu-id="0887f-251">**인수:** 속성 이름을 특성식에 별칭으로 지정하는 `xml:lang` 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-251">**Arguments:** A string that specifies the name of the property to alias to `xml:lang` on the attributed type.</span></span>

<span data-ttu-id="0887f-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute>은 XML `lang` 지시문에 매핑되는 특성 형식의 속성을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> reports a property of the attributed type that maps to the XML `lang` directive.</span></span> <span data-ttu-id="0887f-253">속성은 반드시 형식이 <xref:System.String> 아니지만 문자열에서 할당할 수 있어야 합니다(형식 변환기를 속성의 형식 또는 특정 속성과 연결하여 할당할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0887f-253">The property is not necessarily of type <xref:System.String> but must be assignable from a string (assignment could be accomplished by associating a type converter with the property's type or with the specific property).</span></span> <span data-ttu-id="0887f-254">속성은 읽기/쓰기여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-254">The property must be read/write.</span></span>

<span data-ttu-id="0887f-255">매핑 `xml:lang` 시나리오는 런타임 개체 모델이 XMLDOM을 사용하여 특별히 처리하지 않고 XML 지정 언어 정보에 액세스할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-255">The scenario for mapping `xml:lang` is so that a runtime object model has access to XML-specified language information without specifically processing with an XMLDOM.</span></span>

<span data-ttu-id="0887f-256">정의는 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-256">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="0887f-257">드문 시나리오이지만 특정 파생 형식에 적용하여 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-257">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> on the specific derived type, although that is an uncommon scenario.</span></span>

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a><span data-ttu-id="0887f-258">어셈블리 수준에서의 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="0887f-258">XAML-Related CLR Attributes at the Assembly Level</span></span>

<span data-ttu-id="0887f-259">다음 섹션에서는 형식 또는 멤버 정의에 적용되지 않고 어셈블리에 적용되는 XAML 관련 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-259">The following sections describe the XAML-related attributes that are not applied to types or member definitions, but are instead applied to assemblies.</span></span> <span data-ttu-id="0887f-260">이러한 특성은 XAML에서 사용할 사용자 지정 형식을 포함하는 라이브러리를 정의하는 전반적인 목표와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-260">These attributes are pertinent to the overall goal of defining a library that contains custom types to use in XAML.</span></span> <span data-ttu-id="0887f-261">일부 특성이 반드시 XAML 노드 스트림에 직접 영향을 줄 필요는 없지만 다른 소비자가 사용할 수 있도록 노드 스트림에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-261">Some of the attributes do not necessarily influence the XAML node stream directly, but are passed on in the node stream for other consumers to use.</span></span> <span data-ttu-id="0887f-262">정보에 대한 소비자는 XAML 네임스페이스 정보 및 관련 접두사 정보가 필요한 설계 환경 또는 직렬화 프로세스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-262">Consumers for the information include design environments or serialization processes that need XAML namespace information and associated prefix information.</span></span> <span data-ttu-id="0887f-263">XAML 스키마 컨텍스트(.NET XAML 서비스 기본값 포함)도 이 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-263">A XAML schema context (including the .NET XAML Services default) also uses this information.</span></span>

### <a name="xmlnscompatiblewithattribute"></a><span data-ttu-id="0887f-264">Xmlns호환속성</span><span class="sxs-lookup"><span data-stu-id="0887f-264">XmlnsCompatibleWithAttribute</span></span>

<span data-ttu-id="0887f-265">**참조 문서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-265">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span></span>

<span data-ttu-id="0887f-266">**인수:**</span><span class="sxs-lookup"><span data-stu-id="0887f-266">**Arguments:**</span></span>

- <span data-ttu-id="0887f-267">XAML 네임스페이스의 식별자를 subsume로 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-267">A string that specifies the identifier of the XAML namespace to subsume.</span></span>

- <span data-ttu-id="0887f-268">이전 인수에서 XAML 네임스페이스를 subsume할 수 있는 XAML 네임스페이스의 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-268">A string that specifies the identifier of the XAML namespace that can subsume the XAML namespace from the previous argument.</span></span>

  <span data-ttu-id="0887f-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>XAML 네임스페이스를 다른 XAML 네임스페이스에 의해 subsumed할 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> specifies that a XAML namespace can be subsumed by another XAML namespace.</span></span> <span data-ttu-id="0887f-270">일반적으로 포함하는 XAML 네임스페이스는 미리 정의된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-270">Typically, the subsuming XAML namespace is indicated in a previously defined <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span> <span data-ttu-id="0887f-271">이 기술은 라이브러리에서 XAML 어휘를 버전화하고 이전 버전의 어휘에 대해 이전에 정의된 태그와 호환되도록 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-271">This technique can be used for versioning a XAML vocabulary in a library and to make it compatible with previously defined markup against the earlier versioned vocabulary.</span></span>

### <a name="xmlnsdefinitionattribute"></a><span data-ttu-id="0887f-272">Xmlns정의속성</span><span class="sxs-lookup"><span data-stu-id="0887f-272">XmlnsDefinitionAttribute</span></span>

<span data-ttu-id="0887f-273">**참조 문서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-273">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span></span>

<span data-ttu-id="0887f-274">**인수:**</span><span class="sxs-lookup"><span data-stu-id="0887f-274">**Arguments:**</span></span>

- <span data-ttu-id="0887f-275">정의할 XAML 네임스페이스의 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-275">A string that specifies the identifier of the XAML namespace to define.</span></span>

- <span data-ttu-id="0887f-276">CLR 네임스페이스의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-276">A string that names a CLR namespace.</span></span> <span data-ttu-id="0887f-277">CLR 네임스페이스는 어셈블리에서 공용 형식을 정의해야 하며, CLR 네임스페이스 유형 중 하나 이상이 XAML 사용을 위해 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-277">The CLR namespace should define public types in your assembly, and at least one of the CLR namespace types should be intended for XAML usage.</span></span>

  <span data-ttu-id="0887f-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 네임스페이스와 CLR 네임스페이스 사이의 어셈블리별로 매핑을 지정한 다음 XAML 개체 작성기 또는 XAML 스키마 컨텍스트에서 형식 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a mapping on a per-assembly basis between a XAML namespace and a CLR namespace, which is then used for type resolution by a XAML object writer or XAML schema context.</span></span>

  <span data-ttu-id="0887f-279">어셈블리에 두 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 개 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-279">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="0887f-280">이 작업은 다음과 같은 이유로 인해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-280">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="0887f-281">라이브러리 디자인에는 런타임 API 액세스의 논리적 조직을 위한 여러 CLR 네임스페이스가 포함되어 있습니다. 그러나 동일한 XAML 네임스페이스를 참조하여 해당 네임스페이스의 모든 형식을 XAML로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-281">The library design contains multiple CLR namespaces for logical organization of run-time API access; however, you want all types in those namespaces to be XAML-usable by referencing the same XAML namespace.</span></span> <span data-ttu-id="0887f-282">이 경우 동일한 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값이지만 다른 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 값을 사용하여 여러 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-282">In this case, you apply several <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributes using the same <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value but different <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> values.</span></span> <span data-ttu-id="0887f-283">이 기능은 프레임워크 또는 응용 프로그램이 일반적인 사용에서 기본 XAML 네임스페이스로 의도하는 XAML 네임스페이스에 대한 매핑을 정의하는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-283">This is especially useful if you are defining mappings for the XAML namespace that your framework or application intends to be the default XAML namespace in common usage.</span></span>

- <span data-ttu-id="0887f-284">라이브러리 디자인에는 여러 CLR 네임스페이스가 포함되어 있으며 해당 CLR 네임스페이스에서 형식의 사용 법 간에 의도적으로 XAML 네임스페이스를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-284">The library design contains multiple CLR namespaces, and you want a deliberate XAML namespace separation between the usages of types in those CLR namespaces.</span></span>

- <span data-ttu-id="0887f-285">어셈블리에서 CLR 네임스페이스를 정의하고 두 개 이상의 XAML 네임스페이스를 통해 액세스할 수 있도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-285">You define a CLR namespace in the assembly, and you want it to be accessible through more than one XAML namespace.</span></span> <span data-ttu-id="0887f-286">이 시나리오는 동일한 코드베이스를 통해 여러 어휘를 지원할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-286">This scenario occurs when you are supporting multiple vocabularies with the same codebase.</span></span>

- <span data-ttu-id="0887f-287">하나 이상의 CLR 네임스페이스에서 XAML 언어 지원을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-287">You define XAML language support in one or more CLR namespaces.</span></span> <span data-ttu-id="0887f-288">이 경우 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값은 이어야 `http://schemas.microsoft.com/winfx/2006/xaml`합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-288">In this case, the <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value should be `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span>

### <a name="xmlnsprefixattribute"></a><span data-ttu-id="0887f-289">Xmlns사전수정속성</span><span class="sxs-lookup"><span data-stu-id="0887f-289">XmlnsPrefixAttribute</span></span>

<span data-ttu-id="0887f-290">**참조 문서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span><span class="sxs-lookup"><span data-stu-id="0887f-290">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span></span>

<span data-ttu-id="0887f-291">**인수:**</span><span class="sxs-lookup"><span data-stu-id="0887f-291">**Arguments:**</span></span>

- <span data-ttu-id="0887f-292">XAML 네임스페이스의 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-292">A string that specifies the identifier of a XAML namespace.</span></span>

- <span data-ttu-id="0887f-293">권장 접두사를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-293">A string that specifies a recommended prefix.</span></span>

  <span data-ttu-id="0887f-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 네임스페이스에 사용할 권장 접두사를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a recommended prefix to use for a XAML namespace.</span></span> <span data-ttu-id="0887f-295">접두사는 .NET XAML 서비스에서 <xref:System.Xaml.XamlXmlWriter>직렬화된 XAML 파일의 요소 및 특성을 작성하거나 XAML 구현 라이브러리가 XAML 편집 기능이 있는 디자인 환경과 상호 작용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-295">The prefix is useful when writing elements and attributes in a XAML file that is serialized by .NET XAML Services <xref:System.Xaml.XamlXmlWriter>, or when a XAML-implementing library interacts with a design environment that has XAML editing features.</span></span>

  <span data-ttu-id="0887f-296">어셈블리에 두 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 개 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-296">More than one <xref:System.Windows.Markup.XmlnsPrefixAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="0887f-297">이 작업은 다음과 같은 이유로 인해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-297">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="0887f-298">어셈블리는 두 개 이상의 XAML 네임스페이스에 대한 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-298">Your assembly defines types for more than one XAML namespace.</span></span> <span data-ttu-id="0887f-299">이 경우 각 XAML 네임스페이스에 대해 서로 다른 접두사 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-299">In this case, define different prefix values for each XAML namespace.</span></span>

- <span data-ttu-id="0887f-300">여러 어휘를 지원하고 있으며 각 어휘와 XAML 네임스페이스에 대해 서로 다른 접두사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-300">You are supporting multiple vocabularies, and you use different prefixes for each vocabulary and XAML namespace.</span></span>

- <span data-ttu-id="0887f-301">어셈블리에서 XAML 언어 지원을 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 정의하고 에 대해 `http://schemas.microsoft.com/winfx/2006/xaml`</span><span class="sxs-lookup"><span data-stu-id="0887f-301">You define XAML language support in the assembly and have a <xref:System.Windows.Markup.XmlnsDefinitionAttribute> for `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span> <span data-ttu-id="0887f-302">이 경우 일반적으로 접두사를 `x`승격해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-302">In this case, you typically should promote the prefix `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="0887f-303">.NET XAML 서비스는 XAML 관련 특성도 <xref:System.Windows.Markup.RootNamespaceAttribute>정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-303">.NET XAML Services also defines the XAML-related attribute <xref:System.Windows.Markup.RootNamespaceAttribute>.</span></span> <span data-ttu-id="0887f-304">이 특성은 프로젝트 시스템 지원에 대한 어셈블리 수준 특성이며 XAML 사용자 지정 형식과는 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0887f-304">This attribute is an assembly-level attribute for project system support, and it is not relevant for XAML custom types.</span></span>

## <a name="see-also"></a><span data-ttu-id="0887f-305">참조</span><span class="sxs-lookup"><span data-stu-id="0887f-305">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="0887f-306">.NET XAML 서비스에서 사용할 사용자 지정 형식 정의</span><span class="sxs-lookup"><span data-stu-id="0887f-306">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
