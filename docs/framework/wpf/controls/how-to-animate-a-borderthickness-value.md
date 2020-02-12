---
title: '방법: BorderThickness 값에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124665"
---
# <a name="how-to-animate-a-borderthickness-value"></a>방법: BorderThickness 값에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimation> 클래스를 사용 하 여 테두리 두께에 변경 내용을 적용 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Media.Animation.ThicknessAnimation>를 사용 하 여 테두리 두께에 애니메이션 효과를 적용 합니다. 이 예제에서는 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Border.BorderThickness%2A> 속성을 사용 합니다.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 전체 샘플은 [애니메이션 예제 갤러리](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [애니메이션 개요](../graphics-multimedia/animation-overview.md)
- [애니메이션 및 타이밍 방법 도움말 항목](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
