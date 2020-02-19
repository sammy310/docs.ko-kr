---
title: '방법: 현재 위치에서 요소가 회전하도록 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452794"
---
# <a name="how-to-make-an-element-spin-in-place"></a>방법: 현재 위치에서 요소가 회전하도록 만들기
이 예제에서는 <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>를 사용 하 여 요소를 회전 하는 방법을 보여 줍니다.  
  
 다음 예에서는 <xref:System.Windows.Media.RotateTransform>를 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용 합니다. 이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>를 사용 하 여 <xref:System.Windows.Media.RotateTransform><xref:System.Windows.Media.RotateTransform.Angle%2A>에 애니메이션 효과를 적용 합니다. 요소가 현재 위치에서 회전 하도록 하기 위해이 예제에서는 요소의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 point (0.5, 0.5)로 설정 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 더 많은 변환 예제를 포함 하는 전체 샘플은 [2 차원 변환 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [Transform 개요](transforms-overview.md)
