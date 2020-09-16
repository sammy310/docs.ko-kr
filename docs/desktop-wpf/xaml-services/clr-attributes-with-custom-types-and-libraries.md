---
title: 사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: a4b8a58ea2c7d9de2b59ed78dc37e4ce1c434b79
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535399"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a><span data-ttu-id="f118b-102">사용자 지정 형식 및 라이브러리에 대 한 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="f118b-102">XAML-related CLR attributes for custom types and libraries</span></span>

<span data-ttu-id="f118b-103">이 항목에서는 .NET XAML 서비스에서 정의 되는 CLR (공용 언어 런타임) 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-103">This topic describes the common language runtime (CLR) attributes that are defined by .NET XAML Services.</span></span> <span data-ttu-id="f118b-104">또한 응용 프로그램에 대 한 XAML 관련 시나리오를 포함 하는 .NET에 정의 된 다른 CLR 특성도 어셈블리 또는 형식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-104">It also describes other CLR attributes that are defined in .NET that have a XAML-related scenario for application to assemblies or types.</span></span> <span data-ttu-id="f118b-105">이러한 CLR 특성을 사용 하 여 어셈블리, 형식 또는 멤버를 특성으로 사용 하면 형식과 관련 된 XAML 형식 시스템 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-105">Attributing assemblies, types, or members with these CLR attributes provides XAML type system information related to your types.</span></span> <span data-ttu-id="f118b-106">XAML 노드 스트림을 직접 처리 하거나 전용 XAML 판독기와 XAML 작성기를 통해 .NET XAML 서비스를 사용 하는 모든 XAML 소비자에 게 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-106">Information is provided to any XAML consumer that uses .NET XAML Services for processing the XAML node stream directly or through the dedicated XAML readers and XAML writers.</span></span>

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a><span data-ttu-id="f118b-107">사용자 지정 형식 및 사용자 지정 멤버에 대 한 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="f118b-107">XAML-Related CLR Attributes for Custom Types and Custom Members</span></span>

<span data-ttu-id="f118b-108">CLR 특성을 사용 하려면 전체 CLR을 사용 하 여 형식을 정의 해야 합니다. 그렇지 않으면 이러한 특성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-108">Using CLR attributes entails that you are using the overall CLR to define your types, otherwise such attributes are not available.</span></span> <span data-ttu-id="f118b-109">CLR을 사용 하 여 형식 지원을 정의 하는 경우 .NET XAML 서비스 XAML 작성기에서 사용 하는 기본 XAML 스키마 컨텍스트는 지원 어셈블리에 대해 리플렉션을 통해 CLR 특성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-109">If you use the CLR to define type backing, then the default XAML schema context used by .NET XAML Services XAML writers can read CLR attribution through reflection against backing assemblies.</span></span>

<span data-ttu-id="f118b-110">다음 섹션에서는 사용자 지정 형식 또는 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-110">The following sections describe the XAML-related attributes that you can apply to custom types or custom members.</span></span> <span data-ttu-id="f118b-111">각 CLR 특성은 XAML 형식 시스템과 관련 된 정보를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-111">Each CLR attribute communicates information that is relevant to a XAML type system.</span></span> <span data-ttu-id="f118b-112">로드 경로에서 특성을 사용 하는 정보는 xaml 판독기가 유효한 XAML 노드 스트림을 만드는 데 도움이 되거나 XAML 작성기가 유효한 개체 그래프를 생성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-112">In the load path, the attributed information either helps the XAML reader form a valid XAML node stream, or it helps the XAML writer produce a valid object graph.</span></span> <span data-ttu-id="f118b-113">저장 경로에서 특성이 지정 된 정보는 xaml 판독기가 XAML 형식 시스템 정보를 다시 구성 하는 유효한 XAML 노드 스트림을 만드는 데 도움이 됩니다. 또는 XAML 작성기 또는 다른 XAML 소비자에 대 한 serialization 힌트 또는 요구 사항을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-113">In the save path, the attributed information either helps the XAML reader form a valid XAML node stream that reconstitutes XAML type system information; or it declares serialization hints or requirements for the XAML writer or other XAML consumers.</span></span>

### <a name="ambientattribute"></a><span data-ttu-id="f118b-114">AmbientAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-114">AmbientAttribute</span></span>

<span data-ttu-id="f118b-115">**참조 설명서:**<xref:System.Windows.Markup.AmbientAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-115">**Reference Documentation:** <xref:System.Windows.Markup.AmbientAttribute></span></span>

<span data-ttu-id="f118b-116">**적용 대상:** 연결할 수 있는 속성을 지 원하는 클래스, 속성 또는 `get` 접근자 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-116">**Applies to:** Class, property, or `get` accessor members that support attachable properties.</span></span>

<span data-ttu-id="f118b-117">**인수:** 없음을</span><span class="sxs-lookup"><span data-stu-id="f118b-117">**Arguments:** None</span></span>

<span data-ttu-id="f118b-118"><xref:System.Windows.Markup.AmbientAttribute> 속성이 나 특성 형식을 사용 하는 모든 속성이 XAML의 앰비언트 속성 개념에서 해석 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-118"><xref:System.Windows.Markup.AmbientAttribute> indicates that the property, or all properties that take the attributed type, should be interpreted under the ambient property concept in XAML.</span></span> <span data-ttu-id="f118b-119">앰비언트 개념은 XAML 프로세서가 멤버의 형식 소유자를 결정하는 방법과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-119">The ambient concept relates to how XAML processors determine type owners of members.</span></span> <span data-ttu-id="f118b-120">앰비언트 속성은 개체 그래프를 만들 때 파서 컨텍스트에서 값을 사용할 수 있어야 하지만 직접 XAML 노드 집합에 대해 일반적인 형식 멤버 조회가 일시 중단 되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-120">An ambient property is a property where the value is expected to be available in the parser context when creating an object graph, but where typical type-member lookup is suspended for the immediate XAML node set being created.</span></span>

<span data-ttu-id="f118b-121">앰비언트 개념은 CLR 특성을 정의 하는 방법에 따라 속성으로 표시 되지 않는 연결 가능한 멤버에 적용 될 수 있습니다 <xref:System.AttributeTargets> .</span><span class="sxs-lookup"><span data-stu-id="f118b-121">The ambient concept can be applied to attachable members, which are not represented as properties in terms of how CLR attribution defines <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="f118b-122">메서드 특성 사용은 `get` XAML에 연결할 수 있는 사용을 지 원하는 접근자에만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-122">The method attribution usage should be applied only for a `get` accessor that supports attachable usage for XAML.</span></span>

### <a name="constructorargumentattribute"></a><span data-ttu-id="f118b-123">ConstructorArgumentAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-123">ConstructorArgumentAttribute</span></span>

<span data-ttu-id="f118b-124">**참조 설명서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-124">**Reference Documentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span></span>

<span data-ttu-id="f118b-125">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-125">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-126">**인수:** 단일 생성자 인수와 일치 하는 속성의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-126">**Arguments:** A string that specifies the name of the property that matches a single constructor argument.</span></span>

<span data-ttu-id="f118b-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> 매개 변수가 없는 생성자 구문을 사용 하 여 개체를 초기화할 수 있고 지정 된 이름의 속성이 생성 정보를 제공 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> specifies that an object can be initialized by using a non-parameterless constructor syntax, and that a property of the specified name supplies construction information.</span></span> <span data-ttu-id="f118b-128">이 정보는 주로 XAML serialization용입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-128">This information is primarily for XAML serialization.</span></span> <span data-ttu-id="f118b-129">자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-129">For more information, see <xref:System.Windows.Markup.ConstructorArgumentAttribute>.</span></span>

### <a name="contentpropertyattribute"></a><span data-ttu-id="f118b-130">ContentPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-130">ContentPropertyAttribute</span></span>

<span data-ttu-id="f118b-131">**참조 설명서:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-131">**Reference Documentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span></span>

<span data-ttu-id="f118b-132">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-132">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-133">**인수:** 특성 사용 형식의 멤버 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-133">**Arguments:** A string that specifies the name of a member of the attributed type.</span></span>

<span data-ttu-id="f118b-134"><xref:System.Windows.Markup.ContentPropertyAttribute> 인수에 의해 이름이 지정 된 속성이 해당 형식에 대 한 XAML 콘텐츠 속성으로 사용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-134"><xref:System.Windows.Markup.ContentPropertyAttribute> indicates that the property as named by the argument should serve as the XAML content property for that type.</span></span> <span data-ttu-id="f118b-135">XAML 콘텐츠 속성 정의는 정의 형식에 할당할 수 있는 모든 파생 형식에 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-135">The XAML content property definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="f118b-136">특정 파생 형식에를 적용 하 여 특정 파생 형식에 대 한 정의를 재정의할 수 있습니다 <xref:System.Windows.Markup.ContentPropertyAttribute> .</span><span class="sxs-lookup"><span data-stu-id="f118b-136">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.ContentPropertyAttribute> on the specific derived type.</span></span>

<span data-ttu-id="f118b-137">XAML 콘텐츠 속성으로 사용 되는 속성의 경우 속성에 대 한 속성 요소 태그 지정은 XAML 사용에서 생략 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-137">For the property that serves as the XAML content property, property element tagging for the property can be omitted in the XAML usage.</span></span> <span data-ttu-id="f118b-138">일반적으로 콘텐츠 및 포함 모델에 대해 간소화 된 XAML 태그의 수준을 올리는 XAML 콘텐츠 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-138">Typically, you designate XAML content properties that promote a streamlined XAML markup for your content and containment models.</span></span> <span data-ttu-id="f118b-139">하나의 멤버만 XAML 콘텐츠 속성으로 지정할 수 있기 때문에 일부 형식의 컨테이너 속성을 XAML 콘텐츠 속성으로 지정 해야 하는 것에 대 한 디자인 선택 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-139">Because only one member can be designated as the XAML content property, you sometimes have design choices to make regarding which of several container properties of a type should be designated as the XAML content property.</span></span> <span data-ttu-id="f118b-140">다른 컨테이너 속성은 명시적 속성 요소와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-140">The other container properties must be used with explicit property elements.</span></span>

<span data-ttu-id="f118b-141">XAML 노드 스트림에서 XAML 콘텐츠 속성은 여전히의 `StartMember` `EndMember` 속성 이름을 사용 하 여 및 노드를 생성 <xref:System.Xaml.XamlMember> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-141">In the XAML node stream, XAML content properties still produce `StartMember` and `EndMember` nodes, using the name of the property for the <xref:System.Xaml.XamlMember>.</span></span> <span data-ttu-id="f118b-142">멤버가 XAML 콘텐츠 속성 인지 확인 하려면 위치에서 값을 검사 하 <xref:System.Xaml.XamlType> `StartObject` 고 값을 가져옵니다 <xref:System.Xaml.XamlType.ContentProperty%2A> .</span><span class="sxs-lookup"><span data-stu-id="f118b-142">To determine whether a member is the XAML content property, examine the <xref:System.Xaml.XamlType> value from the `StartObject` position and obtain the value of <xref:System.Xaml.XamlType.ContentProperty%2A>.</span></span>

### <a name="contentwrapperattribute"></a><span data-ttu-id="f118b-143">ContentWrapperAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-143">ContentWrapperAttribute</span></span>

<span data-ttu-id="f118b-144">**참조 설명서:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-144">**Reference Documentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span></span>

<span data-ttu-id="f118b-145">**적용 대상:** 클래스, 특히 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-145">**Applies to:** Class, specifically collection types.</span></span>

<span data-ttu-id="f118b-146">**인수:** <xref:System.Type> 외부 콘텐츠의 콘텐츠 래퍼 형식으로 사용할 형식을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-146">**Arguments:** A <xref:System.Type> that specifies the type to use as the content wrapper type for foreign content.</span></span>

<span data-ttu-id="f118b-147"><xref:System.Windows.Markup.ContentWrapperAttribute> 외부 콘텐츠를 래핑하는 데 사용할 연결 된 컬렉션 형식에 하나 이상의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-147"><xref:System.Windows.Markup.ContentWrapperAttribute> specifies one or more types on the associated collection type that will be used to wrap foreign content.</span></span> <span data-ttu-id="f118b-148">외부 콘텐츠는 콘텐츠 속성의 형식에 대 한 형식 시스템 제약 조건이 소유 형식의 XAML 사용에서 지원할 수 있는 모든 콘텐츠 사례를 캡처하지 않는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-148">Foreign content refers to cases where the type system constraints on the type of the content property do not capture all of the possible content cases that XAML usage for the owning type would support.</span></span> <span data-ttu-id="f118b-149">예를 들어 특정 형식의 콘텐츠에 대 한 XAML 지원은 강력한 형식의 제네릭에서 문자열을 지원할 수 있습니다 <xref:System.Collections.ObjectModel.Collection%601> .</span><span class="sxs-lookup"><span data-stu-id="f118b-149">For example, XAML support for content of a particular type might support strings in a strongly typed generic <xref:System.Collections.ObjectModel.Collection%601>.</span></span> <span data-ttu-id="f118b-150">콘텐츠 래퍼는 텍스트 관련 콘텐츠 모델 마이그레이션과 같이 컬렉션에 대해 기존 태그 규칙을 XAML의 conception 할당 가능한 값으로 마이그레이션하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-150">Content wrappers are useful for migrating pre-existing markup conventions into XAML's conception of assignable values for collections, such as migrating text-related content models.</span></span>

<span data-ttu-id="f118b-151">콘텐츠 래퍼 유형을 두 개 이상 지정 하려면 특성을 여러 번 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-151">To specify more than one content wrapper type, apply the attribute multiple times.</span></span>

### <a name="dependsonattribute"></a><span data-ttu-id="f118b-152">DependsOnAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-152">DependsOnAttribute</span></span>

<span data-ttu-id="f118b-153">**참조 설명서:**  <xref:System.Windows.Markup.DependsOnAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-153">**Reference Documentation:**  <xref:System.Windows.Markup.DependsOnAttribute></span></span>

<span data-ttu-id="f118b-154">**적용 대상:** 속성</span><span class="sxs-lookup"><span data-stu-id="f118b-154">**Applies to:** Property</span></span>

<span data-ttu-id="f118b-155">**인수:** 특성 사용 형식에 대 한 다른 멤버의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-155">**Arguments:** A string that specifies the name of another member of the attributed type.</span></span>

<span data-ttu-id="f118b-156"><xref:System.Windows.Markup.DependsOnAttribute> 특성 사용 속성이 다른 속성의 값에 종속 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-156"><xref:System.Windows.Markup.DependsOnAttribute> indicates that the attributed property depends on the value of another property.</span></span> <span data-ttu-id="f118b-157">속성 정의에이 특성을 적용 하면 종속 속성이 XAML 개체 쓰기에서 먼저 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-157">Applying this attribute to a property definition ensures that the dependent properties are processed first in XAML object writing.</span></span> <span data-ttu-id="f118b-158">를 사용 <xref:System.Windows.Markup.DependsOnAttribute> 하 여 유효한 개체 생성을 위해 특정 구문 분석 순서를 따라야 하는 형식에 대 한 속성의 예외적인 사례를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-158">Usages of <xref:System.Windows.Markup.DependsOnAttribute> specify the exceptional cases of properties on types where a specific order of parsing must be followed for valid object creation.</span></span>

<span data-ttu-id="f118b-159"><xref:System.Windows.Markup.DependsOnAttribute>속성 정의에 여러 사례를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-159">You can apply multiple <xref:System.Windows.Markup.DependsOnAttribute> cases to a property definition.</span></span>

### <a name="markupextensionreturntypeattribute"></a><span data-ttu-id="f118b-160">MarkupExtensionReturnTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-160">MarkupExtensionReturnTypeAttribute</span></span>

<span data-ttu-id="f118b-161">**참조 설명서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-161">**Reference Documentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span></span>

<span data-ttu-id="f118b-162">**적용 대상:** 파생 형식으로 예상 되는 클래스입니다 <xref:System.Windows.Markup.MarkupExtension> .</span><span class="sxs-lookup"><span data-stu-id="f118b-162">**Applies to:** Class, which is expected to be a <xref:System.Windows.Markup.MarkupExtension> derived type.</span></span>

<span data-ttu-id="f118b-163">**인수:** <xref:System.Type> 특성의 결과로 가장 정확 하 게 예측할 형식을 지정 하는입니다 `ProvideValue` <xref:System.Windows.Markup.MarkupExtension> .</span><span class="sxs-lookup"><span data-stu-id="f118b-163">**Arguments:** A <xref:System.Type> that specifies the most precise type to expect as the `ProvideValue` result of the attributed <xref:System.Windows.Markup.MarkupExtension>.</span></span>

<span data-ttu-id="f118b-164">자세한 내용은 [XAML 태그 확장 개요](markup-extensions-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-164">For more information, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

### <a name="namescopepropertyattribute"></a><span data-ttu-id="f118b-165">NameScopePropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-165">NameScopePropertyAttribute</span></span>

<span data-ttu-id="f118b-166">**참조 설명서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-166">**Reference Documentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span></span>

<span data-ttu-id="f118b-167">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-167">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-168">**인수:** 에서는 두 가지 형식의 특성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-168">**Arguments:** Supports two forms of attribution:</span></span>

- <span data-ttu-id="f118b-169">특성 사용 형식에 대 한 속성의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-169">A string that specifies the name of a property on the attributed type.</span></span>

- <span data-ttu-id="f118b-170">속성의 이름과 <xref:System.Type> 명명 된 속성을 정의 하는 형식에 대 한를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-170">A string that specifies the name of a property, and a <xref:System.Type> for the type that defines the named property.</span></span> <span data-ttu-id="f118b-171">이 폼은 연결 가능한 멤버를 XAML 이름 범위 속성으로 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-171">This form is for specifying an attachable member as the XAML namescope property.</span></span>

<span data-ttu-id="f118b-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> 특성 사용 클래스에 대 한 XAML 이름 범위 값을 제공 하는 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> specifies a property that provides the XAML namescope value for the attributed class.</span></span> <span data-ttu-id="f118b-173">XAML 이름 범위 속성은 <xref:System.Windows.Markup.INameScope> 실제 xaml 이름 범위, 해당 저장소 및 해당 동작을 구현 하 고 유지 하는 개체를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-173">The XAML namescope property is expected to reference an object that implements <xref:System.Windows.Markup.INameScope> and holds the actual XAML namescope, its store, and its behavior.</span></span>

### <a name="runtimenamepropertyattribute"></a><span data-ttu-id="f118b-174">RuntimeNamePropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-174">RuntimeNamePropertyAttribute</span></span>

<span data-ttu-id="f118b-175">**참조 설명서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-175">**Reference Documentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span></span>

<span data-ttu-id="f118b-176">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-176">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-177">**인수:** 특성 사용 형식에 대 한 런타임 이름 속성의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-177">**Arguments:** A string that specifies the name of the run-time name property on the attributed type.</span></span>

<span data-ttu-id="f118b-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> XAML [X:Name 지시문](xname-directive.md)에 매핑되는 특성 사용 형식의 속성을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> reports a property of the attributed type that maps to the XAML [x:Name Directive](xname-directive.md).</span></span> <span data-ttu-id="f118b-179">속성은 형식 이어야 <xref:System.String> 하며 읽기/쓰기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-179">The property must be of type <xref:System.String> and must be read/write.</span></span>

<span data-ttu-id="f118b-180">정의는 정의 형식에 할당할 수 있는 모든 파생 형식에 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-180">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="f118b-181">특정 파생 형식에를 적용 하 여 특정 파생 형식에 대 한 정의를 재정의할 수 있습니다 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> .</span><span class="sxs-lookup"><span data-stu-id="f118b-181">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> on the specific derived type.</span></span>

### <a name="trimsurroundingwhitespaceattribute"></a><span data-ttu-id="f118b-182">TrimSurroundingWhitespaceAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-182">TrimSurroundingWhitespaceAttribute</span></span>

<span data-ttu-id="f118b-183">**참조 설명서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-183">**Reference Documentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span></span>

<span data-ttu-id="f118b-184">**적용 대상:** 종류</span><span class="sxs-lookup"><span data-stu-id="f118b-184">**Applies to:** Types</span></span>

<span data-ttu-id="f118b-185">**인수:** 없음을.</span><span class="sxs-lookup"><span data-stu-id="f118b-185">**Arguments:** None.</span></span>

<span data-ttu-id="f118b-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 는 공백 유효 콘텐츠 내에 자식 요소로 나타날 수 있는 특정 형식에 적용 됩니다 (가 있는 컬렉션에서 콘텐츠 보유 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> ).</span><span class="sxs-lookup"><span data-stu-id="f118b-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is applied to specific types that might appear as child elements within white-space significant content (content held by a collection that has <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>).</span></span> <span data-ttu-id="f118b-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 는 주로 저장 경로와 관련이 있지만를 검사 하 여 로드 경로의 XAML 형식 시스템에서 사용할 수 있습니다 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f118b-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is mainly relevant to the save path, but is available in the XAML type system in the load path by examining <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f118b-188">자세한 내용은 [XAML의 공백 처리](white-space-processing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-188">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="typeconverterattribute"></a><span data-ttu-id="f118b-189">TypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-189">TypeConverterAttribute</span></span>

<span data-ttu-id="f118b-190">**참조 설명서:**  <xref:System.ComponentModel.TypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-190">**Reference Documentation:**  <xref:System.ComponentModel.TypeConverterAttribute></span></span>

<span data-ttu-id="f118b-191">**적용 대상:** 클래스, 속성, 메서드 (유일 하 게 XAML 유효한 메서드 대/소문자는 연결 `get` 가능한 멤버를 지 원하는 접근자).</span><span class="sxs-lookup"><span data-stu-id="f118b-191">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="f118b-192">**인수:** <xref:System.Type> 의입니다 <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="f118b-192">**Arguments:** The <xref:System.Type> of the <xref:System.ComponentModel.TypeConverter>.</span></span>

<span data-ttu-id="f118b-193"><xref:System.ComponentModel.TypeConverterAttribute> XAML 컨텍스트에서는 사용자 지정를 참조 <xref:System.ComponentModel.TypeConverter> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-193"><xref:System.ComponentModel.TypeConverterAttribute> in a XAML context references a custom <xref:System.ComponentModel.TypeConverter>.</span></span> <span data-ttu-id="f118b-194">이 <xref:System.ComponentModel.TypeConverter> 는 사용자 지정 형식 또는 해당 형식의 멤버에 대 한 형식 변환 동작을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-194">This <xref:System.ComponentModel.TypeConverter> provides type conversion behavior for custom types, or members of that type.</span></span>

<span data-ttu-id="f118b-195">형식에 특성을 적용 하 여 <xref:System.ComponentModel.TypeConverterAttribute> 형식 변환기 구현을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-195">Apply the <xref:System.ComponentModel.TypeConverterAttribute> attribute to your type, referencing your type converter implementation.</span></span> <span data-ttu-id="f118b-196">클래스, 구조체 또는 인터페이스의 XAML에 대 한 형식 변환기를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-196">You can define type converters for XAML on classes, structures, or interfaces.</span></span> <span data-ttu-id="f118b-197">열거형에 대해 형식 변환을 제공할 필요는 없으며, 기본적으로 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-197">You do not need to provide type conversion for enumerations, that conversion is enabled natively.</span></span>

<span data-ttu-id="f118b-198">형식 변환기는 태그의 특성 또는 초기화 텍스트에 사용 되는 문자열을 원하는 대상 형식으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-198">Your type converter should be able to convert from a string that is used for attributes or initialization text in markup, into your intended destination type.</span></span> <span data-ttu-id="f118b-199">자세한 내용은 [typeconverter 및 XAML](/dotnet/desktop/wpf/advanced/typeconverters-and-xaml)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-199">For more information, see [TypeConverters and XAML](/dotnet/desktop/wpf/advanced/typeconverters-and-xaml).</span></span>

<span data-ttu-id="f118b-200">형식의 모든 값에 적용 하는 대신 XAML의 형식 변환기 동작도 특정 속성에 대해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-200">Rather than applying to all values of a type, a type converter behavior for XAML can also be established on a specific property.</span></span> <span data-ttu-id="f118b-201">이 경우 <xref:System.ComponentModel.TypeConverterAttribute> 속성 정의 (특정 및 정의가 아닌 외부 정의)에 적용 `get` `set` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-201">In this case, you apply <xref:System.ComponentModel.TypeConverterAttribute> to the property definition (the outer definition, not the specific `get` and `set` definitions).</span></span>

<span data-ttu-id="f118b-202">사용자 지정 연결 가능 멤버의 XAML 사용에 대 한 형식 변환기 동작은 <xref:System.ComponentModel.TypeConverterAttribute> `get` xaml 사용을 지 원하는 메서드 접근자에를 적용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-202">A type converter behavior for XAML usage of a custom attachable member can be assigned by applying <xref:System.ComponentModel.TypeConverterAttribute> to the `get` method accessor that supports the XAML usage.</span></span>

<span data-ttu-id="f118b-203">와 유사 <xref:System.ComponentModel.TypeConverter> <xref:System.ComponentModel.TypeConverterAttribute> 합니다 .이는 XAML이 존재 하기 이전에 .net에 존재 하 고 형식 변환기 모델은 다른 용도를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-203">Similar to <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existed in .NET prior to the existence of XAML, and the type converter model served other purposes.</span></span> <span data-ttu-id="f118b-204">를 참조 하 고 사용 하려면를 <xref:System.ComponentModel.TypeConverterAttribute> 정규화 하거나 `using` 에 대 한 문을 제공 해야 합니다 <xref:System.ComponentModel> .</span><span class="sxs-lookup"><span data-stu-id="f118b-204">In order to reference and use <xref:System.ComponentModel.TypeConverterAttribute>, you must fully qualify it or provide a `using` statement for <xref:System.ComponentModel>.</span></span> <span data-ttu-id="f118b-205">또한 프로젝트에 시스템 어셈블리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-205">Also include the System assembly in your project.</span></span>

### <a name="uidpropertyattribute"></a><span data-ttu-id="f118b-206">UidPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-206">UidPropertyAttribute</span></span>

<span data-ttu-id="f118b-207">**참조 설명서:**  <xref:System.Windows.Markup.UidPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-207">**Reference Documentation:**  <xref:System.Windows.Markup.UidPropertyAttribute></span></span>

<span data-ttu-id="f118b-208">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-208">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-209">**인수:** 이름으로 관련 속성을 참조 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-209">**Arguments:** A string that references the relevant property by name.</span></span>

<span data-ttu-id="f118b-210">[X:Uid 지시문](xuid-directive.md)의 별칭을 지정 하는 클래스의 CLR 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-210">Indicates the CLR property of a class that aliases the [x:Uid Directive](xuid-directive.md).</span></span>

### <a name="usableduringinitializationattribute"></a><span data-ttu-id="f118b-211">UsableDuringInitializationAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-211">UsableDuringInitializationAttribute</span></span>

<span data-ttu-id="f118b-212">**참조 설명서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-212">**Reference Documentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span></span>

<span data-ttu-id="f118b-213">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-213">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-214">**인수:** 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-214">**Arguments:** A Boolean.</span></span> <span data-ttu-id="f118b-215">특성의 용도에 사용 되는 경우 값을로 설정 해야 합니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="f118b-215">If used for the attribute's intended purpose, the value should be set to `true`.</span></span>

<span data-ttu-id="f118b-216">XAML 개체 그래프를 만드는 동안 형식이 하향식으로 빌드 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-216">Indicates whether the type is built top-down during XAML object graph creation.</span></span> <span data-ttu-id="f118b-217">이는 프로그래밍 모델의 정의와 밀접 하 게 관련 된 고급 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-217">This is an advanced concept, which is probably closely related to the definition of your programming model.</span></span> <span data-ttu-id="f118b-218">자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-218">For more information, see <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.</span></span>

### <a name="valueserializerattribute"></a><span data-ttu-id="f118b-219">ValueSerializerAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-219">ValueSerializerAttribute</span></span>

<span data-ttu-id="f118b-220">**참조 설명서:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-220">**Reference Documentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span></span>

<span data-ttu-id="f118b-221">**적용 대상:** 클래스, 속성, 메서드 (유일 하 게 XAML 유효한 메서드 대/소문자는 연결 `get` 가능한 멤버를 지 원하는 접근자).</span><span class="sxs-lookup"><span data-stu-id="f118b-221">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="f118b-222">**인수:** <xref:System.Type> 특성을 사용 하는 형식의 모든 속성 또는 특성을 사용 하는 특정 속성을 serialize 할 때 사용할 값 serializer 지원 클래스를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-222">**Arguments:** A <xref:System.Type> that specifies the value serializer support class to use when serializing all properties of the attributed type, or the specific attributed property.</span></span>

<span data-ttu-id="f118b-223"><xref:System.Windows.Markup.ValueSerializer> 보다 많은 상태와 컨텍스트가 필요한 값 serialization 클래스를 지정 합니다 <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="f118b-223"><xref:System.Windows.Markup.ValueSerializer> specifies a value serialization class that requires more state and context than a <xref:System.ComponentModel.TypeConverter> does.</span></span> <span data-ttu-id="f118b-224"><xref:System.Windows.Markup.ValueSerializer> 연결 가능한 <xref:System.Windows.Markup.ValueSerializerAttribute> `get` 멤버에 대 한 정적 접근자 메서드에 특성을 적용 하 여 연결할 수 있는 멤버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-224"><xref:System.Windows.Markup.ValueSerializer> can be associated with an attachable member by applying the <xref:System.Windows.Markup.ValueSerializerAttribute> attribute on the static `get` accessor method for the attachable member.</span></span> <span data-ttu-id="f118b-225">값 serialization은 열거형, 인터페이스 및 구조체에도 적용 되지만 대리자에 대해서는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-225">Value serialization is also applicable for enumerations, interfaces, and structures, but not for delegates.</span></span>

### <a name="whitespacesignificantcollectionattribute"></a><span data-ttu-id="f118b-226">WhitespaceSignificantCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-226">WhitespaceSignificantCollectionAttribute</span></span>

<span data-ttu-id="f118b-227">**참조 설명서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-227">**Reference Documentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span></span>

<span data-ttu-id="f118b-228">**적용 대상:** 클래스, 혼합 된 콘텐츠를 호스팅할 것으로 예상 되는 컬렉션 형식, 즉, 개체 요소 주위의 공백이 UI 표현에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-228">**Applies to:** Class, specifically collection types that are expected to host mixed content, where white space around object elements might be significant for UI representation.</span></span>

<span data-ttu-id="f118b-229">**인수:** 없음을.</span><span class="sxs-lookup"><span data-stu-id="f118b-229">**Arguments:** None.</span></span>

<span data-ttu-id="f118b-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 컬렉션 형식이 XAML 프로세서에 의해 공백으로 처리 되어야 함을 나타냅니다 .이는 컬렉션 내 XAML 노드 스트림의 값 노드 생성에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicates that a collection type should be processed as white-space significant by a XAML processor, which influences the construction of the XAML node stream's value nodes within the collection.</span></span> <span data-ttu-id="f118b-231">자세한 내용은 [XAML의 공백 처리](white-space-processing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-231">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="xamldeferloadattribute"></a><span data-ttu-id="f118b-232">XamlDeferLoadAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-232">XamlDeferLoadAttribute</span></span>

<span data-ttu-id="f118b-233">**참조 설명서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-233">**Reference Documentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span></span>

<span data-ttu-id="f118b-234">**적용 대상:** 클래스, 속성</span><span class="sxs-lookup"><span data-stu-id="f118b-234">**Applies to:** Class, property.</span></span>

<span data-ttu-id="f118b-235">**인수:** 에서는 두 가지 특성 형식 형식 (문자열 또는 형식)을 지원 <xref:System.Type> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-235">**Arguments:** Supports two attribution forms types as strings, or types as <xref:System.Type>.</span></span> <span data-ttu-id="f118b-236"><xref:System.Windows.Markup.XamlDeferLoadAttribute>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f118b-236">See <xref:System.Windows.Markup.XamlDeferLoadAttribute>.</span></span>

<span data-ttu-id="f118b-237">클래스 또는 속성에 XAML에 대한 지연된 로드 사용(예: 템플릿 동작)이 있음을 나타내고 지연 동작 및 해당 대상/콘텐츠 형식을 사용하도록 설정하는 클래스를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-237">Indicates that a class or property has a deferred load usage for XAML (such as a template behavior), and reports the class that enables the deferring behavior and its destination/content type.</span></span>

### <a name="xamlsetmarkupextensionattribute"></a><span data-ttu-id="f118b-238">System.windows.markup.xamlsetmarkupextensionattribute</span><span class="sxs-lookup"><span data-stu-id="f118b-238">XamlSetMarkupExtensionAttribute</span></span>

<span data-ttu-id="f118b-239">**참조 설명서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-239">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span></span>

<span data-ttu-id="f118b-240">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-240">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-241">**인수:** 콜백의 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-241">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="f118b-242">클래스에서 태그 확장을 사용 하 여 하나 이상의 해당 속성에 대 한 값을 제공 하 고, XAML 작성기가 클래스의 모든 속성에 대해 태그 확장 설정 작업을 수행 하기 전에 호출 해야 하는 처리기를 참조할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-242">Indicates that a class can use a markup extension to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a markup extension set operation on any property of the class.</span></span>

### <a name="xamlsettypeconverterattribute"></a><span data-ttu-id="f118b-243">XamlSetTypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-243">XamlSetTypeConverterAttribute</span></span>

<span data-ttu-id="f118b-244">**참조 설명서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-244">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span></span>

<span data-ttu-id="f118b-245">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-245">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-246">**인수:** 콜백의 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-246">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="f118b-247">클래스에서 형식 변환기를 사용 하 여 하나 이상의 해당 속성에 대 한 값을 제공 하 고, 클래스의 모든 속성에 대해 형식 변환기 설정 작업을 수행 하기 전에 XAML 작성기에서 호출 해야 하는 처리기를 참조할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-247">Indicates that a class can use a type converter to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a type converter set operation on any property of the class.</span></span>

### <a name="xmllangpropertyattribute"></a><span data-ttu-id="f118b-248">XmlLangPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-248">XmlLangPropertyAttribute</span></span>

<span data-ttu-id="f118b-249">**참조 설명서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-249">**Reference Documentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span></span>

<span data-ttu-id="f118b-250">**적용 대상:** 클래스</span><span class="sxs-lookup"><span data-stu-id="f118b-250">**Applies to:** Class</span></span>

<span data-ttu-id="f118b-251">**인수:** 특성 사용 형식에 대 한 별칭으로 지정할 속성의 이름을 지정 하는 문자열입니다 `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="f118b-251">**Arguments:** A string that specifies the name of the property to alias to `xml:lang` on the attributed type.</span></span>

<span data-ttu-id="f118b-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> XML 지시문에 매핑되는 특성 사용 형식의 속성을 보고 `lang` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> reports a property of the attributed type that maps to the XML `lang` directive.</span></span> <span data-ttu-id="f118b-253">속성은 형식이 아니어도 <xref:System.String> 되지만 문자열에서 할당할 수 있어야 합니다. 형식 변환기를 속성의 형식 또는 특정 속성과 연결 하 여 할당을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-253">The property is not necessarily of type <xref:System.String> but must be assignable from a string (assignment could be accomplished by associating a type converter with the property's type or with the specific property).</span></span> <span data-ttu-id="f118b-254">속성은 읽기/쓰기가 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-254">The property must be read/write.</span></span>

<span data-ttu-id="f118b-255">매핑의 시나리오는 `xml:lang` 런타임 개체 모델이 XMLDOM을 사용 하 여 특별히 처리 하지 않고도 XML 지정 언어 정보에 액세스할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-255">The scenario for mapping `xml:lang` is so that a runtime object model has access to XML-specified language information without specifically processing with an XMLDOM.</span></span>

<span data-ttu-id="f118b-256">정의는 정의 형식에 할당할 수 있는 모든 파생 형식에 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-256">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="f118b-257">특정 파생 형식에를 적용 하 여 특정 파생 형식에 대 한 정의를 재정의할 수 있습니다 <xref:System.Windows.Markup.XmlLangPropertyAttribute> . 단,이는 드문 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-257">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> on the specific derived type, although that is an uncommon scenario.</span></span>

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a><span data-ttu-id="f118b-258">어셈블리 수준에서 XAML 관련 CLR 특성</span><span class="sxs-lookup"><span data-stu-id="f118b-258">XAML-Related CLR Attributes at the Assembly Level</span></span>

<span data-ttu-id="f118b-259">다음 섹션에서는 형식 또는 멤버 정의에 적용 되지 않고 어셈블리에 적용 되는 XAML 관련 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-259">The following sections describe the XAML-related attributes that are not applied to types or member definitions, but are instead applied to assemblies.</span></span> <span data-ttu-id="f118b-260">이러한 특성은 XAML에서 사용할 사용자 지정 형식을 포함 하는 라이브러리를 정의 하는 전반적인 목표와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-260">These attributes are pertinent to the overall goal of defining a library that contains custom types to use in XAML.</span></span> <span data-ttu-id="f118b-261">일부 특성은 XAML 노드 스트림에 직접 영향을 주지는 않지만 다른 소비자가 사용할 수 있도록 노드 스트림에서 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-261">Some of the attributes do not necessarily influence the XAML node stream directly, but are passed on in the node stream for other consumers to use.</span></span> <span data-ttu-id="f118b-262">정보의 소비자에는 XAML 네임 스페이스 정보 및 관련 접두사 정보가 필요한 디자인 환경 또는 serialization 프로세스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-262">Consumers for the information include design environments or serialization processes that need XAML namespace information and associated prefix information.</span></span> <span data-ttu-id="f118b-263">XAML 스키마 컨텍스트 (.NET XAML 서비스 기본값 포함)도이 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-263">A XAML schema context (including the .NET XAML Services default) also uses this information.</span></span>

### <a name="xmlnscompatiblewithattribute"></a><span data-ttu-id="f118b-264">XmlnsCompatibleWithAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-264">XmlnsCompatibleWithAttribute</span></span>

<span data-ttu-id="f118b-265">**참조 설명서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-265">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span></span>

<span data-ttu-id="f118b-266">**인수:**</span><span class="sxs-lookup"><span data-stu-id="f118b-266">**Arguments:**</span></span>

- <span data-ttu-id="f118b-267">포함에 대 한 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-267">A string that specifies the identifier of the XAML namespace to subsume.</span></span>

- <span data-ttu-id="f118b-268">이전 인수에서 XAML 네임 스페이스를 포함 수 있는 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-268">A string that specifies the identifier of the XAML namespace that can subsume the XAML namespace from the previous argument.</span></span>

  <span data-ttu-id="f118b-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> 다른 XAML 네임 스페이스에서 XAML 네임 스페이스를 스페이스가 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> specifies that a XAML namespace can be subsumed by another XAML namespace.</span></span> <span data-ttu-id="f118b-270">일반적으로 포함하는 XAML 네임스페이스는 미리 정의된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-270">Typically, the subsuming XAML namespace is indicated in a previously defined <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span> <span data-ttu-id="f118b-271">이 기술은 라이브러리의 XAML 어휘 버전을 관리 하 고 이전 버전의 어휘에 대해 이전에 정의 된 태그와 호환 되도록 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-271">This technique can be used for versioning a XAML vocabulary in a library and to make it compatible with previously defined markup against the earlier versioned vocabulary.</span></span>

### <a name="xmlnsdefinitionattribute"></a><span data-ttu-id="f118b-272">매핑하기</span><span class="sxs-lookup"><span data-stu-id="f118b-272">XmlnsDefinitionAttribute</span></span>

<span data-ttu-id="f118b-273">**참조 설명서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-273">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span></span>

<span data-ttu-id="f118b-274">**인수:**</span><span class="sxs-lookup"><span data-stu-id="f118b-274">**Arguments:**</span></span>

- <span data-ttu-id="f118b-275">정의할 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-275">A string that specifies the identifier of the XAML namespace to define.</span></span>

- <span data-ttu-id="f118b-276">CLR 네임 스페이스의 이름을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-276">A string that names a CLR namespace.</span></span> <span data-ttu-id="f118b-277">CLR 네임 스페이스는 어셈블리에서 public 형식을 정의 해야 하며 CLR 네임 스페이스 형식 중 하나 이상이 XAML 사용을 위한 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-277">The CLR namespace should define public types in your assembly, and at least one of the CLR namespace types should be intended for XAML usage.</span></span>

  <span data-ttu-id="f118b-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> xaml 네임 스페이스와 CLR 네임 스페이스 사이에서 어셈블리 별로 매핑을 지정 합니다 .이는 XAML 개체 작성기 또는 XAML 스키마 컨텍스트에서 형식 확인에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a mapping on a per-assembly basis between a XAML namespace and a CLR namespace, which is then used for type resolution by a XAML object writer or XAML schema context.</span></span>

  <span data-ttu-id="f118b-279">하나 이상의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-279">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="f118b-280">이 작업은 다음과 같은 이유를 조합 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-280">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="f118b-281">라이브러리 디자인에는 런타임 API 액세스의 논리적 구성에 대 한 여러 CLR 네임 스페이스가 포함 되어 있습니다. 그러나 동일한 XAML 네임 스페이스를 참조 하 여 해당 네임 스페이스의 모든 형식을 XAML에서 사용할 수 있도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-281">The library design contains multiple CLR namespaces for logical organization of run-time API access; however, you want all types in those namespaces to be XAML-usable by referencing the same XAML namespace.</span></span> <span data-ttu-id="f118b-282">이 경우 값 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 은 같지만 값은 다른 여러 특성을 적용 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-282">In this case, you apply several <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributes using the same <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value but different <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> values.</span></span> <span data-ttu-id="f118b-283">이는 프레임 워크 또는 응용 프로그램이 일반적으로 사용 되는 기본 XAML 네임 스페이스를 사용 하는 XAML 네임 스페이스에 대 한 매핑을 정의 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-283">This is especially useful if you are defining mappings for the XAML namespace that your framework or application intends to be the default XAML namespace in common usage.</span></span>

- <span data-ttu-id="f118b-284">라이브러리 디자인에는 여러 CLR 네임 스페이스가 포함 되어 있으며, 이러한 CLR 네임 스페이스의 형식 사용 사이에 XAML 네임 스페이스를 명확 하 게 구분 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-284">The library design contains multiple CLR namespaces, and you want a deliberate XAML namespace separation between the usages of types in those CLR namespaces.</span></span>

- <span data-ttu-id="f118b-285">어셈블리에 CLR 네임 스페이스를 정의 하 고 둘 이상의 XAML 네임 스페이스를 통해 해당 네임 스페이스에 액세스할 수 있도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-285">You define a CLR namespace in the assembly, and you want it to be accessible through more than one XAML namespace.</span></span> <span data-ttu-id="f118b-286">이 시나리오는 동일한 코드 베이스를 사용 하 여 여러 어휘를 지원할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-286">This scenario occurs when you are supporting multiple vocabularies with the same codebase.</span></span>

- <span data-ttu-id="f118b-287">하나 이상의 CLR 네임 스페이스에서 XAML 언어 지원을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-287">You define XAML language support in one or more CLR namespaces.</span></span> <span data-ttu-id="f118b-288">이 경우 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값은 이어야 합니다 `http://schemas.microsoft.com/winfx/2006/xaml` .</span><span class="sxs-lookup"><span data-stu-id="f118b-288">In this case, the <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value should be `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span>

### <a name="xmlnsprefixattribute"></a><span data-ttu-id="f118b-289">XmlnsPrefixAttribute</span><span class="sxs-lookup"><span data-stu-id="f118b-289">XmlnsPrefixAttribute</span></span>

<span data-ttu-id="f118b-290">**참조 설명서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span><span class="sxs-lookup"><span data-stu-id="f118b-290">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span></span>

<span data-ttu-id="f118b-291">**인수:**</span><span class="sxs-lookup"><span data-stu-id="f118b-291">**Arguments:**</span></span>

- <span data-ttu-id="f118b-292">XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-292">A string that specifies the identifier of a XAML namespace.</span></span>

- <span data-ttu-id="f118b-293">권장 접두사를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-293">A string that specifies a recommended prefix.</span></span>

  <span data-ttu-id="f118b-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 네임 스페이스에 사용할 권장 접두사를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a recommended prefix to use for a XAML namespace.</span></span> <span data-ttu-id="f118b-295">접두사는 .NET XAML 서비스에 의해 serialize 되는 XAML 파일의 요소 및 특성을 쓰거나 xaml <xref:System.Xaml.XamlXmlWriter> 구현 라이브러리가 xaml 편집 기능이 있는 디자인 환경과 상호 작용 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-295">The prefix is useful when writing elements and attributes in a XAML file that is serialized by .NET XAML Services <xref:System.Xaml.XamlXmlWriter>, or when a XAML-implementing library interacts with a design environment that has XAML editing features.</span></span>

  <span data-ttu-id="f118b-296">하나 이상의 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-296">More than one <xref:System.Windows.Markup.XmlnsPrefixAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="f118b-297">이 작업은 다음과 같은 이유를 조합 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-297">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="f118b-298">어셈블리에서 둘 이상의 XAML 네임 스페이스에 대 한 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-298">Your assembly defines types for more than one XAML namespace.</span></span> <span data-ttu-id="f118b-299">이 경우 각 XAML 네임 스페이스에 대해 서로 다른 접두사 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-299">In this case, define different prefix values for each XAML namespace.</span></span>

- <span data-ttu-id="f118b-300">여러 어휘를 지원 하 고 각 어휘 및 XAML 네임 스페이스에 대해 서로 다른 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-300">You are supporting multiple vocabularies, and you use different prefixes for each vocabulary and XAML namespace.</span></span>

- <span data-ttu-id="f118b-301">어셈블리에서 XAML 언어 지원을 정의 하 고 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 에 대 한를 포함 `http://schemas.microsoft.com/winfx/2006/xaml` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-301">You define XAML language support in the assembly and have a <xref:System.Windows.Markup.XmlnsDefinitionAttribute> for `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span> <span data-ttu-id="f118b-302">이 경우 일반적으로 접두사의 수준을 올립니다 `x` .</span><span class="sxs-lookup"><span data-stu-id="f118b-302">In this case, you typically should promote the prefix `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="f118b-303">또한 .NET XAML 서비스는 XAML 관련 특성을 정의 <xref:System.Windows.Markup.RootNamespaceAttribute> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-303">.NET XAML Services also defines the XAML-related attribute <xref:System.Windows.Markup.RootNamespaceAttribute>.</span></span> <span data-ttu-id="f118b-304">이 특성은 프로젝트 시스템 지원에 대 한 어셈블리 수준 특성이 며 XAML 사용자 지정 형식과는 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f118b-304">This attribute is an assembly-level attribute for project system support, and it is not relevant for XAML custom types.</span></span>

## <a name="see-also"></a><span data-ttu-id="f118b-305">참조</span><span class="sxs-lookup"><span data-stu-id="f118b-305">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="f118b-306">.NET XAML 서비스에서 사용할 사용자 지정 형식 정의</span><span class="sxs-lookup"><span data-stu-id="f118b-306">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
