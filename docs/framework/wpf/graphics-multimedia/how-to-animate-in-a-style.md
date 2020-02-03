---
title: 스타일에서 애니메이션 효과를 주는 방법
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 0b29648bf15f0046adcdee610f9565f7deb24972
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744884"
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="84a98-102">스타일에서 애니메이션 효과를 주는 방법</span><span class="sxs-lookup"><span data-stu-id="84a98-102">How to animate in a style</span></span>

<span data-ttu-id="84a98-103">이 예제에서는 스타일의 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="84a98-104">스타일 내에서 애니메이션 효과를 적용 하는 경우 스타일이 정의 된 프레임 워크 요소만 직접 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="84a98-105">Freezable 개체를 대상으로 지정 하려면 스타일이 지정 된 요소의 속성에서 "dot" 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>

<span data-ttu-id="84a98-106">다음 예제에서는 여러 애니메이션이 스타일 내에서 정의 되 고 <xref:System.Windows.Controls.Button>에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="84a98-107">사용자가 단추 위로 마우스를 이동 하면 불투명에서 부분적으로 투명 하 게 그리고 다시 반복 해 서 다시 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="84a98-108">사용자가 마우스를 단추 밖으로 움직이면 완전히 불투명 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="84a98-109">단추를 클릭 하면 배경색이 주황색에서 흰색으로 바뀌고 다시 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="84a98-110">단추를 그리는 데 사용 되는 <xref:System.Windows.Media.SolidColorBrush>를 직접 대상으로 지정할 수 없으므로 단추의 <xref:System.Windows.Controls.Control.Background%2A> 속성에서 dotting down을 사용 하 여 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="84a98-111">예제</span><span class="sxs-lookup"><span data-stu-id="84a98-111">Example</span></span>

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

<span data-ttu-id="84a98-112">스타일 내에서 애니메이션 효과를 적용 하는 경우 존재 하지 않는 개체를 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="84a98-113">예를 들어 스타일에서 <xref:System.Windows.Media.SolidColorBrush>를 사용 하 여 단추의 배경 속성을 설정 한다고 가정 하지만, 특정 시점에는 스타일이 재정의 되 고 단추의 배경이 <xref:System.Windows.Media.LinearGradientBrush>로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="84a98-114"><xref:System.Windows.Media.SolidColorBrush>에 애니메이션을 적용 하려고 하면 예외가 throw 되지 않습니다. 애니메이션은 간단 하 게 자동으로 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a98-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>

<span data-ttu-id="84a98-115">Storyboard 대상 지정 구문에 대 한 자세한 내용은 [Storyboard 개요](storyboards-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84a98-115">For more information about storyboard targeting syntax, see the [Storyboards Overview](storyboards-overview.md).</span></span> <span data-ttu-id="84a98-116">애니메이션에 대 한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84a98-116">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="84a98-117">스타일에 대 한 자세한 내용은 스타일 지정 [및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84a98-117">For more information about styles, see the [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>
