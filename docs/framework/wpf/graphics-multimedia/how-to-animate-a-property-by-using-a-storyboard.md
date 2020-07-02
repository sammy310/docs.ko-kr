---
title: '방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기'
description: Windows Presentation Foundation (WPF)의 속성에 대 한 애니메이션 및 스토리 보드를 사용 하 여 사용자 인터페이스를 Enliven 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f21b606751b845905a7bde6d3a7658b214369cc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853752"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기
이 예제에서는를 사용 하 여 <xref:System.Windows.Media.Animation.Storyboard> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다. 을 사용 하 여 속성에 애니메이션 효과를 주려면 애니메이션 <xref:System.Windows.Media.Animation.Storyboard> 효과를 적용할 각 속성에 대 한 애니메이션을 만들고 애니메이션을 포함 하는을 만듭니다 <xref:System.Windows.Media.Animation.Storyboard> .  
  
 속성 형식에 따라 사용할 애니메이션 형식이 결정됩니다. 예를 들어 값을 사용 하는 속성에 애니메이션 효과를 주려면를 <xref:System.Double> 사용 <xref:System.Windows.Media.Animation.DoubleAnimation> 합니다. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> 연결 된 속성은 애니메이션이 적용 되는 개체 및 속성을 지정 합니다.  
  
 에서 storyboard를 시작 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 작업과를 사용 <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger> 합니다. 는 <xref:System.Windows.EventTrigger> 속성에 <xref:System.Windows.Media.Animation.BeginStoryboard> 지정 된 이벤트가 발생할 때 작업을 시작 합니다 <xref:System.Windows.EventTrigger.RoutedEvent%2A> . <xref:System.Windows.Media.Animation.BeginStoryboard>작업은를 시작 합니다 <xref:System.Windows.Media.Animation.Storyboard> .  
  
 다음 예제에서는 개체를 사용 하 여 <xref:System.Windows.Media.Animation.Storyboard> 두 컨트롤에 애니메이션 효과를 적용 <xref:System.Windows.Controls.Button> 합니다. 첫 번째 단추의 크기를 변경 하려면에 애니메이션을 <xref:System.Windows.FrameworkElement.Width%2A> 적용 합니다. 두 번째 단추의 색을 변경 하려면 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 속성을 사용 하 여 <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Controls.Control.Background%2A> 애니메이션 효과가 적용 되는 단추의를 설정 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> 애니메이션은 또는와 같은 개체와 또는 등의 개체를 모두 대상으로 할 수 있지만 <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.Panel> <xref:System.Windows.Freezable> <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Transform> 프레임 워크 요소만 속성을 가집니다 <xref:System.Windows.FrameworkElement.Name%2A> . 애니메이션의 대상으로 지정될 수 있게 freezable에 이름을 할당하려면 이전 예제와 같이 [x:Name 지시문](../../../desktop-wpf/xaml-services/xname-directive.md)을 사용합니다.  
  
 코드를 사용 하는 경우에는에 <xref:System.Windows.NameScope> 대 한를 만들고 <xref:System.Windows.FrameworkElement> 개체 이름을 등록 하 여 애니메이션 효과를 적용 해야 합니다 <xref:System.Windows.FrameworkElement> . 코드에서 애니메이션을 시작 하려면를 사용 하 여 작업을 사용 <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger> 합니다. 필요에 따라 이벤트 처리기 및의 메서드를 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> <xref:System.Windows.Media.Animation.Storyboard> . 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 애니메이션 및 Storyboard에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
 코드를 사용 하는 경우 <xref:System.Windows.Media.Animation.Storyboard> 속성에 애니메이션 효과를 주기 위해 개체를 사용 하는 것으로 제한 되지 않습니다. 자세한 내용 및 예제에 대해서는 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md) 및 [AnimationClock을 사용하여 속성에 애니메이션 효과 적용](how-to-animate-a-property-by-using-an-animationclock.md)을 참조하세요.
