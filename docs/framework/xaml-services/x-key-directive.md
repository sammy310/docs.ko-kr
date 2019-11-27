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
ms.openlocfilehash: 8321a09db31c9f6d2103a252a195fcdbf8da3e66
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283852"
---
# <a name="xkey-directive"></a><span data-ttu-id="c05be-102">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="c05be-102">x:Key Directive</span></span>
<span data-ttu-id="c05be-103">XAML 정의 사전에서 만들어지고 참조 되는 요소를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="c05be-104">XAML 개체 요소에 `x:Key` 값을 추가 하는 것은 WPF <xref:System.Windows.ResourceDictionary>와 같이 리소스 사전에서 리소스를 식별 하는 가장 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c05be-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="c05be-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="c05be-106">XAML 특성 사용 (WPF 관련)</span><span class="sxs-lookup"><span data-stu-id="c05be-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c05be-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="c05be-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="c05be-108">키로 사용할 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-108">A text string to use as a key.</span></span> <span data-ttu-id="c05be-109">텍스트 문자열은 [XamlName 문법을](xamlname-grammar.md)준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-109">The text string must conform to the [XamlName Grammar](xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="c05be-110">태그 확장 구분 기호 내에서 키로 사용할 개체를 제공 하는 태그 확장 사용 {}입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="c05be-111">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c05be-112">주의</span><span class="sxs-lookup"><span data-stu-id="c05be-112">Remarks</span></span>  
 <span data-ttu-id="c05be-113">`x:Key`는 XAML 리소스 사전 개념을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="c05be-114">언어별 XAML은 특정 UI 프레임 워크로 남은 리소스 사전 구현을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="c05be-115">WPF에서 XAML 리소스 사전을 구현 하는 방법에 대해 자세히 알아보려면 [Xaml 리소스](../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="c05be-116">XAML 2006 및 WPF에서 `x:Key`은 특성으로 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="c05be-117">여전히 문자열이 아닌 키를 사용할 수 있지만 특성 형식에서 문자열이 아닌 값을 제공 하기 위해 태그 확장 사용이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="c05be-118">XAML 2009를 사용 하는 경우 태그 확장 중간을 요구 하지 않고 문자열 이외의 개체 형식으로 키가 지정 된 사전을 명시적으로 지원 하기 위해 `x:Key`를 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="c05be-119">이 항목의 "XAML 2009" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="c05be-120">설명 섹션의 나머지 부분은 XAML 2006 구현에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="c05be-121">`x:Key`의 특성 값은 [XamlName 문법](xamlname-grammar.md) 에 정의 된 문자열이 될 수도 있고 태그 확장을 통해 계산 되는 개체 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="c05be-122">WPF의 예제는 "WPF 사용 정보"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="c05be-123"><xref:System.Collections.IDictionary> 구현인 부모 요소의 자식 요소는 일반적으로 해당 사전 내에서 고유한 키 값을 지정 하는 `x:Key` 특성을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="c05be-124">프레임 워크는 특정 형식에 대 한 `x:Key`를 대체 하기 위해 별칭 지정 키 속성을 구현할 수 있습니다. 이러한 속성을 정의 하는 형식은 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="c05be-125">`x:Key`를 지정 하는 것과 동일한 코드는 기본 <xref:System.Collections.IDictionary>에 사용 되는 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="c05be-126">예를 들어 WPF에서 리소스에 대 한 태그에 적용 되는 `x:Key`는 코드에서 WPF <xref:System.Windows.ResourceDictionary>에 리소스를 추가할 때 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>의 `key` 매개 변수 값과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c05be-127">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="c05be-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="c05be-128">WPF <xref:System.Windows.ResourceDictionary>와 같이 <xref:System.Collections.IDictionary> 구현인 부모 개체의 자식 개체는 일반적으로 `x:Key` 특성을 포함 해야 하며 키 값은 해당 사전 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="c05be-129">다음과 같은 두 가지 주목할 만한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-129">There are two notable exceptions:</span></span>  
  
- <span data-ttu-id="c05be-130">일부 WPF 형식은 사전 사용에 대 한 암시적 키를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="c05be-131">예를 들어 <xref:System.Windows.Style.TargetType%2A>또는 <xref:System.Windows.DataTemplate.DataType%2A>있는 <xref:System.Windows.DataTemplate> 있는 <xref:System.Windows.Style>는 <xref:System.Windows.ResourceDictionary>에 있고 암시적 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
- <span data-ttu-id="c05be-132">WPF는 병합 된 리소스 사전 개념을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="c05be-133">병합 된 사전 간에 키를 공유할 수 있으며 <xref:System.Windows.FrameworkContentElement.FindResource%2A>를 사용 하 여 공유 키 동작에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="c05be-134">자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-134">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="c05be-135">전반적인 WPF XAML 구현 및 응용 프로그램 모델에서 키 고유성이 XAML 태그 컴파일러에 의해 검사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="c05be-136">대신, `x:Key` 값이 없거나 고유 하지 않으면 로드 시간 XAML 파서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="c05be-137">그러나 WPF 용 사전의 Visual Studio 처리는 디자인 단계에서 이러한 오류를 종종 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-137">However, Visual Studio handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="c05be-138">표시 된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 생성 하 여 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션을 채우는 방법에서 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="c05be-139"><xref:System.Windows.ResourceDictionary>은 일반적으로 태그에서 요소로 명시적으로 제공 되지 않습니다 .이는 명확 하 게 하기 위해 필요한 경우 (예를 들어, <xref:System.Windows.FrameworkElement.Resources%2A> property 요소와 사전을 채우는 내의 항목 사이에 컬렉션 개체 요소가 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c05be-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="c05be-140">컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대 한 자세한 내용은 [XAML 구문](../wpf/advanced/xaml-syntax-in-detail.md)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="c05be-141">WPF XAML 구현에서 리소스 사전 키에 대 한 처리는 <xref:System.Windows.ResourceKey> 추상 클래스에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="c05be-142">그러나 WPF XAML 프로세서는 용도에 따라 키에 대해 서로 다른 기본 확장 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="c05be-143">예를 들어 <xref:System.Windows.DataTemplate> 또는 파생 클래스의 키는 별도로 처리 되 고 고유한 <xref:System.Windows.DataTemplateKey> 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="c05be-144">키와 이름은 기본 XAML 정의에서 다른 지시문 및 언어 요소 (`x:Key` `x:Name`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="c05be-145">키와 이름은 WPF 정의 및 이러한 개념의 응용 프로그램에서 다양 한 상황에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="c05be-146">자세한 내용은 [WPF XAML 이름 범위](../wpf/advanced/wpf-xaml-namescopes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-146">For details, see [WPF XAML Namescopes](../wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="c05be-147">앞에서 설명한 것 처럼 키 값은 태그 확장을 통해 제공 될 수 있으며 문자열 값이 아닌 다른 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="c05be-148">예제 WPF 시나리오는 `x:Key` 값이 [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-148">An example WPF scenario is that the value of `x:Key` may be a [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="c05be-149">특정 컨트롤은 스타일을 완전히 바꾸지 않고 해당 컨트롤의 모양과 동작의 일부에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 형식의 스타일 키를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="c05be-150">이러한 키의 예는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="c05be-151">WPF 병합 사전 기능에서는 키 고유성 및 키 조회 동작에 대 한 추가 고려 사항을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="c05be-152">자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c05be-152">For more information, see [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="c05be-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="c05be-153">XAML 2009</span></span>  
 <span data-ttu-id="c05be-154">XAML 2009은 `x:Key` 항상 특성 형식으로 제공 되는 제한을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="c05be-155">WPF에서 XAML 2009 기능을 사용할 수 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="c05be-156">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="c05be-157">XAML 2009에서는 다음을 사용 하 여 `x:Key` 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="c05be-158">XAML 요소 사용 (XAML 2009에만 해당)</span><span class="sxs-lookup"><span data-stu-id="c05be-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="c05be-159">XAML 값</span><span class="sxs-lookup"><span data-stu-id="c05be-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="c05be-160">특수 한 사전에서 지정 된 `object`에 대 한 키로 사용 되는 개체의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
- <span data-ttu-id="c05be-161">이러한 종류의 용도에 대 한 컨테이너/부모는 여기에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="c05be-162">`object`은 특수 사전 구현을 나타내는 개체 요소의 자식일 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="c05be-163">`keyObject`은 해당 하는 특정 사전 구현에 대 한 키로 적합 한 개체 인스턴스 (또는 값 형식의 값)가 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
- <span data-ttu-id="c05be-164">WPF는 이러한 사용법이 필요한 사전을 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="c05be-165">개체 키는 XAML 언어의 일반적인 기능입니다. XAML로 사전을 만드는 것이 바람직한 특정 사용자 지정 사전 시나리오에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="c05be-166">리소스에 대해 문자열이 아닌 키를 사용 하는 암시적 스타일과 같은 WPF 기능의 경우 키를 설정 하거나 지정 하는 다른 기술 들이 존재 하므로 개체 키를 사용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
- <span data-ttu-id="c05be-167">*keyObject* 는 직접 개체 인스턴스가 아닌 개체 요소 형식에서 태그 확장 사용이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="c05be-168">Silverlight 사용 메모</span><span class="sxs-lookup"><span data-stu-id="c05be-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="c05be-169">Silverlight에 대 한 `x:Key` 별도로 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c05be-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="c05be-170">자세한 내용은 [XAML 네임 스페이스 (x:)를 참조 하세요. 언어 기능 (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).</span><span class="sxs-lookup"><span data-stu-id="c05be-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05be-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c05be-171">See also</span></span>

- [<span data-ttu-id="c05be-172">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="c05be-172">XAML Resources</span></span>](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="c05be-173">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="c05be-173">Resources and Code</span></span>](../wpf/advanced/resources-and-code.md)
- [<span data-ttu-id="c05be-174">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c05be-174">StaticResource Markup Extension</span></span>](../wpf/advanced/staticresource-markup-extension.md)
