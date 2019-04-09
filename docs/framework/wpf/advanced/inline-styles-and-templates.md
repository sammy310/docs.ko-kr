---
title: 인라인 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091436"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="5a16a-102">인라인 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5a16a-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="5a16a-103">제공 <xref:System.Windows.Style> 개체 및 템플릿은 개체 (<xref:System.Windows.FrameworkTemplate> 서브 클래스) 리소스에서 요소의 시각적 모양을 정의 하는 방법,으로 사용할 수 있도록 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="5a16a-104">따라서 특성 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 형식을 사용 하 <xref:System.Windows.Style> 고 <xref:System.Windows.FrameworkTemplate> 거의 항상 리소스 참조를 기존 스타일 및 템플릿 사용 하지 않고 새로 인라인을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="5a16a-105">인라인 스타일 및 템플릿의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5a16a-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="5a16a-106">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 스타일 및 템플릿 속성 기술적으로 두 가지 방법 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="5a16a-107">예를 들어 리소스 내에서 정의 된 스타일을 참조할 특성 구문을 사용할 수 있습니다 `<` *개체*`Style="{StaticResource`*myResourceKey*`}" .../>`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="5a16a-108">또는 예를 들어 인라인 스타일을 정의 하려면 속성 요소 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 `<` *<span data-ttu-id="5a16a-109">object</span><span class="sxs-lookup"><span data-stu-id="5a16a-109">object</span></span>* `>`  
  
 `<` *<span data-ttu-id="5a16a-110">object</span><span class="sxs-lookup"><span data-stu-id="5a16a-110">object</span></span>* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *<span data-ttu-id="5a16a-111">object</span><span class="sxs-lookup"><span data-stu-id="5a16a-111">object</span></span>* `.Style>`  
  
 `</` *<span data-ttu-id="5a16a-112">object</span><span class="sxs-lookup"><span data-stu-id="5a16a-112">object</span></span>* `>`  
  
 <span data-ttu-id="5a16a-113">특성을 사용 하는 것이 훨씬 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-113">The attribute usage is much more common.</span></span> <span data-ttu-id="5a16a-114">인라인으로 정의 및에서는 정의 되지 않은 리소스는 스타일을 포함 하는 요소에만 범위가 지정 이므로 사용할 수 없습니다 다시 쉽게 없는 리소스 키를 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-114">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="5a16a-115">일반적 리소스 정의 스타일을 유용 하 게 이며 더 일반적인 부합 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프로그래밍 모델 원칙 태그에는 디자인에서 코드의 프로그램 논리를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-115">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="5a16a-116">일반적으로 해당 위치에 해당 스타일이 나 템플릿을 사용 하려는 경우에 스타일 또는 템플릿이 인라인을 설정할 필요가 없습니다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-116">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="5a16a-117">스타일이 나 템플릿을 사용할 수 있는 대부분의 요소는 또한 콘텐츠 속성 및 콘텐츠 모델을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-117">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="5a16a-118">어떤 논리 트리만 사용 하는 경우 만든 스타일이 나 템플릿을 통해 한 번,는 것이 더욱 쉽게 직접 태그에서 해당 자식 요소를 사용 하 여 해당 콘텐츠 속성을 채우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-118">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="5a16a-119">이 스타일 및 템플릿 메커니즘은 완전히 바이패스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-119">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="5a16a-120">개체를 반환 하는 태그 확장으로 사용 하도록 설정 하는 다른 구문 스타일 및 템플릿을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-120">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="5a16a-121">이러한 두 확장 가능한 시나리오에 포함할 [TemplateBinding](templatebinding-markup-extension.md) 고 <xref:System.Windows.Data.Binding>입니다.</span><span class="sxs-lookup"><span data-stu-id="5a16a-121">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a16a-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a16a-122">See also</span></span>

- [<span data-ttu-id="5a16a-123">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5a16a-123">Styling and Templating</span></span>](../controls/styling-and-templating.md)
