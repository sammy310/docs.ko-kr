---
title: x:Key 지시문
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: c05f98932ceceeb1530b34a09b1923f2af1378b5
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432757"
---
# <a name="xkey-directive"></a><span data-ttu-id="75f24-102">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="75f24-102">x:Key Directive</span></span>
<span data-ttu-id="75f24-103">XAML 정의 사전에서 생성되고 참조되는 요소를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="75f24-104">XAML 개체 요소에 `x:Key` 값을 추가하는 것은 WPF와 <xref:System.Windows.ResourceDictionary>같은 리소스 사전에서 리소스를 식별하는 가장 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="75f24-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="75f24-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="75f24-106">XAML 특성 사용(WPF별)</span><span class="sxs-lookup"><span data-stu-id="75f24-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="75f24-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="75f24-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="75f24-108">키로 사용할 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-108">A text string to use as a key.</span></span> <span data-ttu-id="75f24-109">텍스트 문자열은 [XamlName 문법을](xamlname-grammar.md)준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-109">The text string must conform to the [XamlName Grammar](xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="75f24-110">태그 확장 구분 기호 {}내에서 키로 사용할 개체를 제공하는 태그 확장 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="75f24-111">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75f24-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f24-112">설명</span><span class="sxs-lookup"><span data-stu-id="75f24-112">Remarks</span></span>  
 <span data-ttu-id="75f24-113">`x:Key`XAML 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="75f24-114">XAML은 특정 UI 프레임워크에 남아 있는 리소스 사전 구현을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="75f24-115">WPF에서 XAML 리소스 사전을 구현하는 방법에 대한 자세한 내용은 [XAML 리소스를](../fundamentals/xaml-resources-define.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75f24-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="75f24-116">XAML 2006 및 WPF에서는 특성으로 `x:Key` 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="75f24-117">여전히 비문자열 키를 사용할 수 있지만 특성 양식에 문자열이 아닌 값을 제공하기 위해서는 태그 확장 사용이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="75f24-118">XAML 2009를 사용하는 `x:Key` 경우 마크업 확장 중간 없이 문자열이 아닌 개체 형식별로 키에 지정된 사전을 명시적으로 지원하기 위해 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="75f24-119">이 항목의 "XAML 2009" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75f24-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="75f24-120">주석 섹션의 나머지 부분은 XAML 2006 구현에 특히 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="75f24-121">의 `x:Key` 특성 값은 [XamlName 문법에](xamlname-grammar.md) 정의된 모든 문자열이거나 태그 확장을 통해 평가되는 개체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="75f24-122">WPF의 예는 "WPF 사용 노트"를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75f24-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="75f24-123"><xref:System.Collections.IDictionary> 구현인 부모 요소의 자식 요소에는 `x:Key` 일반적으로 해당 사전 내에서 고유한 키 값을 지정하는 특성이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="75f24-124">프레임워크는 특정 `x:Key` 형식에서 대체할 별칭 키 속성을 구현할 수 있습니다. 이러한 속성을 정의하는 형식은 로 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>인해 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="75f24-125">지정에 `x:Key` 해당하는 코드는 기본 <xref:System.Collections.IDictionary>에 사용되는 키입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="75f24-126">예를 들어 `x:Key` WPF의 리소스에 대한 태그에 적용되는 것은 코드의 `key` WPF에 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> <xref:System.Windows.ResourceDictionary> 리소스를 추가할 때의 매개 변수 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="75f24-127">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="75f24-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="75f24-128">WPF와 <xref:System.Collections.IDictionary> <xref:System.Windows.ResourceDictionary>같은 구현인 부모 개체의 자식 개체는 일반적으로 `x:Key` 특성을 포함해야 하며 키 값은 해당 사전 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="75f24-129">두 가지 주목할 만한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-129">There are two notable exceptions:</span></span>  
  
- <span data-ttu-id="75f24-130">일부 WPF 형식은 사전 사용에 대한 암시적 키를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="75f24-131">예를 들어 <xref:System.Windows.Style> <xref:System.Windows.Style.TargetType%2A>a 또는 a와 <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A>함께 있는 a는 에 <xref:System.Windows.ResourceDictionary> 있을 수 있으며 암시적 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
- <span data-ttu-id="75f24-132">WPF는 병합된 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="75f24-133">병합된 사전 간에 키를 공유할 수 있으며 을 사용하여 <xref:System.Windows.FrameworkContentElement.FindResource%2A>공유 키 동작에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="75f24-134">자세한 내용은 [병합된 리소스 사전](../../framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75f24-134">For more information, see [Merged Resource Dictionaries](../../framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="75f24-135">전체 WPF XAML 구현 및 응용 프로그램 모델에서 키 고유성은 XAML 태그 컴파일러에서 검사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="75f24-136">대신 누락되었거나 `x:Key` 고유하지 않은 값이 로드 타임 XAML 파서 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="75f24-137">그러나 WPF용 사전의 Visual Studio 처리는 설계 단계에서 이러한 오류를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-137">However, Visual Studio handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="75f24-138">표시된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 채우는 컬렉션을 생성하는 방법에 <xref:System.Windows.FrameworkElement.Resources%2A> 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="75f24-139">A는 <xref:System.Windows.ResourceDictionary> 일반적으로 태그의 요소로 명시적으로 제공되지 않지만 명확성을 원한다면 경우에 따라 제공될 수 <xref:System.Windows.FrameworkElement.Resources%2A> 있습니다(속성 요소와 사전을 채우는 항목 사이의 컬렉션 개체 요소일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="75f24-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="75f24-140">컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대한 자세한 내용은 [XAML 구문 세부 정보를](../../framework/wpf/advanced/xaml-syntax-in-detail.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75f24-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../../framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="75f24-141">WPF XAML 구현에서 리소스 사전 키에 대한 <xref:System.Windows.ResourceKey> 처리는 추상 클래스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="75f24-142">그러나 WPF XAML 프로세서는 사용량에 따라 키에 대해 다른 기본 확장 유형을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="75f24-143">예를 들어 a <xref:System.Windows.DataTemplate> 또는 파생 클래스의 키는 별도로 처리되고 고유한 <xref:System.Windows.DataTemplateKey> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="75f24-144">키와 이름은 기본 XAML`x:Key` 정의에서 서로 다른 지시문 및 언어 요소(대)를 `x:Name`사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="75f24-145">키와 이름은 WPF 정의 및 이러한 개념의 응용 프로그램에 의해 다른 상황에서사용된다.</span><span class="sxs-lookup"><span data-stu-id="75f24-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="75f24-146">자세한 내용은 [WPF XAML 네임스코프 를](../../framework/wpf/advanced/wpf-xaml-namescopes.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75f24-146">For details, see [WPF XAML Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="75f24-147">앞에서 설명한 것처럼 키 값은 태그 확장을 통해 제공될 수 있으며 문자열 값이 아닌 다른 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="75f24-148">WPF 시나리오의 예는 의 `x:Key` 값이 [ComponentResourceKey](../../framework/wpf/advanced/componentresourcekey-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="75f24-148">An example WPF scenario is that the value of `x:Key` may be a [ComponentResourceKey](../../framework/wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="75f24-149">특정 컨트롤은 스타일을 완전히 대체하지 않고 해당 컨트롤의 모양과 동작의 일부에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 유형의 스타일 키를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="75f24-150">이러한 키의 예는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="75f24-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="75f24-151">WPF 병합 사전 기능은 키 고유성 및 키 조회 동작에 대한 추가 고려 사항을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="75f24-152">자세한 내용은 [병합된 리소스 사전](../../framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75f24-152">For more information, see [Merged Resource Dictionaries](../../framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="75f24-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="75f24-153">XAML 2009</span></span>  
 <span data-ttu-id="75f24-154">XAML 2009는 `x:Key` 항상 특성 형태로 제공되는 제한을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="75f24-155">WPF에서는 XAML 2009 기능을 사용할 수 있지만 마크업 컴파일되지 않은 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="75f24-156">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="75f24-157">XAML 2009에서 다음 `x:Key` 사용을 통해 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="75f24-158">XAML 요소 사용(XAML 2009에만)</span><span class="sxs-lookup"><span data-stu-id="75f24-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="75f24-159">XAML 값</span><span class="sxs-lookup"><span data-stu-id="75f24-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="75f24-160">특수 사전에서 제공된 `object` 개체의 키로 사용되는 개체에 대한 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
- <span data-ttu-id="75f24-161">이러한 종류의 사용에 대한 컨테이너/부모는 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="75f24-162">`object`는 특수 사전 구현을 나타내는 개체 요소의 자식으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="75f24-163">`keyObject`는 특정 특수 사전 구현의 키로 적합한 개체 인스턴스(또는 값 형식의 값)가 될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
- <span data-ttu-id="75f24-164">WPF는 이 사용이 필요한 사전을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="75f24-165">개체 키는 XAML 언어의 일반적인 기능으로 XAML에서 사전을 만드는 것이 바람직한 특정 사용자 지정 사전 시나리오에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="75f24-166">리소스에 비 문자열 키를 사용하는 암시적 스타일과 같은 WPF 기능의 경우 키를 설정하거나 지정하는 다른 기술이 있으므로 개체 키를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
- <span data-ttu-id="75f24-167">`keyObject`또한 직접 개체 인스턴스가 아닌 개체 요소 형식의 태그 확장 사용일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-167">`keyObject` could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="75f24-168">실버라이트 사용 노트</span><span class="sxs-lookup"><span data-stu-id="75f24-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="75f24-169">`x:Key`실버라이트에 대한 설명은 별도로 문서화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75f24-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="75f24-170">자세한 내용은 [XAML 네임스페이스(x:)를 참조하십시오. 언어 기능 (실버 라이트)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span><span class="sxs-lookup"><span data-stu-id="75f24-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f24-171">참조</span><span class="sxs-lookup"><span data-stu-id="75f24-171">See also</span></span>

- [<span data-ttu-id="75f24-172">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="75f24-172">XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="75f24-173">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="75f24-173">Resources and Code</span></span>](../../framework/wpf/advanced/resources-and-code.md)
- [<span data-ttu-id="75f24-174">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="75f24-174">StaticResource Markup Extension</span></span>](../../framework/wpf/advanced/staticresource-markup-extension.md)
