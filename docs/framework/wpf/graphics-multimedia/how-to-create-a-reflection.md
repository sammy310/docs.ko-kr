---
title: '방법: 리플렉션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452060"
---
# <a name="how-to-create-a-reflection"></a>방법: 리플렉션 만들기
이 예제에서는 <xref:System.Windows.Media.VisualBrush>를 사용 하 여 리플렉션을 만드는 방법을 보여 줍니다. <xref:System.Windows.Media.VisualBrush>는 기존 시각적 개체를 표시할 수 있으므로이 기능을 사용 하 여 반사 및 확대와 같은 흥미로운 시각적 효과를 얻을 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualBrush>를 사용 하 여 여러 요소를 포함 하는 <xref:System.Windows.Controls.Border>의 리플렉션을 만듭니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![리플렉션된 시각적 개체](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
반사된 표시 개체  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 화면의 일부를 확대 하는 방법을 보여 주는 예제를 포함 하는 전체 샘플 및 반사를 만드는 방법에 대 한 자세한 내용은 [Visualbrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.VisualBrush>
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
