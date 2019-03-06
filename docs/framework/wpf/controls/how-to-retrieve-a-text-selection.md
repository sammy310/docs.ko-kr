---
title: '방법: 텍스트 선택 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: fdd0e3974964e141c4b65e1c8851f3c371a4d501
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357614"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="b2dee-102">방법: 텍스트 선택 검색</span><span class="sxs-lookup"><span data-stu-id="b2dee-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="b2dee-103">이 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 에서 사용자가 선택한 텍스트를 검색할 속성을 <xref:System.Windows.Controls.TextBox> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="b2dee-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2dee-104">예제</span><span class="sxs-lookup"><span data-stu-id="b2dee-104">Example</span></span>  
 <span data-ttu-id="b2dee-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 정의 보여 줍니다.을 <xref:System.Windows.Controls.TextBox> 를 선택 하려면 몇 가지 텍스트가 포함 된 컨트롤 및 <xref:System.Windows.Controls.Button> 지정 된 컨트롤 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b2dee-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="b2dee-106">이 예제에서는 연결 된 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 선택한 텍스트를 검색할 이벤트 처리기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2dee-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="b2dee-107">사용자가 단추를 클릭 합니다 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드 문자열에 텍스트 상자에 선택한 텍스트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2dee-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="b2dee-108">특정 상황 텍스트 선택은 검색 하는 (단추 클릭) 뿐만 아니라 해당 선택 (문자열로 텍스트 선택 영역 복사)를 사용 하 여 수행 되는 동작 다양 한 시나리오에 맞게 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2dee-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="b2dee-109">예제</span><span class="sxs-lookup"><span data-stu-id="b2dee-109">Example</span></span>  
 <span data-ttu-id="b2dee-110">다음 C# 예제는 <xref:System.Windows.Controls.Button.OnClick%2A> 에 정의 된 단추에 대 한 이벤트 처리기를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b2dee-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="b2dee-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2dee-111">See also</span></span>
- [<span data-ttu-id="b2dee-112">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="b2dee-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="b2dee-113">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="b2dee-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
