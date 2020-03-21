---
title: '방법: 단색으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849524"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>방법: 단색으로 영역 그리기
단색으로 영역을 페인칠하려면 <xref:System.Windows.Media.Brushes.Red%2A> 또는 와 <xref:System.Windows.Media.Brushes.Blue%2A>같은 미리 정의된 시스템 브러시를 사용하거나 <xref:System.Windows.Media.SolidColorBrush> 알파, <xref:System.Windows.Media.SolidColorBrush.Color%2A> 빨간색, 녹색 및 파란색 값을 사용하여 새 브러시를 만들고 설명할 수 있습니다. XAML에서 16진수 표기법을 사용하여 단색으로 영역을 그릴 수도 있습니다.  
  
 다음 예제에서는 이러한 각 기술을 사용하여 <xref:System.Windows.Shapes.Rectangle> 파란색을 페인칠합니다.  
  
## <a name="example"></a>예제  
 **미리 정의된 브러시 사용**  
  
 다음 예제에서는 미리 정의된 <xref:System.Windows.Media.Brushes.Blue%2A> 브러시를 사용하여 사각형을 파란색으로 칠합니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **16진수 표기법 사용**  
  
 다음 예제에서는 8자리 16진수 표기법을 사용하여 파란색 사각형을 그립니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **ARGB 값 사용**  
  
 다음 예제는 <xref:System.Windows.Media.SolidColorBrush> 파란색에 대한 <xref:System.Windows.Media.SolidColorBrush.Color%2A> ARGB 값을 사용하여 a를 만들고 설명합니다.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 색상을 설명하는 다른 방법은 <xref:System.Windows.Media.Color> 구조를 참조하십시오.  
  
 **관련 주제**  
  
 및 추가 <xref:System.Windows.Media.SolidColorBrush> 예제에 대한 자세한 내용은 [단색 및 그라데이션이 있는 페인팅 개요 개요를](painting-with-solid-colors-and-gradients-overview.md) 참조하십시오.  
  
 이 코드 예제는에 대해 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.SolidColorBrush> 클래스입니다. 전체 샘플은 브러시 [샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Brushes>
