---
title: '방법: 요소 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111974"
---
# <a name="how-to-translate-an-element"></a>방법: 요소 변환
이 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 요소를 변환(이동)하는 방법을 보여 주며.  
  
 클래스는 <xref:System.Windows.Media.TranslateTransform> 절대 위치 지정을 지원하지 않는 패널 내부의 요소를 이동하는 데 특히 유용합니다. 예를 들어 요소의 <xref:System.Windows.Media.TranslateTransform> 속성에 <xref:System.Windows.UIElement.RenderTransform%2A> a를 적용하여 <xref:System.Windows.Controls.StackPanel> 또는 에서 <xref:System.Windows.Controls.DockPanel>요소를 이동할 수 있습니다.  
  
 의 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.X%2A> 속성을 사용하여 x축을 따라 요소를 이동하는 양을 픽셀 단위로 지정합니다. 속성을 <xref:System.Windows.Media.TranslateTransform.Y%2A> 사용하여 y축을 따라 요소를 이동하는 양을 픽셀 단위로 지정합니다. 마지막으로 요소의 <xref:System.Windows.Media.TranslateTransform> 속성에 <xref:System.Windows.UIElement.RenderTransform%2A> 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.TranslateTransform> a를 사용하여 요소를 50픽셀 을 오른쪽으로, 50픽셀 아래로 이동합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [Transform 개요](transforms-overview.md)
