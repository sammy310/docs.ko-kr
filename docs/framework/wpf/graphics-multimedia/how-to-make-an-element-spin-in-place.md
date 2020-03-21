---
title: '방법: 현재 위치에서 요소가 회전하도록 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112078"
---
# <a name="how-to-make-an-element-spin-in-place"></a>방법: 현재 위치에서 요소가 회전하도록 만들기
이 예제에서는 <xref:System.Windows.Media.RotateTransform> a 및 를 사용하여 요소 <xref:System.Windows.Media.Animation.DoubleAnimation>회전을 만드는 방법을 보여 주었습니다.  
  
 다음 예제는 <xref:System.Windows.Media.RotateTransform> 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용 됩니다. 이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform>애니메이션을 사용합니다. 요소를 제자리에 회전시키기 위해 예제에서는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 요소의 속성을 점(0.5, 0.5)으로 설정합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 더 많은 변환 예제가 포함된 전체 샘플의 경우 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [Transform 개요](transforms-overview.md)
