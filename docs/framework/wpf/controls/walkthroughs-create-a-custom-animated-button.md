---
title: '연습: 사용자 지정 애니메이션된 단추 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 3c601641a0eb1024722b4f449f0ab23e54fe93dd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357211"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="79809-102">연습: 사용자 지정 애니메이션된 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="79809-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="79809-103">해당 이름에서 알 수 있듯이, Windows Presentation Foundation (WPF) 고객에 대 한 풍부한 기능의 프레젠테이션 경험 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="79809-104">이러한 연습은 모양과 동작 (애니메이션 포함) 단추를 사용자 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79809-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="79809-105">이 사용자 지정이 이루어집니다 사용 된 스타일 및 템플릿 수 있으므로 응용 프로그램에서 모든 단추에이 사용자 지정 단추를 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79809-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="79809-106">다음 그림에서는 만들려는 사용자 지정된 단추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79809-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="79809-107">![사용자가 만든 사용자 지정된 단추](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="79809-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="79809-108">단추의 모양을 구성 하는 벡터 그래픽을 사용 하 여 만들어진 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="79809-109">것이 더 강력 하 고 확장할 수 있는 점을 제외 하 고 HTML 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="79809-110">Microsoft Visual Studio 또는 메모장을 사용 하 여 수동으로 입력할 수 있습니다 또는 Microsoft Expression Blend와 같은 비주얼 디자인 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79809-110">can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="79809-111">Expression Blend 기본 만들어 작동 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 두 메서드 모두 동일한 그래픽을 만들 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="79809-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79809-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="79809-112">In This Section</span></span>  
 [<span data-ttu-id="79809-113">Microsoft Expression Blend를 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="79809-113">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="79809-114">Expression Blend의 디자이너 기능을 사용 하 여 사용자 지정 동작을 사용 하 여 단추를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79809-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="79809-115">XAML을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="79809-115">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="79809-116">사용 하 여 사용자 지정 동작을 사용 하 여 단추를 만드는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 Visual Studio입니다.</span><span class="sxs-lookup"><span data-stu-id="79809-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="79809-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="79809-117">Related Sections</span></span>  
 [<span data-ttu-id="79809-118">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="79809-118">Styling and Templating</span></span>](styling-and-templating.md)  
 <span data-ttu-id="79809-119">컨트롤의 동작과 모양을 결정할 스타일 및 템플릿 수 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="79809-120">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="79809-120">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="79809-121">개체를 사용 하 여 애니메이션 수는 방법에 대해 설명 합니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 애니메이션 및 타이밍 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="79809-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="79809-122">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="79809-122">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="79809-123">단색, 선형 그라데이션 및 방사형 그라데이션으로 그리는 브러시 개체를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="79809-124">비트맵 효과 개요</span><span class="sxs-lookup"><span data-stu-id="79809-124">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="79809-125">지원 되는 비트맵 효과 설명 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 적용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79809-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
