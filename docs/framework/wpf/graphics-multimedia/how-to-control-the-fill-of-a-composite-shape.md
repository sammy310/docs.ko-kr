---
title: '방법: 복합 도형의 채우기 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 0ba07d8979a2910ce4ec775493e38c714240f642
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427476"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>방법: 복합 도형의 채우기 제어
합니다 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 의 속성을 <xref:System.Windows.Media.GeometryGroup> 또는 <xref:System.Windows.Media.PathGeometry>은 복합 도형이 지정 된 기 하 도형의 일부 인지 확인 하는 "규칙"을 지정 합니다. 두 개의 가능한 값에 대 한 <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> 고 <xref:System.Windows.Media.FillRule.Nonzero>입니다. 다음 섹션에서는 이러한 두 가지 규칙을 사용하는 방법을 설명합니다.  
  
 **EvenOdd:** 이 규칙 점에서 모든 방향으로 무한대로 해당 지점에서 광선을 그리고 광선이 교차 하는 지정된 된 도형 내에서 경로 세그먼트 수를 계산 하 여 채우기 영역에는 점이 인지 여부를 결정 합니다. 이 숫자가 홀수이면 점이 안에 있고, 짝수이면 밖에 있습니다.  
  
 예를 들어 다음 XAML을 일련의 동심 링 (대상)의 구성 된 복합 도형을 사용 하 여 만듭니다는 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 로 <xref:System.Windows.Media.FillRule.EvenOdd>합니다.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![다른 색으로 시리즈 동심 링 이루어져 원형입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)  
  
 위의 그림에서 중심 및 세 번째 링이 채워져 있지는 확인 합니다. 두 링 중 하나에 있는 점에서 그린 광선이 짝수의 세그먼트를 통과하기 때문입니다. 다음 그림을 참조 하세요.  
  
 ![원에 그릴 EvenOdd 광선을 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)  
  
 **0이 아닌:** 이 규칙 점에서 모든 방향으로 무한대로 해당 지점에서 광선을 그리고 다음 도형의 세그먼트가 광선과 교차 하는 위치를 검사 하 여 경로의 채우기 영역에는 점이 인지 여부를 결정 합니다. 0부터 시작하여 세그먼트가 왼쪽에서 오른쪽으로 광선과 교차할 때마다 1을 추가하고 경로 세그먼트가 오른쪽에서 왼쪽으로 광선과 교차할 때마다 1을 뺍니다. 교차 수를 계산한 후 결과가 0이면 점이 경로의 밖에 있습니다. 그렇지 않으면 점이 내부에 있습니다.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 이전 예의 값을 사용 하 여 <xref:System.Windows.Media.FillRule.Nonzero> 에 대 한 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 결과적으로 다음 그림을 제공 합니다.  
  
 ![구성 요소로 이루어져 원 모든는 일련의 동심 링 동일한 색으로 채웁니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)  
  
 여기에서 볼 수 있듯이 모든 링이 채워집니다. 모든 세그먼트가 같은 방향으로 실행되므로 임의 점에서 그린 광선이 하나 이상의 세그먼트와 교차하고 교차의 합계가 0이 아니기 때문입니다. 예를 들어, 다음 그림에서 빨간색 화살표는 세그먼트가 그려진 방향을 나타냅니다 및 흰색 화살표는 가장 안쪽 링의 점에서 실행 되는 임의 광선을 나타냅니다. 광선이 교차하는 각 세그먼트에 대해 0 값부터 시작할 경우 세그먼트가 왼쪽에서 오른쪽으로 광선과 교차하므로 1이 추가됩니다.  
  
 ![Nonzero와 같은 FillRule 속성 값을 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)  
  
 동작을 더 잘 보여 주기 위해 <xref:System.Windows.Media.FillRule.Nonzero> 가 다른 방향으로 실행 하는 세그먼트를 사용 하 여 더 복잡 한 도형을 규칙이 필요 합니다. 아래의 XAML 코드를 제외 하 고 사용 하 여 만든 이전 예제와 비슷한 도형을 만들고를 <xref:System.Windows.Media.PathGeometry> 대신 다음을 <xref:System.Windows.Media.EllipseGeometry> 동심원을 완전히 닫힐 대신는 4 개의 동심 호를 만듭니다.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![세 번째 호 까지는 채워지지를 사용 하 여 다른 색으로 시리즈 동심 링 이루어져 원형입니다.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)  
  
 중심에서 세 번째 호까지는 채워지지 않습니다. 다음 그림에서는 그 이유를 보여 줍니다. 이 그림에서 빨간색 화살표는 세그먼트가 그려진 방향을 나타냅니다. 두 개의 흰색 화살표는 “채워지지 않은” 영역의 점에서 외부로 이동되는 2개의 임의 광선을 나타냅니다. 이 그림에서 볼 수 있듯이 해당 경로에서 세그먼트를 교차하는 지정된 광선의 값 합계는 0입니다. 앞에서 정의한 대로 합계가 0이 *아닌* 경우는 해당 점이 형상에 속하는 것을 의미하지만 합계가 0이라는 사실은 해당 점이 형상에 속하지 않음을 의미합니다(채우기의 일부가 아님).  
  
 ![임의 광선 교차 세그먼트를 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)  
  
 **참고:** 위해 <xref:System.Windows.Media.FillRule>, 모든 셰이프는 닫혀 있다고 간주 합니다. 세그먼트에 틈이 있으면 가상선을 그려 닫습니다. 위의 예제에서는 링에 작은 틈이 있습니다. 이점을 고려할 때 이러한 틈을 지나가는 광선이 다른 결과를 가져와 광선이 다른 방향으로 진행될 것으로 예상할 수 있습니다. 다음은 이러한 틈 및 "가상 세그먼트" 중 하나의 확대 그림 (적용 하기 위해 그린 세그먼트는 <xref:System.Windows.Media.FillRule>)를 닫습니다.  
  
 ![항상 닫힘 FillRule 세그먼트를 보여 주는 다이어그램입니다.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)  
  
## <a name="example"></a>예제  
  
## <a name="see-also"></a>참고자료

- [복합 도형 만들기](how-to-create-a-composite-shape.md)
- [Geometry 개요](geometry-overview.md)
