---
title: '방법: 컨트롤의 배경에 텍스트 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424386"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>방법: 컨트롤의 배경에 텍스트 그리기
텍스트 문자열을 <xref:System.Windows.Media.FormattedText> 개체로 변환한 다음 개체를 컨트롤의 <xref:System.Windows.Media.DrawingContext>에 그려서 컨트롤의 배경에 직접 텍스트를 그릴 수 있습니다. 이 기술을 사용 하 여 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.StackPanel>와 같은 <xref:System.Windows.Controls.Panel>에서 파생 된 개체의 배경으로 그릴 수도 있습니다.  
  
 ![텍스트를 배경으로 표시 하는 컨트롤의 스크린샷](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
사용자 지정 텍스트 배경이 있는 컨트롤의 예  
  
## <a name="example"></a>예제  
 컨트롤의 배경에 그리려면 새 <xref:System.Windows.Media.DrawingBrush> 개체를 만들고 변환 된 텍스트를 개체의 <xref:System.Windows.Media.DrawingContext>에 그립니다. 그런 다음 컨트롤의 background 속성에 새 <xref:System.Windows.Media.DrawingBrush>를 할당 합니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Button> 개체의 배경으로 그리는 방법을 보여 줍니다.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.FormattedText>
- [서식 있는 텍스트 그리기](drawing-formatted-text.md)
