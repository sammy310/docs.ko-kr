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
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="6d78c-102">방법: 컨트롤의 배경에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="6d78c-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="6d78c-103">텍스트 문자열을 <xref:System.Windows.Media.FormattedText> 개체로 변환한 다음 개체를 컨트롤의 <xref:System.Windows.Media.DrawingContext>에 그려서 컨트롤의 배경에 직접 텍스트를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d78c-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6d78c-104">이 기술을 사용 하 여 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.StackPanel>와 같은 <xref:System.Windows.Controls.Panel>에서 파생 된 개체의 배경으로 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d78c-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="6d78c-105">![텍스트를 배경으로 표시 하는 컨트롤의 스크린샷](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="6d78c-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="6d78c-106">사용자 지정 텍스트 배경이 있는 컨트롤의 예</span><span class="sxs-lookup"><span data-stu-id="6d78c-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d78c-107">예제</span><span class="sxs-lookup"><span data-stu-id="6d78c-107">Example</span></span>  
 <span data-ttu-id="6d78c-108">컨트롤의 배경에 그리려면 새 <xref:System.Windows.Media.DrawingBrush> 개체를 만들고 변환 된 텍스트를 개체의 <xref:System.Windows.Media.DrawingContext>에 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6d78c-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6d78c-109">그런 다음 컨트롤의 background 속성에 새 <xref:System.Windows.Media.DrawingBrush>를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d78c-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="6d78c-110">다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Button> 개체의 배경으로 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d78c-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="6d78c-111">참조</span><span class="sxs-lookup"><span data-stu-id="6d78c-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="6d78c-112">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="6d78c-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
