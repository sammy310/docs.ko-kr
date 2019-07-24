---
title: PropertyPath XAML 구문
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: deebdb690a6ba831730701de2608089af2d6bdfd
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401667"
---
# <a name="propertypath-xaml-syntax"></a><span data-ttu-id="55097-102">PropertyPath XAML 구문</span><span class="sxs-lookup"><span data-stu-id="55097-102">PropertyPath XAML Syntax</span></span>

<span data-ttu-id="55097-103">개체 <xref:System.Windows.PropertyPath> 는 <xref:System.Windows.PropertyPath> 형식을 값으로 사용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 하는 다양 한 속성을 설정 하기 위한 복잡 한 인라인 구문을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-103">The <xref:System.Windows.PropertyPath> object supports a complex inline [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] syntax for setting various properties that take the <xref:System.Windows.PropertyPath> type as their value.</span></span> <span data-ttu-id="55097-104">이 항목에서는 바인딩 <xref:System.Windows.PropertyPath> 및 애니메이션 구문에 적용 되는 구문에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-104">This topic documents the <xref:System.Windows.PropertyPath> syntax as applied to binding and animation syntaxes.</span></span>

<a name="where"></a>

## <a name="where-propertypath-is-used"></a><span data-ttu-id="55097-105">PropertyPath를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="55097-105">Where PropertyPath Is Used</span></span>

<span data-ttu-id="55097-106"><xref:System.Windows.PropertyPath>는 여러 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능에서 사용 되는 공통 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-106"><xref:System.Windows.PropertyPath> is a common object that is used in several [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] features.</span></span> <span data-ttu-id="55097-107">일반적 <xref:System.Windows.PropertyPath> 으로 속성 경로 정보를 전달 하는 데에도 불구 하 고 <xref:System.Windows.PropertyPath> 가 형식으로 사용 되는 각 기능 영역에 대 한 사용량은 다양 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-107">Despite using the common <xref:System.Windows.PropertyPath> to convey property path information, the usages for each feature area where <xref:System.Windows.PropertyPath> is used as a type vary.</span></span> <span data-ttu-id="55097-108">따라서 구문은 기능별로 설명하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-108">Therefore, it is more practical to document the syntaxes on a per-feature basis.</span></span>

<span data-ttu-id="55097-109">주로는를 <xref:System.Windows.PropertyPath> 사용 하 여 개체 데이터 소스의 속성을 순회 하 고 대상 애니메이션의 대상 경로를 설명 하는 개체 모델 경로를 설명 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55097-109">Primarily, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uses <xref:System.Windows.PropertyPath> to describe object-model paths for traversing the properties of an object data source, and to describe the target path for targeted animations.</span></span>

<span data-ttu-id="55097-110">과 같은 일부 스타일 및 템플릿 속성 <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> 은 표면적와 <xref:System.Windows.PropertyPath>비슷한 정규화 된 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-110">Some style and template properties such as <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> take a qualified property name that superficially resembles a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="55097-111">그러나이는 <xref:System.Windows.PropertyPath>true가 아니라 정규화 된 *소유자입니다.* WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서의 <xref:System.Windows.DependencyProperty>형식 변환기와 함께 사용 하도록 설정 된 속성 문자열 형식 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-111">But this is not a true <xref:System.Windows.PropertyPath>; instead it is a qualified *owner.property* string format usage that is enabled by the WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor in combination with the type converter for <xref:System.Windows.DependencyProperty>.</span></span>

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a><span data-ttu-id="55097-112">데이터 바인딩의 개체에 대한 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="55097-112">PropertyPath for Objects in Data Binding</span></span>

<span data-ttu-id="55097-113">데이터 바인딩은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능으로 이를 통해 종속성 속성의 대상 값에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-113">Data binding is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] feature whereby you can bind to the target value of any dependency property.</span></span> <span data-ttu-id="55097-114">하지만 해당 데이터 바인딩의 소스는 종속성 속성이어야 하며 적용 가능한 데이터 공급자가 인식하는 모든 속성 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-114">However, the source of such a data binding need not be a dependency property; it can be any property type that is recognized by the applicable data provider.</span></span> <span data-ttu-id="55097-115">속성 경로는 CLR (공용 언어 <xref:System.Windows.Data.ObjectDataProvider>런타임) 개체 및 해당 속성에서 바인딩 소스를 가져오는 데 사용 되는에 특히 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-115">Property paths are particularly used for the <xref:System.Windows.Data.ObjectDataProvider>, which is used for obtaining binding sources from common language runtime (CLR) objects and their properties.</span></span>

<span data-ttu-id="55097-116">에 대 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 한 데이터 바인딩은에서을 사용 <xref:System.Windows.PropertyPath> <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding>하지 않으므로를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-116">Note that data binding to [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] does not use <xref:System.Windows.PropertyPath>, because it does not use <xref:System.Windows.Data.Binding.Path%2A> in the <xref:System.Windows.Data.Binding>.</span></span> <span data-ttu-id="55097-117">대신를 사용 <xref:System.Windows.Data.Binding.XPath%2A> 하 여 데이터의에 [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] 올바른 XPath 구문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-117">Instead, you use <xref:System.Windows.Data.Binding.XPath%2A> and specify valid XPath syntax into the [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] of the data.</span></span> <span data-ttu-id="55097-118"><xref:System.Windows.Data.Binding.XPath%2A>는 문자열로도 지정 되어 있지만 여기서는 설명 하지 않습니다. [XMLDataProvider 및 XPath 쿼리를 사용 하 여 XML 데이터에 바인딩을](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55097-118"><xref:System.Windows.Data.Binding.XPath%2A> is also specified as a string, but is not documented here; see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span>

<span data-ttu-id="55097-119">데이터 바인딩의 속성 경로를 이해하는 열쇠는 개별 속성 값에 대한 바인딩을 대상으로 지정할 수 있거나 목록이나 컬렉션을 사용하는 대상 속성에 바인딩할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-119">A key to understanding property paths in data binding is that you can target the binding to an individual property value, or you can instead bind to target properties that take lists or collections.</span></span> <span data-ttu-id="55097-120">컬렉션을 바인딩하는 경우 컬렉션에 있는 데이터 항목 <xref:System.Windows.Controls.ListBox> 의 수에 따라 확장 되는 인스턴스를 바인딩하는 경우 속성 경로는 개별 컬렉션 항목이 아니라 컬렉션 개체를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-120">If you are binding collections, for instance binding a <xref:System.Windows.Controls.ListBox> that will expand depending on how many data items are in the collection, then your property path should reference the collection object, not individual collection items.</span></span> <span data-ttu-id="55097-121">데이터 바인딩 엔진은 데이터 원본으로 사용 되는 컬렉션을 바인딩 대상의 형식으로 자동으로 일치 시킵니다. 그러면에 <xref:System.Windows.Controls.ListBox> 항목 배열을 채우는 것과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-121">The data binding engine will match the collection used as the data source to the type of the binding target automatically, resulting in behavior such as populating a <xref:System.Windows.Controls.ListBox> with an items array.</span></span>

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a><span data-ttu-id="55097-122">데이터 컨텍스트로서 직접 실행 개체에 대한 단일 속성</span><span class="sxs-lookup"><span data-stu-id="55097-122">Single Property on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="propertyName" .../>
```

<span data-ttu-id="55097-123">*propertyName* 은 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Data.Binding.Path%2A> 사용에 대 한 현재에 있는 속성의 이름으로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-123">*propertyName* must resolve to be the name of a property that is in the current <xref:System.Windows.FrameworkElement.DataContext%2A> for a <xref:System.Windows.Data.Binding.Path%2A> usage.</span></span> <span data-ttu-id="55097-124">바인딩이 소스를 업데이트하면 해당 속성은 읽기/쓰기여야 하고 소스 개체는 변경 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-124">If your binding updates the source, that property must be read/write and the source object must be mutable.</span></span>

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a><span data-ttu-id="55097-125">데이터 컨텍스트로서 직접 실행 개체에 대한 단일 인덱서</span><span class="sxs-lookup"><span data-stu-id="55097-125">Single Indexer on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="[key]" .../>
```

<span data-ttu-id="55097-126">`key`는 사전 및 해시 테이블에 대한 형식화된 인덱스이거나 배열의 정수 인덱스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-126">`key` must be either the typed index to a dictionary or hash table, or the integer index of an array.</span></span> <span data-ttu-id="55097-127">또한 키 값은 키 값이 적용되는 속성에 직접 바인딩할 수 있는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-127">Also, the value of the key must be a type that is directly bindable to the property where it is applied.</span></span> <span data-ttu-id="55097-128">예를 들어 문자열 키 및 문자열 값을 포함 하는 해시 테이블을이 방법으로 사용 하 여의 <xref:System.Windows.Controls.TextBox>텍스트에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-128">For instance, a hash table that contains string keys and string values can be used this way to bind to Text for a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="55097-129">또는 키가 컬렉션이나 하위 인덱스를 가리키는 경우 이 구문을 사용하여 대상 컬렉션 속성에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-129">Or, if the key points to a collection or subindex, you could use this syntax to bind to a target collection property.</span></span> <span data-ttu-id="55097-130">이외의 경우에는 `<Binding Path="[key].propertyName" .../>`과 같은 구문을 통해 특정 속성을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-130">Otherwise, you need to reference a specific property, through a syntax such as `<Binding Path="[key].propertyName" .../>`.</span></span>

<span data-ttu-id="55097-131">필요한 경우 인덱스의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-131">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="55097-132">인덱싱된 속성 경로의 이러한 측면에 대 한 자세한 내용은을 참조 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>하십시오.</span><span class="sxs-lookup"><span data-stu-id="55097-132">For details on this aspect of an indexed property path, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a><span data-ttu-id="55097-133">다중 속성(간접 속성 대상 지정)</span><span class="sxs-lookup"><span data-stu-id="55097-133">Multiple Property (Indirect Property Targeting)</span></span>

```xml
<Binding Path="propertyName.propertyName2" .../>
```

<span data-ttu-id="55097-134">`propertyName`는 현재 <xref:System.Windows.FrameworkElement.DataContext%2A>인 속성의 이름으로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-134">`propertyName` must resolve to be the name of a property that is the current <xref:System.Windows.FrameworkElement.DataContext%2A>.</span></span> <span data-ttu-id="55097-135">경로 속성 `propertyName` 및 `propertyName2`는 관계에 있는 속성일 수 있습니다. 여기서 `propertyName2`는 `propertyName` 값인 형식에 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-135">The path properties `propertyName` and `propertyName2` can be any properties that exist in a relationship, where `propertyName2` is a property that exists on the type that is the value of `propertyName`.</span></span>

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a><span data-ttu-id="55097-136">연결된 또는 정규화된 형식의 단일 속성</span><span class="sxs-lookup"><span data-stu-id="55097-136">Single Property, Attached or Otherwise Type-Qualified</span></span>

```xml
<object property="(ownerType.propertyName)" .../>
```

<span data-ttu-id="55097-137">괄호는의 <xref:System.Windows.PropertyPath> 이 속성이 부분 정규화를 사용 하 여 생성 되어야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-137">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="55097-138">XML 네임스페이스를 사용하여 적절한 매핑이 있는 형식을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-138">It can use an XML namespace to find the type with an appropriate mapping.</span></span> <span data-ttu-id="55097-139">는 `ownerType` 각 어셈블리의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 선언을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 통해 프로세서가 액세스할 수 있는 형식을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-139">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="55097-140">대부분 애플리케이션에서는 기본 XML 네임스페이스가 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 매핑되므로 접두사는 대개 사용자 지정 형식 또는 해당 네임스페이스 외부의 형식에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-140">Most applications have the default XML namespace mapped to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span>  <span data-ttu-id="55097-141">`propertyName`은 `ownerType`에 있는 속성의 이름으로 확인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-141">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="55097-142">일반적으로 이 구문은 다음 경우 중 하나에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-142">This syntax is generally used for one of the following cases:</span></span>

- <span data-ttu-id="55097-143">경로는 지정된 대상 형식이 없는 스타일 또는 템플릿인 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-143">The path is specified in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that is in a style or template that does not have a specified Target Type.</span></span> <span data-ttu-id="55097-144">스타일이 아니고 템플릿이 아닌 경우에 속성은 형식이 아닌 인스턴스에 있으므로 일반적으로 이를 제외한 다른 경우에는 정규화된 사용이 적절하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-144">A qualified usage is generally not valid for cases other than this, because in non-style, non-template cases, the property exists on an instance, not a type.</span></span>

- <span data-ttu-id="55097-145">속성은 연결된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-145">The property is an attached property.</span></span>

- <span data-ttu-id="55097-146">정적 속성이 바인딩 중입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-146">You are binding to a static property.</span></span>

<span data-ttu-id="55097-147">스토리 보드 대상으로 사용 하는 경우로 `propertyName` 지정 된 속성은 이어야 합니다. <xref:System.Windows.DependencyProperty></span><span class="sxs-lookup"><span data-stu-id="55097-147">For use as storyboard target, the property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span>

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a><span data-ttu-id="55097-148">소스 순회(컬렉션 계층 구조에 바인딩)</span><span class="sxs-lookup"><span data-stu-id="55097-148">Source Traversal (Binding to Hierarchies of Collections)</span></span>

```xml
<object Path="propertyName/propertyNameX" .../>
```

<span data-ttu-id="55097-149">이 구문의 /는 계층적 데이터 소스 개체 내에서 탐색하는 데 사용되고 연속 / 문자가 있는 계층 구조에 대한 여러 단계는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-149">The / in this syntax is used to navigate within a hierarchical data source object, and multiple steps into the hierarchy with successive / characters are supported.</span></span> <span data-ttu-id="55097-150">소스 순회는 데이터를 뷰의 UI와 동기화할 때 결정되는 현재 레코드 포인터 위치를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-150">The source traversal accounts for the current record pointer position, which is determined by synchronizing the data with the UI of its view.</span></span> <span data-ttu-id="55097-151">계층적 데이터 소스 개체를 사용한 바인딩 및 데이터 바인딩의 현재 레코드 포인터 개념에 대한 자세한 내용은 [계층적 데이터에 마스터-세부 패턴 사용](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) 또는 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55097-151">For details on binding with hierarchical data source objects, and the concept of current record pointer in data binding, see [Use the Master-Detail Pattern with Hierarchical Data](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) or [Data Binding Overview](../data/data-binding-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="55097-152">표면적으로 이 구문은 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-152">Superficially, this syntax resembles [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)].</span></span> <span data-ttu-id="55097-153">데이터 원본 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding.XPath%2A> 에 바인딩하기 위한 true 식은 값으로 사용 되지 않으며, 대신 함께 사용할 수 없는 속성에 사용 해야 합니다. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55097-153">A true [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] expression for binding to an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data source is not used as a <xref:System.Windows.Data.Binding.Path%2A> value and should instead be used for the mutually exclusive <xref:System.Windows.Data.Binding.XPath%2A> property.</span></span>

### <a name="collection-views"></a><span data-ttu-id="55097-154">컬렉션 뷰</span><span class="sxs-lookup"><span data-stu-id="55097-154">Collection Views</span></span>

<span data-ttu-id="55097-155">명명된 컬렉션 뷰를 참조하려면 해시 문자(`#`)를 컬렉션 뷰 이름에 접두사로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-155">To reference a named collection view, prefix the collection view name with the hash character (`#`).</span></span>

### <a name="current-record-pointer"></a><span data-ttu-id="55097-156">현재 레코드 포인터</span><span class="sxs-lookup"><span data-stu-id="55097-156">Current Record Pointer</span></span>

<span data-ttu-id="55097-157">컬렉션 뷰 또는 마스터 세부 데이터 바인딩 시나리오에 대한 현재 레코드 포인터를 참조하려면 경로 문자열을 슬래시(`/`)로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-157">To reference the current record pointer for a collection view or master detail data binding scenario, start the path string with a forward slash (`/`).</span></span> <span data-ttu-id="55097-158">슬래시를 통과하는 모든 경로는 현재 레코드 포인터부터 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-158">Any path past the forward slash is traversed starting from the current record pointer.</span></span>

### <a name="multiple-indexers"></a><span data-ttu-id="55097-159">여러 인덱서</span><span class="sxs-lookup"><span data-stu-id="55097-159">Multiple Indexers</span></span>

```xaml
<object Path="[index1,index2...]" .../>
```

<span data-ttu-id="55097-160">로 구분하거나 여러</span><span class="sxs-lookup"><span data-stu-id="55097-160">or</span></span>

```xaml
<object Path="propertyName[index,index2...]" .../>
```

<span data-ttu-id="55097-161">특정 개체가 여러 인덱서를 지원할 경우 이러한 인덱서는 배열 참조 구문처럼 순서대로 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-161">If a given object supports multiple indexers, those indexers can be specified in order, similar to an array referencing syntax.</span></span> <span data-ttu-id="55097-162">해당 개체는 현재 컨텍스트이거나 여러 인덱스 개체를 포함하는 속성의 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-162">The object in question can be either the current context or the value of a property that contains a multiple index object.</span></span>

<span data-ttu-id="55097-163">기본적으로 인덱서 값은 기본 개체의 특징을 사용해서 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-163">By default, the indexer values are typed by using the characteristics of the underlying object.</span></span> <span data-ttu-id="55097-164">필요한 경우 인덱스의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-164">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="55097-165">인덱서를 입력 하는 방법에 대 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>한 자세한 내용은을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55097-165">For details on typing the indexers, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a><span data-ttu-id="55097-166">구문 혼합</span><span class="sxs-lookup"><span data-stu-id="55097-166">Mixing Syntaxes</span></span>

<span data-ttu-id="55097-167">위에 표시되는 각 구문은 섞여 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-167">Each of the syntaxes shown above can be interspersed.</span></span> <span data-ttu-id="55097-168">예를 들어, 다음은 개체의 `ColorGrid` <xref:System.Windows.Media.SolidColorBrush> 픽셀 그리드 배열을 포함 하는 속성의 특정 x, y에서 색에 대 한 속성 경로를 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-168">For instance, the following is an example that creates a property path to the color at a particular x,y of a `ColorGrid` property that contains a pixel grid array of <xref:System.Windows.Media.SolidColorBrush> objects:</span></span>

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>
```

### <a name="escapes-for-property-path-strings"></a><span data-ttu-id="55097-169">속성 경로 문자열에 대한 이스케이프</span><span class="sxs-lookup"><span data-stu-id="55097-169">Escapes for Property Path Strings</span></span>

<span data-ttu-id="55097-170">특정 비즈니스 개체의 경우 제대로 구문 분석되려면 속성 경로 문자열에 이스케이프 시퀀스가 있어야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-170">For certain business objects, you might encounter a case where the property path string requires an escape sequence in order to parse correctly.</span></span> <span data-ttu-id="55097-171">이스케이프해야 하는 경우는 드뭅니다. 대부분의 이러한 문자에는 일반적으로 비즈니스 개체를 정의하는 데 사용되는 언어에 비슷한 명명 상호 작용 문제가 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-171">The need to escape should be rare, because many of these characters have similar naming-interaction issues in languages that would typically be used to define the business object.</span></span>

- <span data-ttu-id="55097-172">인덱서([ ]) 안의 캐럿 문자(^)는 다음 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-172">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>

- <span data-ttu-id="55097-173">XML 언어 정의와 관련된 특정 문자를 이스케이프(XML 엔터티 사용)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-173">You must escape (using XML entities) certain characters that are special to the XML language definition.</span></span> <span data-ttu-id="55097-174">"&" 문자를 이스케이프하려면 `&`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-174">Use `&` to escape the character "&".</span></span> <span data-ttu-id="55097-175">">" 끝 태그를 이스케이프하려면 `>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-175">Use `>` to escape the end tag ">".</span></span>

- <span data-ttu-id="55097-176">태그 확장을 처리하기 위해 WPF XAML 구문 분석기 동작과 관련된 특정 문자를 이스케이프해야 합니다(백슬래시 `\` 사용).</span><span class="sxs-lookup"><span data-stu-id="55097-176">You must escape (using backslash `\`) characters that are special to the WPF XAML parser behavior for processing a markup extension.</span></span>

  - <span data-ttu-id="55097-177">백슬래시(`\`)는 그 자체로 이스케이프 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-177">Backslash (`\`) is the escape character itself.</span></span>

  - <span data-ttu-id="55097-178">등호(`=`)는 속성 값에서 속성 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-178">The equal sign (`=`) separates property name from property value.</span></span>

  - <span data-ttu-id="55097-179">쉼표(`,`)는 속성을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-179">Comma (`,`) separates properties.</span></span>

  - <span data-ttu-id="55097-180">오른쪽 중괄호(`}`)는 태그 확장의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-180">The right curly brace (`}`) is the end of a markup extension.</span></span>

> [!NOTE]
> <span data-ttu-id="55097-181">기술적으로 이러한 이스케이프는 스토리보드 속성 경로에도 적용되지만 대개 기존 WPF 개체에 대한 개체 모델을 통과하므로 이스케이프가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-181">Technically, these escapes work for a storyboard property path also, but you are usually traversing object models for existing WPF objects, and escaping should be unnecessary.</span></span>

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a><span data-ttu-id="55097-182">애니메이션 대상에 대한 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="55097-182">PropertyPath for Animation Targets</span></span>

<span data-ttu-id="55097-183">애니메이션의 target 속성은 <xref:System.Windows.Freezable> 또는 기본 형식을 사용 하는 종속성 속성 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-183">The target property of an animation must be a dependency property that takes either a <xref:System.Windows.Freezable> or a primitive type.</span></span> <span data-ttu-id="55097-184">하지만 형식의 대상 속성 및 최종 애니메이션 효과가 적용된 속성은 서로 다른 개체에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-184">However, the targeted property on a type and the eventual animated property can exist on different objects.</span></span> <span data-ttu-id="55097-185">애니메이션에 대한 속성 경로는 속성 값에서 개체 속성 관계를 통과하는 방식으로 명명된 애니메이션 대상 개체의 속성과 의도한 대상 애니메이션 속성 간 연결을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-185">For animations, a property path is used to define the connection between the named animation target object's property and the intended target animation property, by traversing object-property relationships in the property values.</span></span>

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a><span data-ttu-id="55097-186">애니메이션에 대한 일반 개체 속성 고려 사항</span><span class="sxs-lookup"><span data-stu-id="55097-186">General Object-Property Considerations for Animations</span></span>

<span data-ttu-id="55097-187">일반적인 애니메이션 개념에 대한 자세한 내용은 [Storyboard 개요](../graphics-multimedia/storyboards-overview.md) 및 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55097-187">For more information on animation concepts in general, see [Storyboards Overview](../graphics-multimedia/storyboards-overview.md) and [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

<span data-ttu-id="55097-188">애니메이션 효과가 적용 되는 값 형식 또는 속성은 <xref:System.Windows.Freezable> 형식 이거나 기본 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-188">The value type or the property being animated must be either a <xref:System.Windows.Freezable> type or a primitive.</span></span> <span data-ttu-id="55097-189">경로를 시작 하는 속성은 지정 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 된 형식에 있는 종속성 속성의 이름으로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-189">The property that starts the path must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="55097-190">이미 <xref:System.Windows.Freezable> 고정 된에 애니메이션을 적용 하기 위한 복제를 지원 하기 위해에 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 지정 <xref:System.Windows.FrameworkElement> 된 개체는 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-190">In order to support cloning for animating a <xref:System.Windows.Freezable> that is already frozen, the object specified by <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> must be a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class.</span></span>

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a><span data-ttu-id="55097-191">대상 개체에 대한 단일 속성</span><span class="sxs-lookup"><span data-stu-id="55097-191">Single Property on the Target Object</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

<span data-ttu-id="55097-192">`propertyName`는 지정 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 된 형식에 있는 종속성 속성의 이름으로 확인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-192">`propertyName` must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a><span data-ttu-id="55097-193">간접 속성 대상 지정</span><span class="sxs-lookup"><span data-stu-id="55097-193">Indirect Property Targeting</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

<span data-ttu-id="55097-194">`propertyName`는 지정 <xref:System.Windows.Freezable> <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 된 형식에 있는 값 형식 또는 기본 형식인 속성 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-194">`propertyName` must be a property that is either a <xref:System.Windows.Freezable> value type or a primitive, which exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="55097-195">`propertyName2`는 `propertyName` 값인 개체에 있는 종속성 속성의 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-195">`propertyName2` must be the name of a dependency property that exists on the object that is the value of `propertyName`.</span></span> <span data-ttu-id="55097-196">즉, `propertyName2` 는 인 형식 `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>에 대 한 종속성 속성으로 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-196">In other words, `propertyName2` must exist as a dependency property on the type that is the `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.</span></span>

<span data-ttu-id="55097-197">적용된 스타일 및 템플릿 때문에 애니메이션의 간접 대상 지정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-197">Indirect targeting of animations is necessary because of applied styles and templates.</span></span> <span data-ttu-id="55097-198">애니메이션을 대상으로 하려면 대상 개체에가 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 필요 하며,이 이름은 [x:Name](../../xaml-services/x-name-directive.md) 또는 <xref:System.Windows.FrameworkElement.Name%2A>로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-198">In order to target an animation, you need a <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> on a target object, and that name is established by [x:Name](../../xaml-services/x-name-directive.md) or <xref:System.Windows.FrameworkElement.Name%2A>.</span></span> <span data-ttu-id="55097-199">템플릿 및 스타일 요소에 이름이 있을 수 있지만 해당 이름은 스타일 및 템플릿의 네임스페이스 내에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-199">Although template and style elements also can have names, those names are only valid within the namescope of the style and template.</span></span> <span data-ttu-id="55097-200">템플릿 및 스타일이 네임스페이스를 애플리케이션 태그와 공유한 경우 이름이 고유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-200">(If templates and styles did share namescopes with application markup, names couldn't be unique.</span></span> <span data-ttu-id="55097-201">스타일 및 템플릿은 문자 그대로 인스턴스 간에 공유되고 중복 이름을 영구화합니다. 따라서 애니메이션 효과를 줄 요소의 개별 속성이 스타일이나 템플릿을 기반으로 한 경우 스타일 템플릿을 기반으로 하지 않은 명명된 요소 인스턴스로 시작한 다음 애니메이션 효과를 줄 속성에 도착할 스타일 또는 템플릿 시각적 트리를 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-201">The styles and templates are literally shared between instances and would perpetuate duplicate names.) Thus, if the individual properties of an element that you might wish to animate came from a style or template, you need to start with a named element instance that is not from a style template, and then target into the style or template visual tree to arrive at the property you wish to animate.</span></span>

<span data-ttu-id="55097-202">예를 <xref:System.Windows.Controls.Panel.Background%2A> 들어 <xref:System.Windows.Controls.Panel> 의 속성은 테마 템플릿에서 가져온 전체 <xref:System.Windows.Media.Brush> (실제로 <xref:System.Windows.Media.SolidColorBrush>)입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-202">For instance, the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Panel> is a complete <xref:System.Windows.Media.Brush> (actually a <xref:System.Windows.Media.SolidColorBrush>) that came from a theme template.</span></span> <span data-ttu-id="55097-203"><xref:System.Windows.Media.Brush> 전체에 애니메이션 효과를 주려면 BrushAnimation (모든 <xref:System.Windows.Media.Brush> 형식에 대해 하나)가 필요 하 고 이러한 형식이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-203">To animate a <xref:System.Windows.Media.Brush> completely, there would need to be a BrushAnimation (probably one for every <xref:System.Windows.Media.Brush> type) and there is no such type.</span></span> <span data-ttu-id="55097-204">브러시에 애니메이션 효과를 주려면 특정 <xref:System.Windows.Media.Brush> 형식의 속성에 애니메이션 효과를 주는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-204">To animate a Brush, you instead animate properties of a particular <xref:System.Windows.Media.Brush> type.</span></span> <span data-ttu-id="55097-205">에서 <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Media.Animation.ColorAnimation> 로 이동하여이를적용해야합니다.<xref:System.Windows.Media.SolidColorBrush.Color%2A></span><span class="sxs-lookup"><span data-stu-id="55097-205">You need to get from <xref:System.Windows.Media.SolidColorBrush> to its <xref:System.Windows.Media.SolidColorBrush.Color%2A> to apply a <xref:System.Windows.Media.Animation.ColorAnimation> there.</span></span> <span data-ttu-id="55097-206">이 예제의 속성 경로는 `Background.Color`입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-206">The property path for this example would be `Background.Color`.</span></span>

<a name="attachedanim"></a>

### <a name="attached-properties"></a><span data-ttu-id="55097-207">연결된 속성</span><span class="sxs-lookup"><span data-stu-id="55097-207">Attached Properties</span></span>

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

<span data-ttu-id="55097-208">괄호는의 <xref:System.Windows.PropertyPath> 이 속성이 부분 정규화를 사용 하 여 생성 되어야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-208">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="55097-209">XML 네임스페이스를 사용하여 형식을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-209">It can use an XML namespace to find the type.</span></span> <span data-ttu-id="55097-210">는 `ownerType` 각 어셈블리의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 선언을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 통해 프로세서가 액세스할 수 있는 형식을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-210">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="55097-211">대부분 애플리케이션에서는 기본 XML 네임스페이스가 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 매핑되므로 접두사는 대개 사용자 지정 형식 또는 해당 네임스페이스 외부의 형식에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-211">Most applications have the default XML namespace mapped to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span> <span data-ttu-id="55097-212">`propertyName`은 `ownerType`에 있는 속성의 이름으로 확인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-212">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="55097-213">로 `propertyName` 지정 된 속성은 이어야 합니다 <xref:System.Windows.DependencyProperty>.</span><span class="sxs-lookup"><span data-stu-id="55097-213">The property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="55097-214">모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 속성은 종속성 속성으로 구현되므로 이 문제는 사용자 지정 연결된 속성에만 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-214">(All [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attached properties are implemented as dependency properties, so this issue is only of concern for custom attached properties.)</span></span>

<a name="indexanim"></a>

### <a name="indexers"></a><span data-ttu-id="55097-215">인덱서</span><span class="sxs-lookup"><span data-stu-id="55097-215">Indexers</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

<span data-ttu-id="55097-216">대부분의 종속성 속성 <xref:System.Windows.Freezable> 또는 형식은 인덱서를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-216">Most dependency properties or <xref:System.Windows.Freezable> types do not support an indexer.</span></span> <span data-ttu-id="55097-217">따라서 애니메이션 경로에서 인덱서는 명명된 대상에서 체인을 시작하는 속성과 최종 애니메이션 효과가 적용된 속성 사이의 중간 위치에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55097-217">Therefore, the only usage for an indexer in an animation path is at an intermediate position between the property that starts the chain on the named target and the eventual animated property.</span></span> <span data-ttu-id="55097-218">제공된 구문에서 인덱서는 `propertyName2`입니다.</span><span class="sxs-lookup"><span data-stu-id="55097-218">In the provided syntax, that is `propertyName2`.</span></span> <span data-ttu-id="55097-219">예를 들어와 같은 속성 경로 <xref:System.Windows.Media.TransformGroup> `RenderTransform.Children[1].Angle`에 중간 속성이와 같은 컬렉션인 경우 인덱서를 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-219">For instance, an indexer usage might be necessary if the intermediate property is a collection such as <xref:System.Windows.Media.TransformGroup>, in a property path such as `RenderTransform.Children[1].Angle`.</span></span>

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a><span data-ttu-id="55097-220">코드의 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="55097-220">PropertyPath in Code</span></span>

<span data-ttu-id="55097-221">를 <xref:System.Windows.PropertyPath> <xref:System.Windows.PropertyPath>구성 하는 방법을 비롯 하 여의 코드 사용은에 대 한 참조 항목에 설명 되어 있습니다. <xref:System.Windows.PropertyPath></span><span class="sxs-lookup"><span data-stu-id="55097-221">Code usage for <xref:System.Windows.PropertyPath>, including how to construct a <xref:System.Windows.PropertyPath>, is documented in the reference topic for <xref:System.Windows.PropertyPath>.</span></span>

<span data-ttu-id="55097-222">일반적 <xref:System.Windows.PropertyPath> 으로는 바인딩 사용 및 가장 간단한 애니메이션 사용을 위한 생성자와 복잡 한 애니메이션 사용을 위한 두 가지 생성자를 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55097-222">In general, <xref:System.Windows.PropertyPath> is designed to use two different constructors, one for the binding usages and simplest animation usages, and one for the complex animation usages.</span></span> <span data-ttu-id="55097-223">개체를 문자열로 사용 하는 바인딩 사용에 대 한 서명을사용합니다.<xref:System.Windows.PropertyPath.%23ctor%28System.Object%29></span><span class="sxs-lookup"><span data-stu-id="55097-223">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for binding usages, where the object is a string.</span></span> <span data-ttu-id="55097-224">개체가 인 1 단계 애니메이션 경로에 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 서명을 사용 합니다 <xref:System.Windows.DependencyProperty>.</span><span class="sxs-lookup"><span data-stu-id="55097-224">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for one-step animation paths, where the object is a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="55097-225">복합 애니메이션 <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> 에는 서명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-225">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> signature for complex animations.</span></span> <span data-ttu-id="55097-226">후자의 생성자는 첫 번째 매개 변수에 토큰 문자열을 사용하고 속성 경로 관계를 정의하기 위해 토큰 문자열의 위치를 채우는 개체 배열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55097-226">This latter constructor uses a token string for the first parameter and an array of objects that fill positions in the token string to define a property path relationship.</span></span>

## <a name="see-also"></a><span data-ttu-id="55097-227">참고자료</span><span class="sxs-lookup"><span data-stu-id="55097-227">See also</span></span>

- <xref:System.Windows.PropertyPath>
- [<span data-ttu-id="55097-228">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="55097-228">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="55097-229">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="55097-229">Storyboards Overview</span></span>](../graphics-multimedia/storyboards-overview.md)
