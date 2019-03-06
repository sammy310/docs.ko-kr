---
title: '방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 04dbcfdb64525e6231ecf33c8ac5ecf2a2d2cb7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357936"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimation> 클래스를 따라 개체에 애니메이션 효과 주기는 <xref:System.Windows.Shapes.Path>합니다.  
  
## <a name="example"></a>예제  
 다음 예제를 따라 타원을 이동는 <xref:System.Windows.Shapes.Path> 다른 화면의 한 점에서 합니다. 예제 애니메이션의 위치는 <xref:System.Windows.Media.EllipseGeometry> 를 사용 하 여 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션 효과를 주는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [애니메이션 개요](animation-overview.md)
- [그래픽 및 멀티미디어](index.md)
- [그래픽 방법 항목](graphics-how-to-topics.md)
- [애니메이션 및 타이밍 방법 항목](animation-and-timing-how-to-topics.md)
