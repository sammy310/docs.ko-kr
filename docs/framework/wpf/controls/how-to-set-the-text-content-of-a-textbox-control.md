---
title: '방법: TextBox 컨트롤의 텍스트 내용 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212195"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="be31e-102">방법: TextBox 컨트롤의 텍스트 내용 설정</span><span class="sxs-lookup"><span data-stu-id="be31e-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="be31e-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox.Text%2A> 초기 텍스트 콘텐츠를 설정 하는 속성을 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="be31e-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="be31e-104">**참고** 있지만 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 버전의 예제를 사용할 수는 `<TextBox.Text>` 태그의 각 단추의 텍스트를 둘러싸는 <xref:System.Windows.Controls.TextBox> 콘텐츠 필요는 없습니다 때문에 <xref:System.Windows.Controls.TextBox> 적용 됩니다는 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성을 <xref:System.Windows.Controls.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="be31e-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="be31e-105">자세한 내용은 [XAML 개요 (WPF)](../advanced/xaml-overview-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be31e-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be31e-106">예제</span><span class="sxs-lookup"><span data-stu-id="be31e-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="be31e-107">예제</span><span class="sxs-lookup"><span data-stu-id="be31e-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="be31e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="be31e-108">See also</span></span>

- [<span data-ttu-id="be31e-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="be31e-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="be31e-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="be31e-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
