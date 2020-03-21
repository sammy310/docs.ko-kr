---
title: '방법: TileBrush의 바둑판 크기 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186830"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>방법: TileBrush의 바둑판 크기 설정

이 예제에서는 <xref:System.Windows.Media.TileBrush>에 대한 타일 크기를 설정하는 방법을 보여 주며 있습니다. 기본적으로 페인팅할 <xref:System.Windows.Media.TileBrush> 영역을 완전히 채우는 단일 타일이 생성됩니다. 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 설정하여 이 <xref:System.Windows.Media.TileBrush.Viewport%2A> 동작을 재정의할 수 있습니다.

속성은 <xref:System.Windows.Media.TileBrush.Viewport%2A> 에 대한 타일 크기를 <xref:System.Windows.Media.TileBrush>지정합니다. 기본적으로 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성 값은 페인팅되는 영역의 크기에 상대적입니다. 속성이 <xref:System.Windows.Media.TileBrush.Viewport%2A> 절대 타일 크기를 지정하도록 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 하려면 <xref:System.Windows.Media.BrushMappingMode.Absolute>속성을 로 설정합니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Windows.Media.ImageBrush>"의 유형 <xref:System.Windows.Media.TileBrush>"를 사용하여 사각형을 타일로 페인칠합니다. 이 예제에서는 각 타일을 출력 영역(사각형)의 50%씩 50%로 설정합니다. 결과적으로 이미지 프로젝션 4개를 사용한 사각형이 그려집니다.

다음 그림에서는 예제에서 생성하는 출력을 보여 주며, 다음 그림은 다음과 같은 결과를 보여 주며 있습니다.

![이미지 브러시로 타일링을 보여주는 4 개의 체리가있는 직사각형.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

다음 예제에서는 <xref:System.Windows.Media.ImageBrush>을 만들고 <xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` 그 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 에 <xref:System.Windows.Media.BrushMappingMode.Absolute>대해 설정하고 그 를 에 로 설정하고 이를 사용하여 다른 사각형을 페인칠합니다. 결과적으로 이 브러시는 너비 및 높이가 각각 25픽셀인 타일을 생성합니다.

다음 그림에서는 예제에서 생성하는 출력을 보여 주며, 다음 그림은 다음과 같은 결과를 보여 주며 있습니다.

![뷰포트가 있는 타일 브러시를 보여주는 48개의 체리가 있는 직사각형.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

앞의 예제는 큰 샘플의 일부입니다. 전체 샘플은 [ImageBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)참조하십시오.

이 예제에서는 <xref:System.Windows.Media.ImageBrush> 클래스를 <xref:System.Windows.Media.TileBrush.Viewport%2A> 사용하지만 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성은 다른 <xref:System.Windows.Media.TileBrush> 개체, 즉 <xref:System.Windows.Media.DrawingBrush> 에 <xref:System.Windows.Media.VisualBrush>대해 와 동일한 작업을 합니다. 및 기타 <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.ImageBrush> 객체에 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.TileBrush>
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [TileBrush로 다른 바둑판식 배열 패턴 만들기](how-to-create-different-tile-patterns-with-a-tilebrush.md)
