---
title: '방법: 기하 도형을 매개 변수로 사용하여 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 3d6f4190a5b5c8410a6be01d2645df9c123f9ac4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410617"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>방법: 기하 도형을 매개 변수로 사용하여 적중 테스트
사용 하 여 시각적 개체에서 적중 횟수 테스트를 수행 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Geometry> 적중 테스트 매개 변수입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 적중된 테스트를 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Media.GeometryHitTestParameters> 에 대 한는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드. <xref:System.Windows.Point> 에 전달 되는 값을 `OnMouseDown` 메서드는 만드는 데는 <xref:System.Windows.Media.Geometry> 적중 횟수 테스트의 범위를 확대 하기 위해 개체입니다.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 속성을 <xref:System.Windows.Media.GeometryHitTestResult> 사용 하는 적중된 테스트의 결과 대 한 정보를 제공는 <xref:System.Windows.Media.Geometry> 를 적중 테스트 매개 변수로 합니다. 다음 그림에서는 적중 테스트 기하 도형(파란색 원)과 대상 시각적 개체의 렌더링된 콘텐츠(빨간색 사각형) 간 관계를 보여 줍니다.  
  
 ![적중 테스트에 사용 되는 IntersectionDetail를 보여 주는 다이어그램입니다.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 다음 예제에서는 적중된 테스트 콜백을 구현 하는 때를 <xref:System.Windows.Media.Geometry> 적중된 테스트 매개 변수로 사용 됩니다. `result` 캐스팅할 매개 변수를 <xref:System.Windows.Media.GeometryHitTestResult> 의 값을 검색 하기 위해는 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 속성입니다. 속성 값을 사용 하면 여부를 확인 하는 <xref:System.Windows.Media.Geometry> 적중된 테스트 매개 변수는 적중된 테스트 대상의 렌더링된 된 콘텐츠 내에서 완전히 또는 부분적으로 포함 합니다. 이 경우 샘플 코드는 대상 경계 내에 완전히 포함된 시각적 개체 목록에 적중 테스트 결과를 추가하기만 합니다.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Media.HitTestResult> 교차 세부 사항이 때 콜백이 호출 되지 해야 <xref:System.Windows.Media.IntersectionDetail.Empty>합니다.  
  
## <a name="see-also"></a>참고자료
- [시각적 계층에서 적중 테스트](hit-testing-in-the-visual-layer.md)
- [시각적 요소의 기하 도형 적중 테스트](how-to-hit-test-geometry-in-a-visual.md)
