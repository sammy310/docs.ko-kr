---
title: '방법: 요소 기울이기'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112026"
---
# <a name="how-to-skew-an-element"></a>방법: 요소 기울이기
이 예제에서는 a를 <xref:System.Windows.Media.SkewTransform> 사용하여 요소를 왜곡하는 방법을 보여 주었습니다. 전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다. a의 <xref:System.Windows.Media.SkewTransform> 일반적인 용도 중 하나는 2D 개체에서 3D 깊이를 시뮬레이션하는 것입니다.  
  
 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 속성과 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 속성을 사용하여 의 중심점을 지정합니다. <xref:System.Windows.Media.SkewTransform>  
  
 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 속성을 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 사용하여 x축 및 y축의 기울이기 각도를 지정하고 이러한 축을 따라 현재 좌표계를 기울이도록 합니다.  
  
 기울이기 변환의 효과를 예측하려면 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 원래 좌표계를 기준으로 x축 값을 기울이는 것이 좋습니다. 따라서 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30의 경우 y축은 원점을 통해 30도 회전하고 해당 원점에서 30도 씩 값을 x-씩 기울입니다. 마찬가지로 30의 값은 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 모양의 y-값을 원점에서 30도 기울이게 합니다. 이것은 좌표 시스템을 x 또는 y축으로 30도만큼 변환(이동)하는 것과 같지 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(0,0)에서 45도의 수평 스큐를 적용합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(25,25)에서 45도의 수평 스큐를 적용합니다.  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 중심점(25,25)에서 45도의 수직 스큐를 적용합니다.  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 다음 그림에서는 이 예제에서 사용되는 다양한 기울이기를 보여 줍니다.  
  
 ![SkewTransform 예제](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
세 개의 SkewTransform 예제 그림  
  
 전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Transform 개요](transforms-overview.md)
- [방법 주제](transformations-how-to-topics.md)
