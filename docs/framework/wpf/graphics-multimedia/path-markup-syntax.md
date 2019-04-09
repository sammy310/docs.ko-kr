---
title: 경로 태그 구문
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 32eefba26b5e04370599e4c97767b6662cfd1c13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082492"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="f9d54-102">경로 태그 구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-102">Path Markup Syntax</span></span>
<span data-ttu-id="f9d54-103">그러나 경로에 대해서는 [에서 Shape 및 기본 그리기 개요 WPF](shapes-and-basic-drawing-in-wpf-overview.md) 하며 [기 하 도형 개요](geometry-overview.md),이 항목에서는 설명 세부 정보에서 경로 지정 하 여 강력 하 고 복잡 한 미니 언어 기 하 도형 보다 조밀 하 게 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a><span data-ttu-id="f9d54-104">전제 조건</span><span class="sxs-lookup"><span data-stu-id="f9d54-104">Prerequisites</span></span>  
 <span data-ttu-id="f9d54-105">이 항목을 이해 하려면의 기본 기능을 잘 알고 있어야 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="f9d54-106">자세한 내용은 참조는 [기 하 도형 개요](geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-106">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="f9d54-107">StreamGeometry 및 PathFigureCollection 미니 언어</span><span class="sxs-lookup"><span data-stu-id="f9d54-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="f9d54-108">기하학적 경로 설명 하는 미니 언어를 제공 하는 두 개의 클래스를 제공 합니다. <xref:System.Windows.Media.StreamGeometry> 고 <xref:System.Windows.Media.PathFigureCollection>입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-108">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
-   <span data-ttu-id="f9d54-109">사용할를 <xref:System.Windows.Media.StreamGeometry> 미니 언어 형식의 속성을 설정할 때 <xref:System.Windows.Media.Geometry>와 같은 <xref:System.Windows.UIElement.Clip%2A> 의 속성을 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 <xref:System.Windows.Shapes.Path> 요소.</span><span class="sxs-lookup"><span data-stu-id="f9d54-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="f9d54-110">다음 예제에서는 특성 구문을 사용 하 여를 <xref:System.Windows.Media.StreamGeometry>입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   <span data-ttu-id="f9d54-111">사용할 합니다 <xref:System.Windows.Media.PathFigureCollection> 미니 언어를 설정 하는 경우는 <xref:System.Windows.Media.PathGeometry.Figures%2A> 의 속성을 <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="f9d54-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f9d54-112">다음 예제는 특성 구문을 사용 하 여는 <xref:System.Windows.Media.PathFigureCollection> 에 대 한는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="f9d54-113">앞의 예제에서 볼 수 있는 것처럼 두 개의 미니 언어는 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="f9d54-114">사용할 수는 항상을 <xref:System.Windows.Media.PathGeometry> 를 사용할 수 있는 상황에서는 <xref:System.Windows.Media.StreamGeometry>; 따라서 사용 해야 하는?</span><span class="sxs-lookup"><span data-stu-id="f9d54-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="f9d54-115">사용 하 여는 <xref:System.Windows.Media.StreamGeometry> 사용 하 여, 만든 후 경로 수정할 필요가 없는 경우는 <xref:System.Windows.Media.PathGeometry> 경로를 수정 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="f9d54-116">간의 차이점에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 개체를 참조 합니다 [기 하 도형 개요](geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="f9d54-117">공백에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="f9d54-117">A Note about White Space</span></span>  
 <span data-ttu-id="f9d54-118">간단히 말해서 이어지는 구문 섹션에는 단일 공백이 표시되지만 단일 공백이 표시되는 모든 위치에서 여러 개의 공백을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="f9d54-119">두 숫자 실제로 쉼표나 공백을 구분 없지만 이렇게 하면 결과 문자열이 모호 하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-119">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="f9d54-120">예를 들어 `2..3` 은 실제로: "2."</span><span class="sxs-lookup"><span data-stu-id="f9d54-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="f9d54-121">".3"의 두 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-121">And ".3".</span></span> <span data-ttu-id="f9d54-122">마찬가지로, `2-3` 은 "2"와 "-3".</span><span class="sxs-lookup"><span data-stu-id="f9d54-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="f9d54-123">명령 앞뒤에는 공백이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="f9d54-124">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-124">Syntax</span></span>  
 <span data-ttu-id="f9d54-125">합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.StreamGeometry> 선택적으로 구성 됩니다 <xref:System.Windows.Media.FillRule> 값 및 하나 이상의 그림 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="f9d54-126">StreamGeometry XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="f9d54-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|`<` <span data-ttu-id="f9d54-127">*object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\*</span><span class="sxs-lookup"><span data-stu-id="f9d54-127">*object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\*</span></span> `" ... />`|  
  
 <span data-ttu-id="f9d54-128">합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.PathFigureCollection> 하나 이상의 그림 설명으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="f9d54-129">PathFigureCollection XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="f9d54-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|`<` <span data-ttu-id="f9d54-130">*object* *property* `="` `figureDescription`[ `figureDescription`]\*</span><span class="sxs-lookup"><span data-stu-id="f9d54-130">*object* *property* `="` `figureDescription`[ `figureDescription`]\*</span></span> `" ... />`|  
  
|<span data-ttu-id="f9d54-131">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-131">Term</span></span>|<span data-ttu-id="f9d54-132">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-132">Description</span></span>|  
|----------|-----------------|  
|*<span data-ttu-id="f9d54-133">fillRule</span><span class="sxs-lookup"><span data-stu-id="f9d54-133">fillRule</span></span>*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-134">지정 여부를 <xref:System.Windows.Media.StreamGeometry> 사용 하는 <xref:System.Windows.Media.FillRule.EvenOdd> 또는 <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="f9d54-135">-   `F0` 지정 된 <xref:System.Windows.Media.FillRule.EvenOdd> 채우기 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="f9d54-136">-   `F1` 지정 된 <xref:System.Windows.Media.FillRule.Nonzero> 채우기 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="f9d54-137">하위 경로 기본 동작을 사용 하 여이 명령을 생략 <xref:System.Windows.Media.FillRule.EvenOdd>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="f9d54-138">이 명령을 지정하는 경우 맨 앞에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-138">If you specify this command, you must place it first.</span></span>|  
|*<span data-ttu-id="f9d54-139">figureDescription</span><span class="sxs-lookup"><span data-stu-id="f9d54-139">figureDescription</span></span>*|<span data-ttu-id="f9d54-140">이동 명령, 그리기 명령 및 선택적 닫기 명령으로 구성된 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*<span data-ttu-id="f9d54-141">moveCommand</span><span class="sxs-lookup"><span data-stu-id="f9d54-141">moveCommand</span></span>*|<span data-ttu-id="f9d54-142">그림의 시작점을 지정하는 이동 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-142">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="f9d54-143">참조 된 [이동 명령](#themovecommand) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-143">See the [Move Command](#themovecommand) section.</span></span>|  
|*<span data-ttu-id="f9d54-144">drawCommands</span><span class="sxs-lookup"><span data-stu-id="f9d54-144">drawCommands</span></span>*|<span data-ttu-id="f9d54-145">그림의 콘텐츠를 설명하는 하나 이상의 그리기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-145">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="f9d54-146">참조 된 [그리기 명령](#drawcommands) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-146">See the [Draw Commands](#drawcommands) section.</span></span>|  
|*<span data-ttu-id="f9d54-147">closeCommand</span><span class="sxs-lookup"><span data-stu-id="f9d54-147">closeCommand</span></span>*|<span data-ttu-id="f9d54-148">그림을 닫는 선택적 닫기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-148">An optional close command that closes figure.</span></span> <span data-ttu-id="f9d54-149">참조 된 [닫기 명령](#closecommand) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-149">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a><span data-ttu-id="f9d54-150">이동 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-150">Move Command</span></span>  
 <span data-ttu-id="f9d54-151">새 그림의 시작점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-151">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="f9d54-152">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-152">Syntax</span></span>|  
|------------|  
|`M` *<span data-ttu-id="f9d54-153">startPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-153">startPoint</span></span>*<br /><br /> <span data-ttu-id="f9d54-154">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-154">- or -</span></span><br /><br /> `m` *<span data-ttu-id="f9d54-155">startPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-155">startPoint</span></span>*|  
  
|<span data-ttu-id="f9d54-156">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-156">Term</span></span>|<span data-ttu-id="f9d54-157">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-157">Description</span></span>|  
|----------|-----------------|  
|*<span data-ttu-id="f9d54-158">startPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-158">startPoint</span></span>*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-159">새 그림의 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-159">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="f9d54-160">대문자 `M` 나타냅니다 `startPoint` 절대 값인지; 소문자 `m` 나타냅니다 `startPoint` 오프셋을 이전 지점으로 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-160">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="f9d54-161">이동 명령 뒤에 여러 점을 나열하는 경우 선 명령을 지정했어도 해당 점으로 선이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-161">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a><span data-ttu-id="f9d54-162">그리기 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-162">Draw Commands</span></span>  
 <span data-ttu-id="f9d54-163">그리기 명령은 여러 도형 명령으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-163">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="f9d54-164">선, 수평선, 수직선, 입방형 3차원 곡선, 정방형 3차원 곡선, 부드러운 입방형 3차원 곡선, 부드러운 정방형 3차원 곡선 및 타원형 호 등의 도형 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-164">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="f9d54-165">대문자 또는 소문자를 사용하여 각 명령을 입력합니다. 대문자는 절대값을 나타내고 소문자는 상대값을 나타냅니다. 해당 세그먼트에 대한 제어점은 이전 예제의 끝점을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-165">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="f9d54-166">동일한 형식의 둘 이상의 명령이 순차적으로 입력할 때에 중복 되는 명령 출품작을 생략할 수 있습니다. 예를 들어 `L 100,200 300,400` 같습니다 `L 100,200 L 300,400`합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-166">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="f9d54-167">다음 표에 **이동** 및 **그리기** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-167">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="f9d54-168">선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-168">Line Command</span></span>  
 <span data-ttu-id="f9d54-169">현재 점과 지정된 끝점 간에 직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-169">Creates a straight line between the current point and the specified end point.</span></span> `l 20 30` <span data-ttu-id="f9d54-170">및 `L 20,30` 은 유효한 예제 **줄** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-170">and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="f9d54-171">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-171">Syntax</span></span>|  
|------------|  
|`L` *<span data-ttu-id="f9d54-172">endPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-172">endPoint</span></span>*<br /><br /> <span data-ttu-id="f9d54-173">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-173">- or -</span></span><br /><br /> `l` *<span data-ttu-id="f9d54-174">endPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-174">endPoint</span></span>*|  
  
|<span data-ttu-id="f9d54-175">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-175">Term</span></span>|<span data-ttu-id="f9d54-176">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-176">Description</span></span>|  
|----------|-----------------|  
|*<span data-ttu-id="f9d54-177">endPoint</span><span class="sxs-lookup"><span data-stu-id="f9d54-177">endPoint</span></span>*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-178">선의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-178">The end point of the line.</span></span>|  

<span data-ttu-id="f9d54-179">대문자 `L` 나타냅니다 `endPoint` 절대 값인지; 소문자 `l` 나타냅니다 `endPoint` 오프셋을 이전 지점으로 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-179">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="f9d54-180">수평선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-180">Horizontal Line Command</span></span>  
 <span data-ttu-id="f9d54-181">현재 점과 지정된 x 좌표 간에 수평선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-181">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> `H 90` <span data-ttu-id="f9d54-182">유효한 수평선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-182">is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="f9d54-183">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-183">Syntax</span></span>|  
|------------|  
|`H`  *<span data-ttu-id="f9d54-184">x</span><span class="sxs-lookup"><span data-stu-id="f9d54-184">x</span></span>*<br /><br /> <span data-ttu-id="f9d54-185">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-185">- or -</span></span><br /><br /> `h`  *<span data-ttu-id="f9d54-186">x</span><span class="sxs-lookup"><span data-stu-id="f9d54-186">x</span></span>*|  
  
|<span data-ttu-id="f9d54-187">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-187">Term</span></span>|<span data-ttu-id="f9d54-188">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-188">Description</span></span>|  
|----------|-----------------|  
|*<span data-ttu-id="f9d54-189">x</span><span class="sxs-lookup"><span data-stu-id="f9d54-189">x</span></span>*|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-190">선 끝점의 x 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-190">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="f9d54-191">대문자 `H` 나타냅니다 `x` 절대 값인지; 소문자 `h` 나타냅니다 `x` 오프셋을 이전 지점으로 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-191">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="f9d54-192">수직선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-192">Vertical Line Command</span></span>  
 <span data-ttu-id="f9d54-193">현재 점과 지정된 y 좌표 간에 수직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-193">Creates a vertical line between the current point and the specified y-coordinate.</span></span> `v 90` <span data-ttu-id="f9d54-194">유효한 수직선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-194">is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="f9d54-195">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-195">Syntax</span></span>|  
|------------|  
|`V`  *<span data-ttu-id="f9d54-196">y</span><span class="sxs-lookup"><span data-stu-id="f9d54-196">y</span></span>*<br /><br /> <span data-ttu-id="f9d54-197">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-197">- or -</span></span><br /><br /> `v`  *<span data-ttu-id="f9d54-198">y</span><span class="sxs-lookup"><span data-stu-id="f9d54-198">y</span></span>*|  
  
|<span data-ttu-id="f9d54-199">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-199">Term</span></span>|<span data-ttu-id="f9d54-200">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-200">Description</span></span>|  
|----------|-----------------|  
|*<span data-ttu-id="f9d54-201">y</span><span class="sxs-lookup"><span data-stu-id="f9d54-201">y</span></span>*|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-202">선 끝점의 y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-202">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="f9d54-203">대문자 `V` 나타냅니다 `y` 절대 값인지; 소문자 `v` 나타냅니다 `y` 오프셋을 이전 지점으로 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="f9d54-203">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  
    
### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="f9d54-204">입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-204">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="f9d54-205">지정한 두 개의 제어점을 사용 하 여 현재 점과 지정 된 끝점 간에 입방 형 3 차원 곡선을 만듭니다 (`controlPoint`1 및 `controlPoint`2).</span><span class="sxs-lookup"><span data-stu-id="f9d54-205">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> `C 100,200 200,400 300,200` <span data-ttu-id="f9d54-206">유효한 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-206">is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="f9d54-207">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-207">Syntax</span></span>|  
|------------|  
|`C` `controlPoint`<span data-ttu-id="f9d54-208">1`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="f9d54-208">1`controlPoint`2</span></span>`endPoint`<br /><br /> <span data-ttu-id="f9d54-209">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-209">- or -</span></span><br /><br /> `c` `controlPoint`<span data-ttu-id="f9d54-210">1`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="f9d54-210">1`controlPoint`2</span></span>`endPoint`|  
  
|<span data-ttu-id="f9d54-211">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-211">Term</span></span>|<span data-ttu-id="f9d54-212">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-212">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`<span data-ttu-id="f9d54-213">1</span><span class="sxs-lookup"><span data-stu-id="f9d54-213">1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-214">곡선의 시작 접선을 결정하는 곡선의 첫 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-214">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|`controlPoint`<span data-ttu-id="f9d54-215">2</span><span class="sxs-lookup"><span data-stu-id="f9d54-215">2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-216">곡선의 끝 접선을 결정하는 곡선의 두 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-216">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-217">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-217">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="f9d54-218">정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-218">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="f9d54-219">지정 된 제어점을 사용 하 여 현재 점과 지정 된 끝점 간에 정방형 베 지 어 곡선을 만듭니다 (`controlPoint`).</span><span class="sxs-lookup"><span data-stu-id="f9d54-219">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> `q 100,200 300,200` <span data-ttu-id="f9d54-220">유효한 정방형 3 차원 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-220">is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="f9d54-221">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-221">Syntax</span></span>|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> <span data-ttu-id="f9d54-222">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-222">- or -</span></span><br /><br /> `q` `controlPoint` `endPoint`|  
  
|<span data-ttu-id="f9d54-223">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-223">Term</span></span>|<span data-ttu-id="f9d54-224">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-224">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-225">곡선의 시작 및 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-225">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-226">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-226">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="f9d54-227">부드러운 입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-227">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="f9d54-228">현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-228">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="f9d54-229">첫 번째 제어점은 현재 점을 기준으로 이전 명령의 두 번째 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-229">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="f9d54-230">이전 명령이 없거나 이전 명령이 입방형 3차원 곡선 명령 또는 부드러운 입방 형 3차원 곡선 명령이 아닌 경우 첫 번째 제어점이 현재 점과 일치한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-230">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="f9d54-231">두 번째 제어점을 곡선의 끝에 대 한 제어점 된 `controlPoint`2입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-231">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="f9d54-232">예를 들어 `S 100,200 200,300` 은 유효한 부드러운 입방 형 3 차원 곡선 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-232">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="f9d54-233">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-233">Syntax</span></span>|  
|------------|  
|`S` `controlPoint`<span data-ttu-id="f9d54-234">2</span><span class="sxs-lookup"><span data-stu-id="f9d54-234">2</span></span>`endPoint`<br /><br /> <span data-ttu-id="f9d54-235">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-235">- or -</span></span><br /><br /> `s` `controlPoint`<span data-ttu-id="f9d54-236">2</span><span class="sxs-lookup"><span data-stu-id="f9d54-236">2</span></span>`endPoint`|  
  
|<span data-ttu-id="f9d54-237">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-237">Term</span></span>|<span data-ttu-id="f9d54-238">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-238">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`<span data-ttu-id="f9d54-239">2</span><span class="sxs-lookup"><span data-stu-id="f9d54-239">2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-240">곡선의 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-240">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-241">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-241">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="f9d54-242">부드러운 정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-242">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="f9d54-243">현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-243">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="f9d54-244">제어점은 현재 점을 기준으로 이전 명령의 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-244">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="f9d54-245">이전 명령이 없거나 이전 명령이 정방형 3차원 곡선 명령 또는 부드러운 정방 형 3차원 곡선 명령이 아닌 경우 제어점이 현재 점과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-245">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="f9d54-246">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-246">Syntax</span></span>|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> <span data-ttu-id="f9d54-247">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-247">- or -</span></span><br /><br /> `t` `controlPoint` `endPoint`|  
  
|<span data-ttu-id="f9d54-248">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-248">Term</span></span>|<span data-ttu-id="f9d54-249">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-249">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-250">곡선의 시작 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-250">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-251">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-251">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="f9d54-252">타원형 호 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-252">Elliptical Arc Command</span></span>  
 <span data-ttu-id="f9d54-253">현재 점과 지정된 끝점 간에 타원형 호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-253">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="f9d54-254">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-254">Syntax</span></span>|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> <span data-ttu-id="f9d54-255">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-255">- or -</span></span><br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|<span data-ttu-id="f9d54-256">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-256">Term</span></span>|<span data-ttu-id="f9d54-257">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-257">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-258">원호의 X 및 y 반지름입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-258">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-259">타원의 회전 각도입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-259">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="f9d54-260">호의 각도가 180도보다 커야 하면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-260">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="f9d54-261">호가 양의 각도 방향으로 그려지면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-261">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-262">호를 그리는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-262">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a><span data-ttu-id="f9d54-263">닫기 명령</span><span class="sxs-lookup"><span data-stu-id="f9d54-263">The Close Command</span></span>  
 <span data-ttu-id="f9d54-264">현재 그림을 끝내고 현재 점을 그림의 시작 점에 연결하는 선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-264">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="f9d54-265">이 명령은 그림의 마지막 세그먼트와 첫 번째 세그먼트 사이에 선 조인(모서리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-265">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="f9d54-266">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-266">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="f9d54-267">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-267">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a><span data-ttu-id="f9d54-268">점 구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-268">Point Syntax</span></span>  
 <span data-ttu-id="f9d54-269">점의 x 및 y 좌표를 설명 합니다. 위치 (0, 0)는 왼쪽된 위 모퉁이.</span><span class="sxs-lookup"><span data-stu-id="f9d54-269">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="f9d54-270">구문</span><span class="sxs-lookup"><span data-stu-id="f9d54-270">Syntax</span></span>|  
|------------|  
|`x` `,` `y`<br /><br /> <span data-ttu-id="f9d54-271">또는</span><span class="sxs-lookup"><span data-stu-id="f9d54-271">- or -</span></span><br /><br /> `x` `y`|  
  
|<span data-ttu-id="f9d54-272">용어</span><span class="sxs-lookup"><span data-stu-id="f9d54-272">Term</span></span>|<span data-ttu-id="f9d54-273">설명</span><span class="sxs-lookup"><span data-stu-id="f9d54-273">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-274">점의 X 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-274">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="f9d54-275">점의 Y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-275">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a><span data-ttu-id="f9d54-276">특수 값</span><span class="sxs-lookup"><span data-stu-id="f9d54-276">Special Values</span></span>  
 <span data-ttu-id="f9d54-277">표준 숫자 값 대신 다음과 같은 특수 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-277">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="f9d54-278">이러한 값은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-278">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="f9d54-279">Infinity</span><span class="sxs-lookup"><span data-stu-id="f9d54-279">Infinity</span></span>  
 <span data-ttu-id="f9d54-280">나타내는 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-280">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f9d54-281">-Infinity</span><span class="sxs-lookup"><span data-stu-id="f9d54-281">-Infinity</span></span>  
 <span data-ttu-id="f9d54-282">나타내는 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-282">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f9d54-283">NaN</span><span class="sxs-lookup"><span data-stu-id="f9d54-283">NaN</span></span>  
 <span data-ttu-id="f9d54-284">나타내는 <xref:System.Double.NaN?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-284">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f9d54-285">과학적 표기법을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-285">You may also use scientific notation.</span></span> <span data-ttu-id="f9d54-286">예를 들어 `+1.e17` 은 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d54-286">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d54-287">참고자료</span><span class="sxs-lookup"><span data-stu-id="f9d54-287">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="f9d54-288">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="f9d54-288">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="f9d54-289">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="f9d54-289">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="f9d54-290">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f9d54-290">How-to Topics</span></span>](geometries-how-to-topics.md)
