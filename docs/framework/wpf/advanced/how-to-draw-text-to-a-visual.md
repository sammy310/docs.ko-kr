---
title: '방법: 시각적 요소에 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094555"
---
# <a name="how-to-draw-text-to-a-visual"></a>방법: 시각적 요소에 텍스트 그리기
다음 예제에서는 <xref:System.Windows.Media.DrawingContext> 개체를 사용 하 여 <xref:System.Windows.Media.DrawingVisual>에 텍스트를 그리는 방법을 보여 줍니다. 그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다. 그리기 컨텍스트에 그래픽과 텍스트를 그릴 수 있습니다.  
  
 그리기 컨텍스트에 텍스트를 그리려면 <xref:System.Windows.Media.DrawingContext> 개체의 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 메서드를 사용 합니다. 그리기 컨텍스트에 콘텐츠 그리기를 마치면 <xref:System.Windows.Media.DrawingContext.Close%2A> 메서드를 호출 하 여 그리기 컨텍스트를 닫고 콘텐츠를 유지 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> 위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)을 참조하세요.
