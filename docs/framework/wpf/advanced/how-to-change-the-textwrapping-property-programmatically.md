---
title: '방법: 프로그래밍 방식으로 TextWrapping 속성 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 21ca31d24121492fe6927cd533d5b3c0785b5a28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975002"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="0034f-102">방법: 프로그래밍 방식으로 TextWrapping 속성 변경</span><span class="sxs-lookup"><span data-stu-id="0034f-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="0034f-103">예제</span><span class="sxs-lookup"><span data-stu-id="0034f-103">Example</span></span>  
 <span data-ttu-id="0034f-104">다음 코드 예제에서는 값을 변경 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 속성 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0034f-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="0034f-105">세 <xref:System.Windows.Controls.Button> 요소 안에 배치 되는 <xref:System.Windows.Controls.StackPanel> 요소에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0034f-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="0034f-106">각 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 에 대 한 이벤트를 <xref:System.Windows.Controls.Button> 코드에서 이벤트 처리기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0034f-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="0034f-107">이벤트 처리기와 같은 이름을 사용 합니다 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 값에 적용 됩니다 `txt2` 단추를 클릭할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="0034f-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="0034f-108">에 텍스트 뿐만 `txt1` (을 <xref:System.Windows.Controls.TextBlock> 에 표시 되지 않습니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) 속성에 변경 내용을 반영 하도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0034f-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0034f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0034f-109">See also</span></span>

- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
