---
title: 인라인 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460012"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="1f93a-102">인라인 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="1f93a-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="1f93a-103">는 여러 번 사용할 수 있도록 리소스에서 요소의 시각적 모양을 정의 하는 방법으로 <xref:System.Windows.Style> 개체 및 템플릿 개체 (<xref:System.Windows.FrameworkTemplate> 서브 클래스)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="1f93a-104">이러한 이유로 <xref:System.Windows.Style> 및 <xref:System.Windows.FrameworkTemplate> 형식을 사용 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성은 거의 항상 새 항목을 인라인으로 정의 하지 않고 기존 스타일 및 템플릿에 대 한 리소스 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="1f93a-105">인라인 스타일 및 템플릿의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="1f93a-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="1f93a-106">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 스타일 및 템플릿 속성은 기술적으로 두 가지 방법 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="1f93a-107">특성 구문을 사용 하 여 리소스 내에 정의 된 스타일을 참조할 수 있습니다. 예를 들어 `<`*개체*`Style="{StaticResource`*myResourceKey*`}" .../>`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="1f93a-108">또는 속성 요소 구문을 사용 하 여 인라인 스타일을 정의할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="1f93a-109">`<` *개체* `>`</span><span class="sxs-lookup"><span data-stu-id="1f93a-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="1f93a-110">`<` *개체* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="1f93a-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="1f93a-111">`<` `Style``.../>`</span><span class="sxs-lookup"><span data-stu-id="1f93a-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="1f93a-112">`</` *개체* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="1f93a-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="1f93a-113">`</` *개체* `>`</span><span class="sxs-lookup"><span data-stu-id="1f93a-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="1f93a-114">특성 사용은 훨씬 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-114">The attribute usage is much more common.</span></span> <span data-ttu-id="1f93a-115">인라인으로 정의 되 고 리소스에 정의 되지 않은 스타일은 반드시 포함 하는 요소로만 범위가 지정 되며 리소스 키가 없기 때문에 쉽게 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="1f93a-116">일반적으로 리소스 정의 스타일은 더 다양 하 고 유용 하며, 코드에서 프로그램 논리를 태그 디자인 으로부터 분리 하는 일반적인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프로그래밍 모델 원칙을 유지 하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="1f93a-117">일반적으로 스타일 또는 템플릿 인라인을 설정 하는 이유는 해당 위치에서 해당 스타일이 나 템플릿만 사용 하려는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="1f93a-118">스타일이 나 템플릿을 사용할 수 있는 대부분의 요소는 콘텐츠 속성과 콘텐츠 모델도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="1f93a-119">스타일 지정 또는 템플릿을 한 번만 사용 하 여 만든 논리 트리를 사용 하는 경우에는 직접 태그에서 해당 하는 자식 요소를 사용 하 여 해당 콘텐츠 속성을 간단 하 게 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="1f93a-120">이는 스타일 및 템플릿 메커니즘을 모두 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="1f93a-121">개체를 반환 하는 태그 확장에서 사용 하도록 설정 된 다른 구문은 스타일 및 템플릿에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="1f93a-122">가능한 시나리오의 두 확장에는 [TemplateBinding](templatebinding-markup-extension.md) 및 <xref:System.Windows.Data.Binding>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f93a-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f93a-123">참조</span><span class="sxs-lookup"><span data-stu-id="1f93a-123">See also</span></span>

- [<span data-ttu-id="1f93a-124">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="1f93a-124">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
