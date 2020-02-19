---
title: '방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452846"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용
이 예제에서는 <xref:System.Windows.Media.GradientStop> 개체의 <xref:System.Windows.Media.GradientStop.Color%2A> 및 <xref:System.Windows.Media.GradientStop.Offset%2A>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.LinearGradientBrush>내에서 세 개의 그라데이션 중지점에 애니메이션 효과를 적용 합니다. 이 예제에서는 각각 다른 그라데이션 중지점에 애니메이션을 적용 하는 세 가지 애니메이션을 사용 합니다.  
  
- 첫 번째 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation>는 첫 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Offset%2A> 0.0에서 1.0로, 다시 0.0으로 애니메이션 효과를 적용 합니다. 따라서 그라데이션의 첫 번째 색은 왼쪽에서 사각형의 오른쪽으로 이동한 다음 왼쪽으로 이동 합니다.  
  
- 두 번째 애니메이션 인 <xref:System.Windows.Media.Animation.ColorAnimation>에서는 두 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.Colors.Purple%2A>에서 <xref:System.Windows.Media.Colors.Yellow%2A>에 애니메이션을 적용 한 다음 다시 <xref:System.Windows.Media.Colors.Purple%2A>에 애니메이션 효과를 적용 합니다. 따라서 그라데이션의 중간 색은 자주색에서 노랑으로, 다시 자주색으로 변경 됩니다.  
  
- 세 번째 애니메이션 인 다른 <xref:System.Windows.Media.Animation.ColorAnimation>는 세 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Color%2A>-1을 사용한 다음 뒤로의 불투명도에 애니메이션 효과를 적용 합니다. 따라서 그라데이션에서 세 번째 색이 서서히 사라지고 다시 불투명 하 게 됩니다.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 이 예제에서는 <xref:System.Windows.Media.LinearGradientBrush>를 사용 하지만 <xref:System.Windows.Media.RadialGradientBrush>내에서 <xref:System.Windows.Media.GradientStop> 개체에 애니메이션을 적용 하는 프로세스는 동일 합니다.  
  
 추가 예제는 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.GradientStop>
- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
