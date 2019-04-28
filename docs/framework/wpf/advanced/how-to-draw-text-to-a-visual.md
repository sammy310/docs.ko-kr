---
title: '방법: 시각적 개체에 텍스트 그리기'
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
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776170"
---
# <a name="how-to-draw-text-to-a-visual"></a>방법: 시각적 개체에 텍스트 그리기
다음 예제에서는 텍스트를 그리는 방법에는 <xref:System.Windows.Media.DrawingVisual> 를 사용 하 여를 <xref:System.Windows.Media.DrawingContext> 개체입니다. 그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다. 그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.  
  
 텍스트를 그리려면 그리기 컨텍스트에 사용 합니다 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 메서드를 <xref:System.Windows.Media.DrawingContext> 개체입니다. 그리기 컨텍스트에 콘텐츠 그리기 작업을 완료 하는 경우 호출 된 <xref:System.Windows.Media.DrawingContext.Close%2A> 그리기 컨텍스트에 닫고 콘텐츠를 유지 하는 메서드.  
  
## <a name="example"></a>예제  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](https://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.
