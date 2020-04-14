---
title: '방법: 애니메이션 가속 또는 감속'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243013"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>방법: 애니메이션 가속 또는 감속

이 예제에서는 애니메이션을 시간이 지남에 따라 가속화하고 감속하는 방법을 보여 줍니다. 다음 예제에서는 여러 사각형이 서로 다른 <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> 설정과 <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> 설정된 애니메이션에 의해 애니메이션됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 이 예제에서 코드가 생략되었습니다. 전체 코드는 애니메이션 [타이밍 동작(C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) 또는 [애니메이션 타이밍 동작(Visual Basic)을](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic)참조하십시오.
