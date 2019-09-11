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
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856117"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="63dea-102">방법: TextBox 컨트롤의 텍스트 내용 설정</span><span class="sxs-lookup"><span data-stu-id="63dea-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="63dea-103">이 예제에서는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.TextBox> 컨트롤의 초기 텍스트 콘텐츠를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63dea-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="63dea-104">`<TextBox.Text>` <xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox> 이 예제의 <xref:System.Windows.Controls.TextBox> 버전에서는 각 단추의 콘텐츠 텍스트 주위에 있는 태그를 사용할 수 있지만에서 속성에 특성을 적용 하기 때문에 필요 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 하지 않습니다. .</span><span class="sxs-lookup"><span data-stu-id="63dea-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="63dea-105">자세한 내용은 [XAML 개요 (WPF)](../advanced/xaml-overview-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63dea-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="63dea-106">예제</span><span class="sxs-lookup"><span data-stu-id="63dea-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="63dea-107">예제</span><span class="sxs-lookup"><span data-stu-id="63dea-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="63dea-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="63dea-108">See also</span></span>

- [<span data-ttu-id="63dea-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="63dea-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="63dea-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="63dea-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
