---
title: '방법: 여러 줄 TextBox 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 29fb4c9498fe163c36e71680242d3ef8cf98c089
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181170"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="d5287-102">방법: 여러 줄 TextBox 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d5287-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="d5287-103">이 예제에 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 <xref:System.Windows.Controls.TextBox> 컨트롤을 여러 줄의 텍스트에 맞게 자동으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5287-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5287-104">예제</span><span class="sxs-lookup"><span data-stu-id="d5287-104">Example</span></span>  
 <span data-ttu-id="d5287-105">설정 합니다 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 **줄 바꿈** 입력 한 텍스트를 새 줄 바꿈이 발생 할 때 줄 가장자리를 <xref:System.Windows.Controls.TextBox> 컨트롤에 도달 하면 자동으로 확장 되는 <xref:System.Windows.Controls.TextBox> 제어 하는 경우 새 줄에 대 한 공간을 포함 하도록 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5287-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="d5287-106">설정 합니다 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 **true** RETURN 키를 누르면 자동으로 다시 한 번 확장 삽입할 새 줄을 <xref:System.Windows.Controls.TextBox> 필요한 경우 새 줄에 대 한 공간을 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5287-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="d5287-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 특성에 있는 스크롤 막대를 추가 합니다 <xref:System.Windows.Controls.TextBox>되도록 내용의 <xref:System.Windows.Controls.TextBox> 경우 스크롤할 수를 <xref:System.Windows.Controls.TextBox> 포함 하는 창 프레임의 크기 이상으로 확장.</span><span class="sxs-lookup"><span data-stu-id="d5287-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="d5287-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5287-108">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="d5287-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d5287-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d5287-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d5287-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
