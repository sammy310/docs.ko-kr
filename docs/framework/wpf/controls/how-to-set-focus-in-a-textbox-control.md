---
title: '방법: TextBox 컨트롤에서 포커스 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: f4ba367ea9bdfcd6dbab7a5015472ec33adfe46f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115507"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="e1ae1-102">방법: TextBox 컨트롤에서 포커스 설정</span><span class="sxs-lookup"><span data-stu-id="e1ae1-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="e1ae1-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement.Focus%2A> 에 포커스를 설정 하는 방법을 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1ae1-104">예제</span><span class="sxs-lookup"><span data-stu-id="e1ae1-104">Example</span></span>  
 <span data-ttu-id="e1ae1-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 간단한 설명 <xref:System.Windows.Controls.TextBox> 컨트롤인 *tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="e1ae1-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="e1ae1-106">예제</span><span class="sxs-lookup"><span data-stu-id="e1ae1-106">Example</span></span>  
 <span data-ttu-id="e1ae1-107">다음 예제에서는 합니다 <xref:System.Windows.UIElement.Focus%2A> 에 포커스를 설정 하는 방법의 <xref:System.Windows.Controls.TextBox> 이름 사용 하 여 컨트롤 *tbFocusMe*합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="e1ae1-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1ae1-108">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="e1ae1-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="e1ae1-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="e1ae1-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="e1ae1-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
