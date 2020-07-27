---
title: '방법: TextBox 컨트롤에서 포커스 설정'
description: 포커스 메서드를 사용 하 여 Windows Presentation Foundation TextBox 컨트롤에 포커스를 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e107c22a3c5b701e02cbc8506d10fa35ee15c79d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168060"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="8fe04-103">방법: TextBox 컨트롤에서 포커스 설정</span><span class="sxs-lookup"><span data-stu-id="8fe04-103">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="8fe04-104">이 예제에서는 메서드를 사용 하 여 <xref:System.Windows.UIElement.Focus%2A> 컨트롤에 포커스를 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="8fe04-104">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe04-105">예제</span><span class="sxs-lookup"><span data-stu-id="8fe04-105">Example</span></span>  
 <span data-ttu-id="8fe04-106">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 <xref:System.Windows.Controls.TextBox> *tbFocusMe* 라는 간단한 컨트롤을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe04-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="8fe04-107">예제</span><span class="sxs-lookup"><span data-stu-id="8fe04-107">Example</span></span>  
 <span data-ttu-id="8fe04-108">다음 예제에서는 메서드를 호출 <xref:System.Windows.UIElement.Focus%2A> 하 여 <xref:System.Windows.Controls.TextBox> *tbFocusMe*이름으로 컨트롤에 포커스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe04-108">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="8fe04-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fe04-109">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="8fe04-110">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="8fe04-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="8fe04-111">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="8fe04-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
