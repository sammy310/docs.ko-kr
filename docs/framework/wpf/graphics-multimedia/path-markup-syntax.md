---
title: 경로 태그 구문
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181856"
---
# <a name="path-markup-syntax"></a>경로 태그 구문
경로는 WPF 개요 및 [형상 개요의](geometry-overview.md) [모양 및 기본 도면에서](shapes-and-basic-drawing-in-wpf-overview.md) 설명되지만 이 항목에서는 을 사용하여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]경로 형상을 보다 컴팩트하게 지정하는 데 사용할 수 있는 강력하고 복잡한 미니 언어를 자세히 설명합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 개체의 <xref:System.Windows.Media.Geometry> 기본 기능에 대해 잘 알고 있어야 합니다. 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry 및 PathFigureCollection 미니 언어  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기하학적 경로를 설명하기 위한 미니 언어를 제공하는 두 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>개의 클래스를 제공합니다.  
  
- a의 <xref:System.Windows.Media.StreamGeometry> 속성 <xref:System.Windows.Media.Geometry> <xref:System.Windows.UIElement.Clip%2A> <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> <xref:System.Windows.Shapes.Path> 요소의 속성과 같은 형식의 속성을 설정할 때 미니 언어를 사용합니다. 다음 예제에서는 특성 구문을 <xref:System.Windows.Media.StreamGeometry>사용하여 을 만듭니다.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- 의 <xref:System.Windows.Media.PathFigureCollection> <xref:System.Windows.Media.PathGeometry.Figures%2A> 속성을 설정할 때 미니 언어를 <xref:System.Windows.Media.PathGeometry>사용합니다. 다음 예제에서는 특성 구문을 사용하여 <xref:System.Windows.Media.PathFigureCollection> <xref:System.Windows.Media.PathGeometry>에 대한 을 만듭니다.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 앞의 예제에서 볼 수 있는 것처럼 두 개의 미니 언어는 매우 비슷합니다. 을 사용할 수 있는 <xref:System.Windows.Media.PathGeometry> 모든 상황에서 를 사용할 <xref:System.Windows.Media.StreamGeometry>수 있습니다. 그래서 당신은 어떤 하나를 사용해야합니까? 패스를 <xref:System.Windows.Media.StreamGeometry> 만든 후 수정할 필요가 없는 경우 를 사용합니다. 패스를 <xref:System.Windows.Media.PathGeometry> 수정해야 하는 경우 를 사용합니다.  
  
 객체와 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 객체 간의 차이점에 대한 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
### <a name="a-note-about-white-space"></a>공백에 대한 참고 사항  
 간단히 말해서 이어지는 구문 섹션에는 단일 공백이 표시되지만 단일 공백이 표시되는 모든 위치에서 여러 개의 공백을 사용해도 됩니다.  
  
 두 숫자는 실제로 쉼표 나 공백으로 구분 될 필요는 없지만 결과 문자열이 모호하지 않은 경우에만 수행 할 수 있습니다. 예를 들어 `2..3` 실제로는 "2"라는 두 개의 숫자입니다. ".3"의 두 숫자입니다. 마찬가지로, `2-3` "2"와 "-3"입니다. 명령 앞뒤에는 공백이 필요하지 않습니다.  
  
### <a name="syntax"></a>구문  
 a의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Media.StreamGeometry> 특성 사용 구문은 선택적 <xref:System.Windows.Media.FillRule> 값과 하나 이상의 그림 설명으로 구성됩니다.  
  
|StreamGeometry XAML 특성 사용|  
|-----------------------------------------|  
|`<`*개체* *property* `="`속성 `fillRule` `figureDescription`[ `figureDescription`[ [ []*`" ... />`|  
  
 a의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Media.PathFigureCollection> 특성 사용 구문은 하나 이상의 그림 설명으로 구성됩니다.  
  
|PathFigureCollection XAML 특성 사용|  
|-----------------------------------------------|  
|`<`*개체* *property* `="` `figureDescription`속성 `figureDescription`[ []*`" ... />`|  
  
|용어|Description|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> 을 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathGeometry.FillRule%2A>사용하는지 여부를 지정합니다. <xref:System.Windows.Media.FillRule.EvenOdd> <xref:System.Windows.Media.FillRule.Nonzero><br /><br /> -   `F0`채우기 규칙을 <xref:System.Windows.Media.FillRule.EvenOdd> 지정합니다.<br />-   `F1`채우기 규칙을 <xref:System.Windows.Media.FillRule.Nonzero> 지정합니다.<br /><br /> 이 명령을 생략하면 하위 경로는 기본 동작을 <xref:System.Windows.Media.FillRule.EvenOdd>사용합니다. 이 명령을 지정하는 경우 맨 앞에 배치해야 합니다.|  
|*figureDescription*|이동 명령, 그리기 명령 및 선택적 닫기 명령으로 구성된 그림입니다.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|그림의 시작점을 지정하는 이동 명령입니다. 명령 [이동](#themovecommand) 섹션을 참조하십시오.|  
|*drawCommands*|그림의 콘텐츠를 설명하는 하나 이상의 그리기 명령입니다. 명령 [그리기](#drawcommands) 섹션을 참조하십시오.|  
|*closeCommand*|그림을 닫는 선택적 닫기 명령입니다. 명령 [닫기](#closecommand) 섹션을 참조하십시오.|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>이동 명령  
 새 그림의 시작점을 지정합니다.  
  
|구문|  
|------------|  
|`M`*시작 점*<br /><br /> -또는-<br /><br /> `m`*시작 점*|  
  
|용어|Description|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 새 그림의 시작점입니다.|  
  
 `startPoint` 대문자는 `M` 절대 값임을 나타냅니다. `startPoint` 소문자는 `m` 이전 점에 대한 오프셋또는 존재하지 않는 경우 (0,0)임을 나타냅니다. 이동 명령 뒤에 여러 점을 나열하는 경우 선 명령을 지정했어도 해당 점으로 선이 그려집니다.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>그리기 명령  
 그리기 명령은 여러 도형 명령으로 구성될 수 있습니다. 선, 수평선, 수직선, 입방형 3차원 곡선, 정방형 3차원 곡선, 부드러운 입방형 3차원 곡선, 부드러운 정방형 3차원 곡선 및 타원형 호 등의 도형 명령을 사용할 수 있습니다.  
  
 대문자 또는 소문자를 사용하여 각 명령을 입력합니다. 대문자는 절대값을 나타내고 소문자는 상대값을 나타냅니다. 해당 세그먼트에 대한 제어점은 이전 예제의 끝점을 기준으로 합니다. 동일한 형식의 두 개 이상의 명령을 순차적으로 입력하면 중복 명령 항목을 생략할 수 있습니다. 예를 들어, `L 100,200 300,400` 에 `L 100,200 L 300,400`해당합니다. 다음 표는 **이동** 및 **그리기** 명령에 대해 설명합니다.  
  
### <a name="line-command"></a>선 명령  
 현재 점과 지정된 끝점 간에 직선을 만듭니다. `l 20 30`유효한 `L 20,30` **줄** 명령의 예입니다.  
  
|구문|  
|------------|  
|`L`*끝점*<br /><br /> -또는-<br /><br /> `l`*끝점*|  
  
|용어|Description|  
|----------|-----------------|  
|*끝점*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 선의 끝점입니다.|  

`endPoint` 대문자는 `L` 절대 값임을 나타냅니다. `endPoint` 소문자는 `l` 이전 점에 대한 오프셋또는 존재하지 않는 경우 (0,0)임을 나타냅니다.

### <a name="horizontal-line-command"></a>수평선 명령  
 현재 점과 지정된 x 좌표 간에 수평선을 만듭니다. `H 90`은 유효한 수평선 명령의 예입니다.

|구문|  
|------------|  
|`H`  *Ⅹ*<br /><br /> -또는-<br /><br /> `h`  *Ⅹ*|  
  
|용어|Description|  
|----------|-----------------|  
|*Ⅹ*|<xref:System.Double?displayProperty=nameWithType><br /><br /> 선 끝점의 x 좌표입니다.|  
  
`x` 대문자는 `H` 절대 값임을 나타냅니다. `x` 소문자는 `h` 이전 점에 대한 오프셋또는 존재하지 않는 경우 (0,0)임을 나타냅니다.
  
### <a name="vertical-line-command"></a>수직선 명령  
 현재 점과 지정된 y 좌표 간에 수직선을 만듭니다. `v 90`은 유효한 수직선 명령의 예입니다.

|구문|  
|------------|  
|`V`  *Y*<br /><br /> -또는-<br /><br /> `v`  *Y*|  
  
|용어|Description|  
|----------|-----------------|  
|*Y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> 선 끝점의 y 좌표입니다.|  

`y` 대문자는 `V` 절대 값임을 나타냅니다. `y` 소문자는 `v` 이전 점에 대한 오프셋또는 존재하지 않는 경우 (0,0)임을 나타냅니다.  

### <a name="cubic-bezier-curve-command"></a>입방형 3차원 곡선 명령  
 지정된 두 가지 제어점(1과`controlPoint` `controlPoint`2)을 사용하여 현재 점과 지정된 끝점 사이에 입방 베지어 곡선을 만듭니다. `C 100,200 200,400 300,200`은 유효한 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`C``controlPoint`1`controlPoint`2`endPoint`<br /><br /> -또는-<br /><br /> `c``controlPoint`1`controlPoint`2`endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 접선을 결정하는 곡선의 첫 번째 제어점입니다.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 끝 접선을 결정하는 곡선의 두 번째 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="quadratic-bezier-curve-command"></a>정방형 3차원 곡선 명령  
 지정된 제어점()을`controlPoint`사용하여 현재 점과 지정된 끝점 사이에 이차 Bezier 곡선을 만듭니다. `q 100,200 300,200`은 유효한 정방형 3차원 곡선 명령의 예입니다.  
  
|구문|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> -또는-<br /><br /> `q` `controlPoint` `endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 및 끝 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>부드러운 입방형 3차원 곡선 명령  
 현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다. 첫 번째 제어점은 현재 점을 기준으로 이전 명령의 두 번째 제어점의 리플렉션으로 간주됩니다. 이전 명령이 없거나 이전 명령이 입방형 3차원 곡선 명령 또는 부드러운 입방 형 3차원 곡선 명령이 아닌 경우 첫 번째 제어점이 현재 점과 일치한다고 가정합니다. 두 번째 제어점인 곡선 끝에 대한 제어점은 2로 `controlPoint`지정됩니다. 예를 들어, `S 100,200 200,300` 유효한 매끄러운 입방 베지어 곡선 명령입니다.  
  
|구문|  
|------------|  
|`S``controlPoint`2개`endPoint`<br /><br /> -또는-<br /><br /> `s``controlPoint`2개`endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 끝 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>부드러운 정방형 3차원 곡선 명령  
 현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다. 제어점은 현재 점을 기준으로 이전 명령의 제어점의 리플렉션으로 간주됩니다. 이전 명령이 없거나 이전 명령이 정방형 3차원 곡선 명령 또는 부드러운 정방 형 3차원 곡선 명령이 아닌 경우 제어점이 현재 점과 일치합니다.  
  
|구문|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> -또는-<br /><br /> `t` `controlPoint` `endPoint`|  
  
|용어|Description|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선의 시작 접선을 결정하는 곡선의 제어점입니다.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> 곡선을 그릴 지점입니다.|  
  
### <a name="elliptical-arc-command"></a>타원형 호 명령  
 현재 점과 지정된 끝점 간에 타원형 호를 만듭니다.  
  
|구문|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> -또는-<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
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
|`Z`<br /><br /> -또는-<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>점 구문  
 (0,0)가 왼쪽 상단 모서리인 점의 x-및 y 좌표를 설명합니다.
  
|구문|  
|------------|  
|`x` `,` `y`<br /><br /> -또는-<br /><br /> `x` `y`|  
  
|용어|Description|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> 점의 X 좌표입니다.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> 점의 Y 좌표입니다.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>특수 값  
 표준 숫자 값 대신 다음과 같은 특수 값을 사용할 수도 있습니다. 이러한 값은 대/소문자를 구분합니다.  
  
 Infinity  
 를 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>나타냅니다.  
  
 -Infinity  
 를 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>나타냅니다.  
  
 NaN  
 를 <xref:System.Double.NaN?displayProperty=nameWithType>나타냅니다.  
  
 과학적 표기법을 사용할 수도 있습니다. 예를 들어 `+1.e17` 유효한 값입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [Geometry 개요](geometry-overview.md)
- [방법 주제](geometries-how-to-topics.md)
