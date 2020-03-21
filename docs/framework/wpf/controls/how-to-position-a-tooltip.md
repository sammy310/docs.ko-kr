---
title: '방법: 도구 설명 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186944"
---
# <a name="how-to-position-a-tooltip"></a>방법: 도구 설명 배치
이 예제에서는 화면에서 도구 설명의 위치를 지정하는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.ToolTip> 클래스와 <xref:System.Windows.Controls.ToolTipService> 클래스 모두에 정의된 5개의 속성 집합을 사용하여 도구 설명에 배치할 수 있습니다. 다음 표에서는 이 두 속성 집합을 보여 주며 클래스에 따라 참조 문서에 대한 링크를 제공합니다.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>클래스별 해당 툴팁 속성  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>클래스 속성|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>클래스 속성|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <xref:System.Windows.Controls.ToolTip> 개체를 사용하여 도구 설명의 내용을 정의하는 경우 두 클래스의 속성을 사용할 수 있습니다. 그러나 속성이 <xref:System.Windows.Controls.ToolTipService> 우선합니다. 객체로 <xref:System.Windows.Controls.ToolTipService> <xref:System.Windows.Controls.ToolTip> 정의되지 않은 도구 설명에 속성을 사용합니다.  
  
 다음 그림에서는 이러한 속성을 사용하여 도구 설명의 위치를 지정하는 방법을 보여 주습니다. 이 그림의 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.ToolTip> 클래스에 의해 정의된 속성을 설정하는 방법을 보여 주지만 <xref:System.Windows.Controls.ToolTipService> 클래스의 해당 속성은 동일한 레이아웃 규칙을 따릅니다. 게재위치 속성의 가능한 값에 대한 자세한 내용은 [노출 위치 설정 동작 을](popup-placement-behavior.md)참조하세요.  

 다음 이미지는 배치 속성을 사용하여 도구 설명 배치 배치를 보여 주며 있습니다.  
  
 ![배치 속성을 사용하여 ToolTip 배치를 보여주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 다음 이미지는 배치 및 배치 직각 특성을 사용하여 도구 설명 배치 배치를 보여 주며 다음과 같은 위치를 보여 주며 다음과 같은 위치를 보여 주며 다음과 같은 위치에 대해 설명합니다.

 ![배치 직각 속성을 사용하여 도구 팁 배치를 보여주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 다음 이미지는 배치, 배치 직각 및 간격띄우기 속성을 사용하여 도구 설명 배치 배치를 보여 주며 다음과 같은 위치를 보여 주며 다음과 같은 위치에 대해 설명합니다.
  
 ![오프셋 속성을 사용하여 ToolTip 배치를 보여주는 다이어그램입니다.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 다음 예제에서는 <xref:System.Windows.Controls.ToolTip> 속성을 사용하여 콘텐츠가 객체인 도구 설명의 위치를 <xref:System.Windows.Controls.ToolTip> 지정하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ToolTipService> 속성을 사용하여 콘텐츠가 <xref:System.Windows.Controls.ToolTip> 개체가 아닌 도구 설명의 위치를 지정하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [방법 주제](tooltip-how-to-topics.md)
- [도구 설명 개요](tooltip-overview.md)
