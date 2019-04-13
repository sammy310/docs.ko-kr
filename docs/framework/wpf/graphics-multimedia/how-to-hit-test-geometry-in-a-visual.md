---
title: '방법: 시각적 개체의 기하 도형 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227342"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>방법: 시각적 개체의 기하 도형 적중 테스트
하나 이상의 구성 된 시각적 개체에 대해 적중된 테스트를 수행 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Geometry> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 검색 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.DrawingGroup> 를 사용 하는 시각적 개체에서의 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드. 적중 횟수 테스트에서 각 그림의 렌더링 된 콘텐츠에 대해 수행한 후의 <xref:System.Windows.Media.DrawingGroup> 적중 된 기 하 도형을 확인 하려면.  
  
> [!NOTE]
>  대부분의 경우에 사용 된 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 점을 시각적 개체의 렌더링된 된 콘텐츠 중 하나를 교차 하는지 여부를 결정 하는 방법입니다.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 합니다 <xref:System.Windows.Media.Geometry.FillContains%2A> 메서드는 지정 된 사용 하 여 적중 테스트를 할 수 있는 오버 로드 된 메서드입니다 <xref:System.Windows.Point> 또는 <xref:System.Windows.Media.Geometry>합니다. 기하 도형에 스트로크를 적용할 경우 스트로크가 채우기 경계 밖으로 확장될 수 있습니다. 호출 하려는 경우에 <xref:System.Windows.Media.Geometry.StrokeContains%2A> 외에 <xref:System.Windows.Media.Geometry.FillContains%2A>합니다.  
  
 제공할 수도 있습니다는 <xref:System.Windows.Media.ToleranceType> 3 차원 곡선의 목적에 사용 되는 합니다.  
  
> [!NOTE]
>  이 샘플에서는 기하 도형에 적용될 수 있는 변환 또는 클리핑을 고려하지 않습니다. 또한 이 샘플은 직접 연결된 그림이 없으므로 스타일이 적용된 컨트롤에서 작동하지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [시각적 계층에서 적중 테스트](hit-testing-in-the-visual-layer.md)
- [기하 도형을 매개 변수로 사용하여 적중 테스트](how-to-hit-test-using-geometry-as-a-parameter.md)
