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
ms.openlocfilehash: 4ffd7a2922c7f3ba35ccb9ac7ce29a6a00cd99af
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837209"
---
# <a name="xkey-directive"></a><span data-ttu-id="ae7cf-102">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="ae7cf-102">x:Key Directive</span></span>
<span data-ttu-id="ae7cf-103">XAML 정의된 사전에서 만들어지고 참조되는 요소를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="ae7cf-104">`x:Key` 값을 XAML 개체 요소를 추가하는 것은 WPF <xref:System.Windows.ResourceDictionary>에서처럼 리소스 사전에서 리소스를 식별하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ae7cf-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="ae7cf-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="ae7cf-106">XAML 특성 사용(WPF 특정)</span><span class="sxs-lookup"><span data-stu-id="ae7cf-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ae7cf-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="ae7cf-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="ae7cf-108">키로 사용할 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-108">A text string to use as a key.</span></span> <span data-ttu-id="ae7cf-109">텍스트 문자열은 [XamlName 문법을](xamlname-grammar.md)준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-109">The text string must conform to the [XamlName Grammar](xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="ae7cf-110">태그 확장 구분 기호 내에서 키로 사용할 개체를 제공 하는 태그 확장 사용 {}입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="ae7cf-111">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae7cf-112">주의</span><span class="sxs-lookup"><span data-stu-id="ae7cf-112">Remarks</span></span>  
 <span data-ttu-id="ae7cf-113">`x:Key`는 XAML 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="ae7cf-114">언어로서의 XAML은 리소스 사전 구현을 정의하지 않으며, 이러한 구현은 특정 UI 프레임워크에서 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="ae7cf-115">WPF에서 XAML 리소스 사전을 구현 하는 방법에 대해 자세히 알아보려면 [Xaml 리소스](../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="ae7cf-116">XAML 2006 및 WPF에서 `x:Key`은 특성으로 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="ae7cf-117">문자열이 아닌 키는 여전히 사용할 수 있지만 특성 양식에서 문자열이 아닌 값을 제공하려면 이 태그 확장을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="ae7cf-118">XAML 2009를 사용 하는 경우 태그 확장 중간을 요구 하지 않고 문자열 이외의 개체 형식으로 키가 지정 된 사전을 명시적으로 지원 하기 위해 `x:Key`를 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="ae7cf-119">이 항목의 "XAML 2009" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="ae7cf-120">설명 섹션의 나머지 부분은 XAML 2006 구현에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="ae7cf-121">`x:Key`의 특성 값은 [XamlName 문법](xamlname-grammar.md) 에 정의 된 문자열이 될 수도 있고 태그 확장을 통해 계산 되는 개체 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="ae7cf-122">WPF의 예제는 "WPF 사용 정보"를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="ae7cf-123"><xref:System.Collections.IDictionary> 구현인 부모 요소의 자식 요소는 일반적으로 해당 사전 내에서 고유한 키 값을 지정하는 `x:Key` 특성을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="ae7cf-124">프레임워크는 특정 형식의 `x:Key`에 대해 별칭이 지정된 키 속성을 구현할 수 있습니다. 이러한 속성을 정의하는 형식은 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>로 특성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="ae7cf-125">코드에서 `x:Key`를 지정하는 것과 동일한 기능을 하는 것은 기본 <xref:System.Collections.IDictionary>용 키를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="ae7cf-126">예를 들어 WPF에서 리소스에 대해 태그에서 적용된 `x:Key`는 코드에서 리소스를 WPF <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>에 추가할 때 지정하는 <xref:System.Windows.ResourceDictionary>의 `key` 매개 변수 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="ae7cf-127">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="ae7cf-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="ae7cf-128">WPF <xref:System.Collections.IDictionary>와 같이 <xref:System.Windows.ResourceDictionary> 구현인 부모 개체의 자식 개체는 일반적으로 `x:Key` 특성을 포함해야 하며 키 값은 해당 사전 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="ae7cf-129">두 가지 중요한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-129">There are two notable exceptions:</span></span>  
  
- <span data-ttu-id="ae7cf-130">일부 WPF 형식은 사전 사용을 위한 암시적 키를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="ae7cf-131">예를 들어, <xref:System.Windows.Style>이 있는 <xref:System.Windows.Style.TargetType%2A> 또는 <xref:System.Windows.DataTemplate>이 있는 <xref:System.Windows.DataTemplate.DataType%2A>를 <xref:System.Windows.ResourceDictionary>에 배치할 수 있고 암시적 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
- <span data-ttu-id="ae7cf-132">WPF는 병합된 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="ae7cf-133">키는 병합된 사전 간에 공유될 수 있으며 공유 키 동작은 <xref:System.Windows.FrameworkContentElement.FindResource%2A>를 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="ae7cf-134">자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-134">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="ae7cf-135">전체적인 WPF XAML 구현 및 응용 프로그램 모델에서 XAML 태그 컴파일러는 키 고유성을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="ae7cf-136">대신, `x:Key` 값이 없거나 고유하지 않으면 로드할 때 XAML 구문 분석기 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="ae7cf-137">그러나 WPF 용 사전의 Visual Studio 처리는 디자인 단계에서 이러한 오류를 종종 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-137">However, Visual Studio handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="ae7cf-138">표시된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 생성하여 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션을 채우는 방법을 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="ae7cf-139"><xref:System.Windows.ResourceDictionary>는 태그에 명시적으로 요소로 제공되지 않는 것이 일반적입니다. 단, 필요한 경우 명확성을 높이기 위해 명시적으로 제공할 수 있으며 이 경우 <xref:System.Windows.FrameworkElement.Resources%2A> 속성 요소와 사전을 채우는 항목 사이의 컬렉션 개체 요소로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="ae7cf-140">컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대 한 자세한 내용은 [XAML 구문](../wpf/advanced/xaml-syntax-in-detail.md)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="ae7cf-141">WPF XAML 구현에서 리소스 사전 키의 처리는 <xref:System.Windows.ResourceKey> 추상 클래스를 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="ae7cf-142">하지만 WPF XAML 프로세서는 키 용도에 따라 키에 대해 서로 다른 기본 확장 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="ae7cf-143">예를 들어 <xref:System.Windows.DataTemplate> 또는 파생 클래스에 대한 키는 별도로 처리되어 별개의 <xref:System.Windows.DataTemplateKey> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="ae7cf-144">키와 이름은 기본 XAML 정의에서 다른 지시문 및 언어 요소(`x:Key` 및 `x:Name`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="ae7cf-145">키와 이름은 이러한 개념의 WPF 정의 및 응용 프로그램에 의해 다른 상황에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="ae7cf-146">자세한 내용은 참조 하세요 [WPF XAML 이름 범위](../wpf/advanced/wpf-xaml-namescopes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-146">For details, see [WPF XAML Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="ae7cf-147">앞에서 설명한 것처럼 키 값은 문자열 값 이외에 태그 확장을 통해 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="ae7cf-148">예제 WPF 시나리오는 `x:Key` 값이 [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-148">An example WPF scenario is that the value of `x:Key` may be a [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="ae7cf-149">특정 컨트롤은 스타일을 완전히 바꾸지 않고 해당 컨트롤의 모양과 동작에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 형식의 스타일 키를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="ae7cf-150">이러한 키로는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="ae7cf-151">WPF 병합된 사전 기능은 키 고유성 및 키 조회 동작에 대한 추가 고려 사항을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="ae7cf-152">자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-152">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="ae7cf-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="ae7cf-153">XAML 2009</span></span>  
 <span data-ttu-id="ae7cf-154">XAML 2009은 `x:Key` 항상 특성 형식으로 제공 되는 제한을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="ae7cf-155">WPF에서 XAML 2009 기능을 사용할 수 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="ae7cf-156">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="ae7cf-157">XAML 2009에서는 다음을 사용 하 여 `x:Key` 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="ae7cf-158">XAML 요소 사용(XAML 2009만 해당)</span><span class="sxs-lookup"><span data-stu-id="ae7cf-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="ae7cf-159">XAML 값</span><span class="sxs-lookup"><span data-stu-id="ae7cf-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="ae7cf-160">특수 사전에서 주어진 `object`에 대한 키로 사용되는 개체의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
- <span data-ttu-id="ae7cf-161">이러한 종류의 사용에 대한 컨테이너/부모는 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="ae7cf-162">`object`는 특수 사전 구현을 나타내는 개체 요소의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="ae7cf-163">`keyObject`는 특정 특수 사전 구현을 위한 키로 적합한 개체 인스턴스(또는 값 형식의 값)로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
- <span data-ttu-id="ae7cf-164">WPF는 이 사용에 필요한 사전을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="ae7cf-165">개체 키는 XAML 언어의 보다 일반적인 기능이며 XAML에서 사전을 만드는 것이 바람직할 때 특정한 사용자 지정 사전 시나리오에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="ae7cf-166">리소스에 대해 문자열이 아닌 키를 사용하는 암시적 스타일 같은 WPF 기능의 경우 키를 설정하거나 지정하는 다른 방법이 있으므로 개체 키를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
- <span data-ttu-id="ae7cf-167">*keyObject* 는 직접 개체 인스턴스가 아닌 개체 요소 형식에서 태그 확장 사용이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="ae7cf-168">Silverlight 사용 정보</span><span class="sxs-lookup"><span data-stu-id="ae7cf-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="ae7cf-169">Silverlight용 `x:Key`는 별도로 문서화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="ae7cf-170">자세한 내용은 [XAML 네임 스페이스 (x:)를 참조 하세요. 언어 기능 (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span><span class="sxs-lookup"><span data-stu-id="ae7cf-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7cf-171">참조</span><span class="sxs-lookup"><span data-stu-id="ae7cf-171">See also</span></span>

- [<span data-ttu-id="ae7cf-172">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="ae7cf-172">XAML Resources</span></span>](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="ae7cf-173">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="ae7cf-173">Resources and Code</span></span>](../wpf/advanced/resources-and-code.md)
- [<span data-ttu-id="ae7cf-174">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="ae7cf-174">StaticResource Markup Extension</span></span>](../wpf/advanced/staticresource-markup-extension.md)
