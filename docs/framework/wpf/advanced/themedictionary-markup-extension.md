---
title: ThemeDictionary 태그 확장
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 450956de1c7498bf2b92096b38ad2f64745a0b2d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141092"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="a76f4-102">ThemeDictionary 태그 확장</span><span class="sxs-lookup"><span data-stu-id="a76f4-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="a76f4-103">타사 컨트롤을 통합하는 사용자 지정 컨트롤 작성자 또는 애플리케이션이 컨트롤 스타일 지정에 사용할 테마별 리소스 사전을 로드하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a76f4-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="a76f4-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="a76f4-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a76f4-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a76f4-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="a76f4-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="a76f4-107">테마 정보를 포함 하는 어셈블리의 URI (uniform resource identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-107">The uniform resource identifier (URI) of the assembly that contains theme information.</span></span> <span data-ttu-id="a76f4-108">일반적으로 이는 더 큰 패키지에서 어셈블리를 참조하는 Pack URI입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="a76f4-109">어셈블리 리소스 및 Pack URI는 배포 문제를 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="a76f4-110">자세한 내용은 [WPF의 Pack URI](../app-development/pack-uris-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a76f4-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a76f4-111">설명</span><span class="sxs-lookup"><span data-stu-id="a76f4-111">Remarks</span></span>  
 <span data-ttu-id="a76f4-112">이 확장은 하나의 특정 속성 값 (에 대 한 <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>값)만 채우도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a76f4-113">이 확장을 사용 하 여 Windows Aero 테마가 사용자 시스템에 적용 되는 경우에만 사용할 일부 스타일을 포함 하는 단일 리소스 전용 어셈블리를 지정 하 고 Luna 테마가 활성 상태인 경우에만 다른 스타일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="a76f4-114">이 확장을 사용하면 컨트롤별 리소스 사전의 콘텐츠가 자동으로 유효성이 검사되고 필요한 경우 또 다른 테마에 관련되도록 다시 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="a76f4-115">문자열 `assemblyUri` (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 속성 값)은 특정 테마에 적용 되는 사전을 식별 하는 명명 규칙의 기본을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="a76f4-116">의 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> `ThemeDictionary` 논리는 미리 컴파일된 리소스 어셈블리에 포함 된 특정 테마 사전 변형을 가리키는 URI (uniform resource identifier)를 생성 하 여 규칙을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a uniform resource identifier (URI) that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="a76f4-117">여기서는 이 규칙에 대한 설명이나 개념상 일반 컨트롤 스타일 지정 및 페이지/애플리케이션 수준 스타일 지정과 테마의 상호 작용을 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="a76f4-118">를 사용 하 `ThemeDictionary` 는 기본 시나리오는 응용 프로그램 <xref:System.Windows.ResourceDictionary.Source%2A> 수준에서 `ResourceDictionary` 선언 된의 속성을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="a76f4-119">직접 URI가 아니라 확장을 `ThemeDictionary` 통해 어셈블리에 대 한 URI를 제공 하는 경우 확장 논리는 시스템 테마가 변경 될 때마다 적용 되는 무효화 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-119">When you provide a URI for the assembly through a `ThemeDictionary` extension rather than as a direct URI, the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="a76f4-120">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="a76f4-121">`ThemeDictionary` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 확장명 클래스의 <xref:System.Windows.ThemeDictionaryExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="a76f4-122">`ThemeDictionary`는 개체 요소 구문에서 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="a76f4-123">이 경우 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 속성의 값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="a76f4-124">`ThemeDictionary` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.Markup.StaticExtension.Member%2A>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 <span data-ttu-id="a76f4-125">자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="a76f4-126">`ThemeDictionary`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="a76f4-127">프로세서 구현에서이 태그 확장에 대 한 처리는 <xref:System.Windows.ThemeDictionaryExtension> 클래스에 의해 정의 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a76f4-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="a76f4-128">`ThemeDictionary`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="a76f4-129">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="a76f4-130">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="a76f4-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="a76f4-131">자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a76f4-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76f4-132">참조</span><span class="sxs-lookup"><span data-stu-id="a76f4-132">See also</span></span>

- [<span data-ttu-id="a76f4-133">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a76f4-133">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a76f4-134">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="a76f4-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="a76f4-135">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="a76f4-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="a76f4-136">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="a76f4-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)
