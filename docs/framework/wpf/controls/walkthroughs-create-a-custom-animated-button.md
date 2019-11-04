---
title: '연습: 사용자 지정 애니메이션 단추 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: a3990a7dc446c264e0865e15dadcdaf3ba0a0ff6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460056"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="6b79f-102">연습: 사용자 지정 애니메이션 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="6b79f-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="6b79f-103">이름에서 알 수 있듯이 WPF (Windows Presentation Foundation)는 고객에 게 풍부한 프레젠테이션 환경을 만드는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="6b79f-104">이러한 연습에서는 단추 (애니메이션 포함)의 모양과 동작을 사용자 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="6b79f-105">응용 프로그램의 모든 단추에이 사용자 지정 단추를 쉽게 적용할 수 있도록 스타일 및 템플릿을 사용 하 여이 사용자 지정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="6b79f-106">다음 그림에서는 사용자가 만드는 사용자 지정 된 단추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-106">The following illustration shows the customized button that you will create.</span></span>

 <span data-ttu-id="6b79f-107">![만들 사용자 지정 된 단추](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="6b79f-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>

 <span data-ttu-id="6b79f-108">단추 모양을 구성 하는 벡터 그래픽은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="6b79f-109">는 강력 하 고 확장 가능 하다는 점을 제외 하 고 HTML과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="6b79f-110">Visual Studio 또는 메모장을 사용 하 여 수동으로 입력 하거나 Blend for Visual Studio와 같은 시각적 디자인 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-110">can be typed in manually using Visual Studio or Notepad, or you can use a visual design tool such as Blend for Visual Studio.</span></span> <span data-ttu-id="6b79f-111">Blend는 기본 XAML 코드를 만들어 작동 하므로 두 메서드 모두 동일한 그래픽을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-111">Blend works by creating underlying XAML code, so both methods create the same graphics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6b79f-112">단원 내용</span><span class="sxs-lookup"><span data-stu-id="6b79f-112">In This Section</span></span>
 <span data-ttu-id="6b79f-113">[Microsoft Expression Blend를 사용 하 여 단추 만들기](walkthrough-create-a-button-by-using-microsoft-expression-blend.md) Expression Blend의 디자이너 기능을 사용 하 여 사용자 지정 동작을 사용 하 여 단추를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-113">[Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md) Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>

 <span data-ttu-id="6b79f-114">[XAML을 사용 하 여 단추 만들기](walkthrough-create-a-button-by-using-xaml.md) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 Visual Studio를 사용 하 여 사용자 지정 동작을 사용 하 여 단추를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-114">[Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6b79f-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6b79f-115">Related Sections</span></span>
 <span data-ttu-id="6b79f-116">[스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md) 스타일 및 템플릿을 사용 하 여 컨트롤의 모양과 동작을 결정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-116">[Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md) Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>

 <span data-ttu-id="6b79f-117">[애니메이션 개요](../graphics-multimedia/animation-overview.md) [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 애니메이션 및 타이밍 시스템을 사용 하 여 개체에 애니메이션 효과를 주는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-117">[Animation Overview](../graphics-multimedia/animation-overview.md) Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>

 <span data-ttu-id="6b79f-118">[단색 및 그라데이션을 사용한 그리기 개요](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) 브러시 개체를 사용 하 여 단색, 선형 그라데이션 및 방사형 그라데이션으로 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-118">[Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>

 <span data-ttu-id="6b79f-119">[비트맵 효과 개요](../graphics-multimedia/bitmap-effects-overview.md) [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 지 원하는 비트맵 효과를 설명 하 고 이러한 효과를 적용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b79f-119">[Bitmap Effects Overview](../graphics-multimedia/bitmap-effects-overview.md) Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
