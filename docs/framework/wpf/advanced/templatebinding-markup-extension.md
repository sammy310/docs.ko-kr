---
title: TemplateBinding 태그 확장
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 1e4adc4c0b5579ca6c75324f358e70edd48273cc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372232"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="c6a9e-102">TemplateBinding 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c6a9e-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="c6a9e-103">컨트롤 템플릿의 속성 값을 템플릿 기반 컨트롤의 다른 속성 값에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c6a9e-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="c6a9e-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="c6a9e-105">XAML 특성 사용(템플릿 또는 스타일의 Setter 속성의 경우)</span><span class="sxs-lookup"><span data-stu-id="c6a9e-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c6a9e-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="c6a9e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="c6a9e-107">setter 구문에 설정할 속성의 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="c6a9e-108">템플릿을 기반으로 만들 형식에 존재하는 또 다른 종속성 속성이며 해당 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="c6a9e-109">또는</span><span class="sxs-lookup"><span data-stu-id="c6a9e-109">- or -</span></span><br /><br /> <span data-ttu-id="c6a9e-110">템플릿을 기반으로 만들 대상 형식과는 다른 형식으로 정의되는 "점으로 구분된" 속성 이름이며</span><span class="sxs-lookup"><span data-stu-id="c6a9e-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="c6a9e-111">실제로는 <xref:System.Windows.PropertyPath>입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="c6a9e-112">참조 [PropertyPath XAML 구문](propertypath-xaml-syntax.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6a9e-113">설명</span><span class="sxs-lookup"><span data-stu-id="c6a9e-113">Remarks</span></span>  
 <span data-ttu-id="c6a9e-114">A `TemplateBinding` 는 최적화 된 형태의 [바인딩](binding-markup-extension.md) 템플릿 시나리오의 경우 유사를 `Binding` 사용 하 여 생성 `{Binding RelativeSource={RelativeSource TemplatedParent}}`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="c6a9e-115">
  `TemplateBinding\`은 속성이 기본적으로 양방향 바인딩과 관련되었더라도 항상 단방향 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="c6a9e-116">관련된 두 속성은 모두 종속성 속성이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="c6a9e-117">템플릿 기반 부모에 양방향 바인딩을 달성 하기 위해 다음 바인딩 문을 대신 사용 `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span> 
  
 <span data-ttu-id="c6a9e-118">[RelativeSource](relativesource-markupextension.md) 함께 또는 그 대신에 사용 되는 또 다른 태그 확장은 `TemplateBinding` 템플릿 내에서 상대적 속성 바인딩을 수행 하려면.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="c6a9e-119">컨트롤 템플릿을 설명 하는 개념은 여기서 다루지 않습니다. 자세한 내용은 [Control 스타일 및 템플릿](../controls/control-styles-and-templates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="c6a9e-120">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="c6a9e-121">`TemplateBinding` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.TemplateBindingExtension.Property%2A> 확장 클래스의 <xref:System.Windows.TemplateBindingExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="c6a9e-122">다른 요소 구문도 가능하지만 실제 환경에서 적용하지 않으므로 표시하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="c6a9e-123">`TemplateBinding`은 평가된 식을 사용하여 setter 내에 값을 채우는 데 사용됩니다. `TemplateBinding`에 대한 개체 요소 구문을 사용하여 `<Setter.Property>` 속성 요소 구문을 채우는 경우 작업이 번거롭습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="c6a9e-124">`TemplateBinding` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.TemplateBindingExtension.Property%2A>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="c6a9e-125">자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="c6a9e-126">
          `TemplateBinding\`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="c6a9e-127">에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서 구현에서이 태그 확장에 대 한 처리는 정의한는 <xref:System.Windows.TemplateBindingExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="c6a9e-128">`TemplateBinding`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="c6a9e-129">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="c6a9e-130">XAML 사용의 모든 태그 확장을 `{` 고 `}` XAML 프로세서는 태그 확장이 특성을 처리 해야 한다는 것을 인식 하는 규칙은 특성 구문에서 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="c6a9e-131">자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6a9e-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a9e-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6a9e-132">See also</span></span>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c6a9e-133">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c6a9e-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="c6a9e-134">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="c6a9e-134">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="c6a9e-135">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="c6a9e-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="c6a9e-136">RelativeSource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c6a9e-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="c6a9e-137">Binding 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c6a9e-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
