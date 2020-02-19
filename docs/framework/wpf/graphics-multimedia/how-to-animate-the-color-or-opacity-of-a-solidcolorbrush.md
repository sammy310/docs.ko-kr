---
title: '방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452885"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용
이 예제에서는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 가지 애니메이션을 사용 하 여 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 적용 합니다.  
  
- 첫 번째 애니메이션 인 <xref:System.Windows.Media.Animation.ColorAnimation>는 마우스를 사각형 안으로 가져갈 때 브러시의 색을 <xref:System.Windows.Media.Colors.Gray%2A>으로 변경 합니다.  
  
- 다음 애니메이션 인 다른 <xref:System.Windows.Media.Animation.ColorAnimation>는 마우스가 사각형을 벗어날 때 브러시의 색을 <xref:System.Windows.Media.Colors.Orange%2A>으로 변경 합니다.  
  
- 최종 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation>왼쪽 마우스 단추를 누르면 브러시의 불투명도가 0.0로 변경 됩니다.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 여러 브러시 형식에 애니메이션 효과를 주는 방법을 보여 주는 전체 샘플을 보려면 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조 하세요. 애니메이션에 대 한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조 하세요.  
  
 다른 애니메이션 예제와의 일관성을 위해이 예제의 코드 버전에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용 하 여 애니메이션을 적용 합니다. 그러나 코드에서 단일 애니메이션을 적용 하는 경우 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하는 대신 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용 하는 것이 더 간단 합니다. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
- [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
