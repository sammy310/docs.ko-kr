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
# <a name="path-markup-syntax"></a>경로 태그 구문
경로는 WPF 개요 및 [기](geometry-overview.md)하 [도형 개요에서 도형 및 기본 그리기](shapes-and-basic-drawing-in-wpf-overview.md) 에 설명 되어 있습니다. 그러나이 항목에서는를 사용 하 여 경로 기 하 도형을 더 조밀 지정 하는 데 사용할 수 있는 강력 하 고 복잡 한 미니 언어에 대해 자세히 설명 합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>사전 요구 사항  
 이 항목을 이해 하려면 개체의 기본 기능에 대해 잘 알고 있어야 합니다 <xref:System.Windows.Media.Geometry> . 자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry 및 PathFigureCollection 미니 언어  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 기하학적 경로를 설명 하는 데 사용할 미니 언어와를 제공 하는 두 가지 클래스를 제공 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection> 합니다.  
  
- <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.Geometry> <xref:System.Windows.UIElement.Clip%2A> 의 속성 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> <xref:System.Windows.Shapes.Path> 요소의 속성 등 형식의 속성을 설정할 때 미니 언어를 사용 합니다. 다음 예제에서는 특성 구문을 사용 하 여를 만듭니다 <xref:System.Windows.Media.StreamGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <xref:System.Windows.Media.PathFigureCollection>의 속성을 설정할 때 미니 언어를 사용 합니다 <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry> . 다음 예제에서는 특성 구문을 사용 하 여에 <xref:System.Windows.Media.PathFigureCollection> 대 한를 만듭니다 <xref:System.Windows.Media.PathGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 앞의 예제에서 볼 수 있는 것처럼 두 개의 미니 언어는 매우 비슷합니다. <xref:System.Windows.Media.PathGeometry>을 사용할 수 있는 상황에서 항상를 사용할 수 있으며, 어떤 경우에는 어떤 것을 <xref:System.Windows.Media.StreamGeometry> 사용 해야 하나요? 경로를 <xref:System.Windows.Media.StreamGeometry> 만든 후 수정할 필요가 없는 경우를 사용 합니다. 경로를 수정 해야 하는 경우에는를 사용 <xref:System.Windows.Media.PathGeometry> 합니다.  
  
 및 개체 간의 차이점에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> [Geometry 개요](geometry-overview.md)를 참조 하세요.  
  
### <a name="a-note-about-white-space"></a>공백에 대한 참고 사항  
 간단히 말해서 이어지는 구문 섹션에는 단일 공백이 표시되지만 단일 공백이 표시되는 모든 위치에서 여러 개의 공백을 사용해도 됩니다.  
  
 두 숫자는 실제로 쉼표나 공백으로 구분할 필요가 없지만 결과 문자열이 명확 하지 않은 경우에만이 작업을 수행할 수 있습니다. 예를 들어 `2..3` 는 실제로 두 개의 숫자 "2"입니다. ".3"의 두 숫자입니다. 마찬가지로 `2-3` 는 "2" 및 "-3"입니다. 명령 앞뒤에는 공백이 필요하지 않습니다.  
  
### <a name="syntax"></a>구문  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대 한 특성 사용 구문은 <xref:System.Windows.Media.StreamGeometry> 선택적 <xref:System.Windows.Media.FillRule> 값과 하나 이상의 그림 설명으로 구성 됩니다.  
  
|StreamGeometry XAML 특성 사용|  
|-----------------------------------------|  
|`<`*object* *속성* `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대 한 특성 사용 구문은 <xref:System.Windows.Media.PathFigureCollection> 하나 이상의 그림 설명으로 구성 됩니다.  
  
|PathFigureCollection XAML 특성 사용|  
|-----------------------------------------------|  
|`<`*object* *속성* `="` `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
|용어|Description|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> 에서 또는을 사용 하는지 여부를 지정 합니다 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .<br /><br /> -   `F0`채우기 규칙을 지정 합니다 <xref:System.Windows.Media.FillRule.EvenOdd> .<br />-   `F1`채우기 규칙을 지정 합니다 <xref:System.Windows.Media.FillRule.Nonzero> .<br /><br /> 이 명령을 생략 하면 하위 경로는 기본 동작인를 사용 합니다 <xref:System.Windows.Media.FillRule.EvenOdd> . 이 명령을 지정하는 경우 맨 앞에 배치해야 합니다.|  
|*figureDescription*|이동 명령, 그리기 명령 및 선택적 닫기 명령으로 구성된 그림입니다.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|그림의 시작점을 지정하는 이동 명령입니다. [이동 명령](#themovecommand) 섹션을 참조 하세요.|  
|*drawCommands*|그림의 콘텐츠를 설명하는 하나 이상의 그리기 명령입니다. [그리기 명령](#drawcommands) 섹션을 참조 하세요.|  
|*closeCommand*|그림을 닫는 선택적 닫기 명령입니다. [닫기 명령](#closecommand) 섹션을 참조 하세요.|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>이동 명령  
 새 그림의 시작점을 지정합니다.  
  
|구문|  
|------------|  
|`M`*startPoint* 시작점<br /><br /> 또는<br /><br /> `m`*startPoint* 시작점|  
  
|용어|Description|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 새 그림의 시작점입니다.|  
  
 대문자는 `M` 가 절대값 임을 나타내고, `startPoint` 소문자는 `m` `startPoint` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다. 이동 명령 뒤에 여러 점을 나열하는 경우 선 명령을 지정했어도 해당 점으로 선이 그려집니다.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>그리기 명령  
 그리기 명령은 여러 도형 명령으로 구성될 수 있습니다. 선, 수평선, 수직선, 입방형 3차원 곡선, 정방형 3차원 곡선, 부드러운 입방형 3차원 곡선, 부드러운 정방형 3차원 곡선 및 타원형 호 등의 도형 명령을 사용할 수 있습니다.  
  
 대문자 또는 소문자를 사용하여 각 명령을 입력합니다. 대문자는 절대값을 나타내고 소문자는 상대값을 나타냅니다. 해당 세그먼트에 대한 제어점은 이전 예제의 끝점을 기준으로 합니다. 동일한 형식의 명령을 두 번 이상 입력 하는 경우 중복 명령 항목을 생략할 수 있습니다. 예를 들어 `L 100,200 300,400` 는과 같습니다 `L 100,200 L 300,400` . 다음 표에서는 **이동** 및 **그리기** 명령에 대해 설명 합니다.  
  
### <a name="line-command"></a>선 명령  
 현재 점과 지정된 끝점 간에 직선을 만듭니다. `l 20 30`및 `L 20,30` 은 올바른 **줄** 명령의 예입니다.  
  
|구문|  
|------------|  
|`L`*끝점*<br /><br /> 또는<br /><br /> `l`*끝점*|  
  
|용어|Description|  
|----------|-----------------|  
|*끝점만*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 선의 끝점입니다.|  

대문자는 `L` 가 절대값 임을 나타내고, `endPoint` 소문자는 `l` `endPoint` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.

### <a name="horizontal-line-command"></a>수평선 명령  
 현재 점과 지정된 x 좌표 간에 수평선을 만듭니다. `H 90`은 유효한 수평선 명령의 예입니다.

|구문|  
|------------|  
|`H`  *.x*<br /><br /> 또는<br /><br /> `h`  *.x*|  
  
|용어|Description|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> 선 끝점의 x 좌표입니다.|  
  
대문자는 `H` 가 절대값 임을 나타내고, `x` 소문자는 `h` `x` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.
  
### <a name="vertical-line-command"></a>수직선 명령  
 현재 점과 지정된 y 좌표 간에 수직선을 만듭니다. `v 90`은 유효한 수직선 명령의 예입니다.

|구문|  
|------------|  
|`V`  *x.y*<br /><br /> 또는<br /><br /> `v`  *x.y*|  
  
|용어|Description|  
|----------|-----------------|  
|*x.y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> 선 끝점의 y 좌표입니다.|  

대문자는 `V` 가 절대값 임을 나타내고, `y` 소문자는 `v` `y` 가 이전 지점에 대 한 오프셋 임을 나타내고, 값이 없는 경우 (0, 0)을 나타냅니다.  

### <a name="cubic-bezier-curve-command"></a>입방형 3차원 곡선 명령  
 지정 된 두 제어점 ( `controlPoint` 1과 2)을 사용 하 여 현재 점과 지정 된 끝점 간에 입방 형 3 차원 곡선을 만듭니다 `controlPoint` . `C 100,200 200,400 300,200`은 유효한 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`C``controlPoint`1 `controlPoint` 2`endPoint`<br /><br /> 또는<br /><br /> `c``controlPoint`1 `controlPoint` 2`endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 접선을 결정하는 곡선의 첫 번째 제어점입니다.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 끝 접선을 결정하는 곡선의 두 번째 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="quadratic-bezier-curve-command"></a>정방형 3차원 곡선 명령  
 지정 된 제어점 ()을 사용 하 여 현재 지점과 지정 된 끝점 사이에 정방형 3 차원 곡선을 만듭니다 `controlPoint` . `q 100,200 300,200`은 유효한 정방형 3차원 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> 또는<br /><br /> `q` `controlPoint` `endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 및 끝 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>부드러운 입방형 3차원 곡선 명령  
 현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다. 첫 번째 제어점은 현재 점을 기준으로 이전 명령의 두 번째 제어점의 리플렉션으로 간주됩니다. 이전 명령이 없거나 이전 명령이 입방형 3차원 곡선 명령 또는 부드러운 입방 형 3차원 곡선 명령이 아닌 경우 첫 번째 제어점이 현재 점과 일치한다고 가정합니다. 두 번째 제어점 인 곡선의 끝에 대 한 제어점은 2로 지정 됩니다 `controlPoint` . 예를 들어 `S 100,200 200,300` 은 유효한 부드러운 입방 형 3 차원 곡선 명령입니다.  
  
|구문|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> 또는<br /><br /> `s``controlPoint`2`endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 끝 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>부드러운 정방형 3차원 곡선 명령  
 현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다. 제어점은 현재 점을 기준으로 이전 명령의 제어점의 리플렉션으로 간주됩니다. 이전 명령이 없거나 이전 명령이 정방형 3차원 곡선 명령 또는 부드러운 정방 형 3차원 곡선 명령이 아닌 경우 제어점이 현재 점과 일치합니다.  
  
|구문|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> 또는<br /><br /> `t` `controlPoint` `endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="elliptical-arc-command"></a>타원형 호 명령  
 현재 점과 지정된 끝점 간에 타원형 호를 만듭니다.  
  
|구문|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> 또는<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> 원호의 X 및 y 반지름입니다.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> 타원의 회전 각도입니다.|  
|`isLargeArcFlag`|호의 각도가 180도보다 커야 하면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.|  
|`sweepDirectionFlag`|호가 양의 각도 방향으로 그려지면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 호를 그리는 점입니다.|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a>닫기 명령  
 현재 그림을 끝내고 현재 점을 그림의 시작 점에 연결하는 선을 만듭니다. 이 명령은 그림의 마지막 세그먼트와 첫 번째 세그먼트 사이에 선 조인(모서리)을 만듭니다.  
  
|구문|  
|------------|  
|`Z`<br /><br /> 또는<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>점 구문  
 (0, 0)이 왼쪽 위 모퉁이에 있는 점의 x 좌표 및 y 좌표를 설명 합니다.
  
|구문|  
|------------|  
|`x` `,` `y`<br /><br /> 또는<br /><br /> `x` `y`|  
  
|용어|Description|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> 점의 X 좌표입니다.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> 점의 Y 좌표입니다.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>특수 값  
 표준 숫자 값 대신 다음과 같은 특수 값을 사용할 수도 있습니다. 이 값은 대/소문자를 구분합니다.  
  
 무한대  
 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>를 나타냅니다.  
  
 -Infinity  
 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>를 나타냅니다.  
  
 NaN  
 <xref:System.Double.NaN?displayProperty=nameWithType>를 나타냅니다.  
  
 과학적 표기법을 사용할 수도 있습니다. 예를 들어 `+1.e17` 는 유효한 값입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [Geometry 개요](geometry-overview.md)
- [방법 도움말 항목](geometries-how-to-topics.md)
