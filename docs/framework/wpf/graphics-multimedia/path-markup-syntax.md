---
title: 경로 태그 구문
description: Windows Presentation Foundation (WPF)에서 압축 경로 기 하 도형을 지정 하는 데 사용할 수 있는 강력 하 고 복잡 한 미니 언어에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 6d2778522b622f0b0dcb59673e793a6d772a4b4f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853660"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="38169-103">경로 태그 구문</span><span class="sxs-lookup"><span data-stu-id="38169-103">Path Markup Syntax</span></span>
<span data-ttu-id="38169-104">경로는 WPF 개요 및 [기](geometry-overview.md)하 [도형 개요에서 도형 및 기본 그리기](shapes-and-basic-drawing-in-wpf-overview.md) 에 설명 되어 있습니다. 그러나이 항목에서는를 사용 하 여 경로 기 하 도형을 더 조밀 지정 하는 데 사용할 수 있는 강력 하 고 복잡 한 미니 언어에 대해 자세히 설명 합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38169-104">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a><span data-ttu-id="38169-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38169-105">Prerequisites</span></span>  
 <span data-ttu-id="38169-106">이 항목을 이해 하려면 개체의 기본 기능에 대해 잘 알고 있어야 합니다 <xref:System.Windows.Media.Geometry> .</span><span class="sxs-lookup"><span data-stu-id="38169-106">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="38169-107">자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38169-107">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="38169-108">StreamGeometry 및 PathFigureCollection 미니 언어</span><span class="sxs-lookup"><span data-stu-id="38169-108">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="38169-109">에서는 기하학적 경로를 설명 하는 데 사용할 미니 언어와를 제공 하는 두 가지 클래스를 제공 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection> 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-109">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
- <span data-ttu-id="38169-110"><xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.Geometry> <xref:System.Windows.UIElement.Clip%2A> 의 속성 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> <xref:System.Windows.Shapes.Path> 요소의 속성 등 형식의 속성을 설정할 때 미니 언어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-110">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="38169-111">다음 예제에서는 특성 구문을 사용 하 여를 만듭니다 <xref:System.Windows.Media.StreamGeometry> .</span><span class="sxs-lookup"><span data-stu-id="38169-111">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <span data-ttu-id="38169-112"><xref:System.Windows.Media.PathFigureCollection>의 속성을 설정할 때 미니 언어를 사용 합니다 <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="38169-112">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="38169-113">다음 예제에서는 특성 구문을 사용 하 여에 <xref:System.Windows.Media.PathFigureCollection> 대 한를 만듭니다 <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="38169-113">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="38169-114">앞의 예제에서 볼 수 있는 것처럼 두 개의 미니 언어는 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-114">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="38169-115"><xref:System.Windows.Media.PathGeometry>을 사용할 수 있는 상황에서 항상를 사용할 수 있으며, 어떤 경우에는 어떤 것을 <xref:System.Windows.Media.StreamGeometry> 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="38169-115">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="38169-116">경로를 <xref:System.Windows.Media.StreamGeometry> 만든 후 수정할 필요가 없는 경우를 사용 합니다. 경로를 수정 해야 하는 경우에는를 사용 <xref:System.Windows.Media.PathGeometry> 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-116">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="38169-117">및 개체 간의 차이점에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> [Geometry 개요](geometry-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38169-117">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="38169-118">공백에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="38169-118">A Note about White Space</span></span>  
 <span data-ttu-id="38169-119">간단히 말해서 이어지는 구문 섹션에는 단일 공백이 표시되지만 단일 공백이 표시되는 모든 위치에서 여러 개의 공백을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38169-119">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="38169-120">두 숫자는 실제로 쉼표나 공백으로 구분할 필요가 없지만 결과 문자열이 명확 하지 않은 경우에만이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-120">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="38169-121">예를 들어 `2..3` 는 실제로 두 개의 숫자 "2"입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-121">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="38169-122">".3"의 두 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-122">And ".3".</span></span> <span data-ttu-id="38169-123">마찬가지로 `2-3` 는 "2" 및 "-3"입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-123">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="38169-124">명령 앞뒤에는 공백이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-124">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="38169-125">구문</span><span class="sxs-lookup"><span data-stu-id="38169-125">Syntax</span></span>  
 <span data-ttu-id="38169-126">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대 한 특성 사용 구문은 <xref:System.Windows.Media.StreamGeometry> 선택적 <xref:System.Windows.Media.FillRule> 값과 하나 이상의 그림 설명으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38169-126">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="38169-127">StreamGeometry XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="38169-127">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="38169-128">`<`*object* *속성* `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] \*`" ... />`</span><span class="sxs-lookup"><span data-stu-id="38169-128">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="38169-129">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대 한 특성 사용 구문은 <xref:System.Windows.Media.PathFigureCollection> 하나 이상의 그림 설명으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38169-129">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="38169-130">PathFigureCollection XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="38169-130">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="38169-131">`<`*object* *속성* `="` `figureDescription` [ `figureDescription` ] \*`" ... />`</span><span class="sxs-lookup"><span data-stu-id="38169-131">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="38169-132">용어</span><span class="sxs-lookup"><span data-stu-id="38169-132">Term</span></span>|<span data-ttu-id="38169-133">Description</span><span class="sxs-lookup"><span data-stu-id="38169-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-134">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="38169-134">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-135">에서 또는을 사용 하는지 여부를 지정 합니다 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .</span><span class="sxs-lookup"><span data-stu-id="38169-135">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="38169-136">-   `F0`채우기 규칙을 지정 합니다 <xref:System.Windows.Media.FillRule.EvenOdd> .</span><span class="sxs-lookup"><span data-stu-id="38169-136">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="38169-137">-   `F1`채우기 규칙을 지정 합니다 <xref:System.Windows.Media.FillRule.Nonzero> .</span><span class="sxs-lookup"><span data-stu-id="38169-137">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="38169-138">이 명령을 생략 하면 하위 경로는 기본 동작인를 사용 합니다 <xref:System.Windows.Media.FillRule.EvenOdd> .</span><span class="sxs-lookup"><span data-stu-id="38169-138">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="38169-139">이 명령을 지정하는 경우 맨 앞에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-139">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="38169-140">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="38169-140">*figureDescription*</span></span>|<span data-ttu-id="38169-141">이동 명령, 그리기 명령 및 선택적 닫기 명령으로 구성된 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-141">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="38169-142">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="38169-142">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="38169-143">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="38169-143">*moveCommand*</span></span>|<span data-ttu-id="38169-144">그림의 시작점을 지정하는 이동 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-144">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="38169-145">[이동 명령](#themovecommand) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38169-145">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="38169-146">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="38169-146">*drawCommands*</span></span>|<span data-ttu-id="38169-147">그림의 콘텐츠를 설명하는 하나 이상의 그리기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-147">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="38169-148">[그리기 명령](#drawcommands) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38169-148">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="38169-149">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="38169-149">*closeCommand*</span></span>|<span data-ttu-id="38169-150">그림을 닫는 선택적 닫기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-150">An optional close command that closes figure.</span></span> <span data-ttu-id="38169-151">[닫기 명령](#closecommand) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38169-151">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a><span data-ttu-id="38169-152">이동 명령</span><span class="sxs-lookup"><span data-stu-id="38169-152">Move Command</span></span>  
 <span data-ttu-id="38169-153">새 그림의 시작점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-153">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="38169-154">구문</span><span class="sxs-lookup"><span data-stu-id="38169-154">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-155">`M`*startPoint* 시작점</span><span class="sxs-lookup"><span data-stu-id="38169-155">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="38169-156">또는</span><span class="sxs-lookup"><span data-stu-id="38169-156">- or -</span></span><br /><br /> <span data-ttu-id="38169-157">`m`*startPoint* 시작점</span><span class="sxs-lookup"><span data-stu-id="38169-157">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="38169-158">용어</span><span class="sxs-lookup"><span data-stu-id="38169-158">Term</span></span>|<span data-ttu-id="38169-159">Description</span><span class="sxs-lookup"><span data-stu-id="38169-159">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-160">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="38169-160">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-161">새 그림의 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-161">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="38169-162">대문자는 `M` 가 절대값 임을 나타내고, `startPoint` 소문자는 `m` `startPoint` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-162">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="38169-163">이동 명령 뒤에 여러 점을 나열하는 경우 선 명령을 지정했어도 해당 점으로 선이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="38169-163">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a><span data-ttu-id="38169-164">그리기 명령</span><span class="sxs-lookup"><span data-stu-id="38169-164">Draw Commands</span></span>  
 <span data-ttu-id="38169-165">그리기 명령은 여러 도형 명령으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-165">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="38169-166">선, 수평선, 수직선, 입방형 3차원 곡선, 정방형 3차원 곡선, 부드러운 입방형 3차원 곡선, 부드러운 정방형 3차원 곡선 및 타원형 호 등의 도형 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-166">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="38169-167">대문자 또는 소문자를 사용하여 각 명령을 입력합니다. 대문자는 절대값을 나타내고 소문자는 상대값을 나타냅니다. 해당 세그먼트에 대한 제어점은 이전 예제의 끝점을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-167">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="38169-168">동일한 형식의 명령을 두 번 이상 입력 하는 경우 중복 명령 항목을 생략할 수 있습니다. 예를 들어 `L 100,200 300,400` 는과 같습니다 `L 100,200 L 300,400` .</span><span class="sxs-lookup"><span data-stu-id="38169-168">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="38169-169">다음 표에서는 **이동** 및 **그리기** 명령에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-169">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="38169-170">선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-170">Line Command</span></span>  
 <span data-ttu-id="38169-171">현재 점과 지정된 끝점 간에 직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-171">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="38169-172">`l 20 30`및 `L 20,30` 은 올바른 **줄** 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-172">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="38169-173">구문</span><span class="sxs-lookup"><span data-stu-id="38169-173">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-174">`L`*끝점*</span><span class="sxs-lookup"><span data-stu-id="38169-174">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="38169-175">또는</span><span class="sxs-lookup"><span data-stu-id="38169-175">- or -</span></span><br /><br /> <span data-ttu-id="38169-176">`l`*끝점*</span><span class="sxs-lookup"><span data-stu-id="38169-176">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="38169-177">용어</span><span class="sxs-lookup"><span data-stu-id="38169-177">Term</span></span>|<span data-ttu-id="38169-178">Description</span><span class="sxs-lookup"><span data-stu-id="38169-178">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-179">*끝점만*</span><span class="sxs-lookup"><span data-stu-id="38169-179">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-180">선의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-180">The end point of the line.</span></span>|  

<span data-ttu-id="38169-181">대문자는 `L` 가 절대값 임을 나타내고, `endPoint` 소문자는 `l` `endPoint` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-181">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="38169-182">수평선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-182">Horizontal Line Command</span></span>  
 <span data-ttu-id="38169-183">현재 점과 지정된 x 좌표 간에 수평선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-183">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="38169-184">`H 90`은 유효한 수평선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-184">`H 90` is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="38169-185">구문</span><span class="sxs-lookup"><span data-stu-id="38169-185">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-186">`H`  *.x*</span><span class="sxs-lookup"><span data-stu-id="38169-186">`H`  *x*</span></span><br /><br /> <span data-ttu-id="38169-187">또는</span><span class="sxs-lookup"><span data-stu-id="38169-187">- or -</span></span><br /><br /> <span data-ttu-id="38169-188">`h`  *.x*</span><span class="sxs-lookup"><span data-stu-id="38169-188">`h`  *x*</span></span>|  
  
|<span data-ttu-id="38169-189">용어</span><span class="sxs-lookup"><span data-stu-id="38169-189">Term</span></span>|<span data-ttu-id="38169-190">Description</span><span class="sxs-lookup"><span data-stu-id="38169-190">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-191">*x*</span><span class="sxs-lookup"><span data-stu-id="38169-191">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-192">선 끝점의 x 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-192">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="38169-193">대문자는 `H` 가 절대값 임을 나타내고, `x` 소문자는 `h` `x` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-193">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="38169-194">수직선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-194">Vertical Line Command</span></span>  
 <span data-ttu-id="38169-195">현재 점과 지정된 y 좌표 간에 수직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-195">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="38169-196">`v 90`은 유효한 수직선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-196">`v 90` is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="38169-197">구문</span><span class="sxs-lookup"><span data-stu-id="38169-197">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-198">`V`  *x.y*</span><span class="sxs-lookup"><span data-stu-id="38169-198">`V`  *y*</span></span><br /><br /> <span data-ttu-id="38169-199">또는</span><span class="sxs-lookup"><span data-stu-id="38169-199">- or -</span></span><br /><br /> <span data-ttu-id="38169-200">`v`  *x.y*</span><span class="sxs-lookup"><span data-stu-id="38169-200">`v`  *y*</span></span>|  
  
|<span data-ttu-id="38169-201">용어</span><span class="sxs-lookup"><span data-stu-id="38169-201">Term</span></span>|<span data-ttu-id="38169-202">Description</span><span class="sxs-lookup"><span data-stu-id="38169-202">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-203">*x.y*</span><span class="sxs-lookup"><span data-stu-id="38169-203">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-204">선 끝점의 y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-204">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="38169-205">대문자는 `V` 가 절대값 임을 나타내고, `y` 소문자는 `v` `y` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-205">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  

### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="38169-206">입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-206">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="38169-207">지정 된 두 제어점 ( `controlPoint` 1과 2)을 사용 하 여 현재 점과 지정 된 끝점 간에 입방 형 3 차원 곡선을 만듭니다 `controlPoint` .</span><span class="sxs-lookup"><span data-stu-id="38169-207">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="38169-208">`C 100,200 200,400 300,200`은 유효한 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-208">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="38169-209">구문</span><span class="sxs-lookup"><span data-stu-id="38169-209">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-210">`C``controlPoint`1 `controlPoint` 2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-210">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="38169-211">또는</span><span class="sxs-lookup"><span data-stu-id="38169-211">- or -</span></span><br /><br /> <span data-ttu-id="38169-212">`c``controlPoint`1 `controlPoint` 2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-212">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="38169-213">용어</span><span class="sxs-lookup"><span data-stu-id="38169-213">Term</span></span>|<span data-ttu-id="38169-214">Description</span><span class="sxs-lookup"><span data-stu-id="38169-214">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-215">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="38169-215">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-216">곡선의 시작 접선을 결정하는 곡선의 첫 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-216">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="38169-217">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="38169-217">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-218">곡선의 끝 접선을 결정하는 곡선의 두 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-218">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-219">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-219">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="38169-220">정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-220">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="38169-221">지정 된 제어점 ()을 사용 하 여 현재 지점과 지정 된 끝점 사이에 정방형 3 차원 곡선을 만듭니다 `controlPoint` .</span><span class="sxs-lookup"><span data-stu-id="38169-221">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="38169-222">`q 100,200 300,200`은 유효한 정방형 3차원 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-222">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="38169-223">구문</span><span class="sxs-lookup"><span data-stu-id="38169-223">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-224">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-224">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="38169-225">또는</span><span class="sxs-lookup"><span data-stu-id="38169-225">- or -</span></span><br /><br /> <span data-ttu-id="38169-226">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-226">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="38169-227">용어</span><span class="sxs-lookup"><span data-stu-id="38169-227">Term</span></span>|<span data-ttu-id="38169-228">Description</span><span class="sxs-lookup"><span data-stu-id="38169-228">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-229">곡선의 시작 및 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-229">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-230">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-230">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="38169-231">부드러운 입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-231">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="38169-232">현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-232">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="38169-233">첫 번째 제어점은 현재 점을 기준으로 이전 명령의 두 번째 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="38169-233">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="38169-234">이전 명령이 없거나 이전 명령이 입방형 3차원 곡선 명령 또는 부드러운 입방 형 3차원 곡선 명령이 아닌 경우 첫 번째 제어점이 현재 점과 일치한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-234">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="38169-235">두 번째 제어점 인 곡선의 끝에 대 한 제어점은 2로 지정 됩니다 `controlPoint` .</span><span class="sxs-lookup"><span data-stu-id="38169-235">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="38169-236">예를 들어 `S 100,200 200,300` 은 유효한 부드러운 입방 형 3 차원 곡선 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-236">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="38169-237">구문</span><span class="sxs-lookup"><span data-stu-id="38169-237">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-238">`S``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-238">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="38169-239">또는</span><span class="sxs-lookup"><span data-stu-id="38169-239">- or -</span></span><br /><br /> <span data-ttu-id="38169-240">`s``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-240">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="38169-241">용어</span><span class="sxs-lookup"><span data-stu-id="38169-241">Term</span></span>|<span data-ttu-id="38169-242">Description</span><span class="sxs-lookup"><span data-stu-id="38169-242">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="38169-243">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="38169-243">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-244">곡선의 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-244">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-245">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-245">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="38169-246">부드러운 정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="38169-246">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="38169-247">현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-247">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="38169-248">제어점은 현재 점을 기준으로 이전 명령의 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="38169-248">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="38169-249">이전 명령이 없거나 이전 명령이 정방형 3차원 곡선 명령 또는 부드러운 정방 형 3차원 곡선 명령이 아닌 경우 제어점이 현재 점과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-249">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="38169-250">구문</span><span class="sxs-lookup"><span data-stu-id="38169-250">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-251">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-251">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="38169-252">또는</span><span class="sxs-lookup"><span data-stu-id="38169-252">- or -</span></span><br /><br /> <span data-ttu-id="38169-253">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-253">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="38169-254">용어</span><span class="sxs-lookup"><span data-stu-id="38169-254">Term</span></span>|<span data-ttu-id="38169-255">Description</span><span class="sxs-lookup"><span data-stu-id="38169-255">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-256">곡선의 시작 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-256">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-257">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-257">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="38169-258">타원형 호 명령</span><span class="sxs-lookup"><span data-stu-id="38169-258">Elliptical Arc Command</span></span>  
 <span data-ttu-id="38169-259">현재 점과 지정된 끝점 간에 타원형 호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-259">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="38169-260">구문</span><span class="sxs-lookup"><span data-stu-id="38169-260">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-261">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-261">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="38169-262">또는</span><span class="sxs-lookup"><span data-stu-id="38169-262">- or -</span></span><br /><br /> <span data-ttu-id="38169-263">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="38169-263">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="38169-264">용어</span><span class="sxs-lookup"><span data-stu-id="38169-264">Term</span></span>|<span data-ttu-id="38169-265">Description</span><span class="sxs-lookup"><span data-stu-id="38169-265">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-266">원호의 X 및 y 반지름입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-266">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-267">타원의 회전 각도입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-267">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="38169-268">호의 각도가 180도보다 커야 하면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-268">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="38169-269">호가 양의 각도 방향으로 그려지면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-269">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-270">호를 그리는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-270">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a><span data-ttu-id="38169-271">닫기 명령</span><span class="sxs-lookup"><span data-stu-id="38169-271">The Close Command</span></span>  
 <span data-ttu-id="38169-272">현재 그림을 끝내고 현재 점을 그림의 시작 점에 연결하는 선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-272">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="38169-273">이 명령은 그림의 마지막 세그먼트와 첫 번째 세그먼트 사이에 선 조인(모서리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38169-273">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="38169-274">구문</span><span class="sxs-lookup"><span data-stu-id="38169-274">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="38169-275">또는</span><span class="sxs-lookup"><span data-stu-id="38169-275">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a><span data-ttu-id="38169-276">점 구문</span><span class="sxs-lookup"><span data-stu-id="38169-276">Point Syntax</span></span>  
 <span data-ttu-id="38169-277">(0, 0)이 왼쪽 위 모퉁이에 있는 점의 x 좌표 및 y 좌표를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-277">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="38169-278">구문</span><span class="sxs-lookup"><span data-stu-id="38169-278">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="38169-279">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="38169-279">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="38169-280">또는</span><span class="sxs-lookup"><span data-stu-id="38169-280">- or -</span></span><br /><br /> <span data-ttu-id="38169-281">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="38169-281">`x` `y`</span></span>|  
  
|<span data-ttu-id="38169-282">용어</span><span class="sxs-lookup"><span data-stu-id="38169-282">Term</span></span>|<span data-ttu-id="38169-283">Description</span><span class="sxs-lookup"><span data-stu-id="38169-283">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-284">점의 X 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-284">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="38169-285">점의 Y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-285">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a><span data-ttu-id="38169-286">특수 값</span><span class="sxs-lookup"><span data-stu-id="38169-286">Special Values</span></span>  
 <span data-ttu-id="38169-287">표준 숫자 값 대신 다음과 같은 특수 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-287">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="38169-288">이 값은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="38169-288">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="38169-289">무한대</span><span class="sxs-lookup"><span data-stu-id="38169-289">Infinity</span></span>  
 <span data-ttu-id="38169-290"><xref:System.Double.PositiveInfinity?displayProperty=nameWithType>를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-290">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="38169-291">-Infinity</span><span class="sxs-lookup"><span data-stu-id="38169-291">-Infinity</span></span>  
 <span data-ttu-id="38169-292"><xref:System.Double.NegativeInfinity?displayProperty=nameWithType>를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-292">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="38169-293">NaN</span><span class="sxs-lookup"><span data-stu-id="38169-293">NaN</span></span>  
 <span data-ttu-id="38169-294"><xref:System.Double.NaN?displayProperty=nameWithType>를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38169-294">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="38169-295">과학적 표기법을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38169-295">You may also use scientific notation.</span></span> <span data-ttu-id="38169-296">예를 들어 `+1.e17` 는 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="38169-296">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38169-297">참조</span><span class="sxs-lookup"><span data-stu-id="38169-297">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="38169-298">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="38169-298">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="38169-299">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="38169-299">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="38169-300">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="38169-300">How-to Topics</span></span>](geometries-how-to-topics.md)
