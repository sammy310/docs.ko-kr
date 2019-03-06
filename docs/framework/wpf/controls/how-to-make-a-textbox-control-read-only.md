---
title: '방법: TextBox 컨트롤을 읽기 전용으로 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3784471020210f995c8bb0a377d56a2466d97da1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364539"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="fc2d7-102">방법: TextBox 컨트롤을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="fc2d7-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="fc2d7-103">구성 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤이 사용자 입력 또는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2d7-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc2d7-104">예제</span><span class="sxs-lookup"><span data-stu-id="fc2d7-104">Example</span></span>  
 <span data-ttu-id="fc2d7-105">내용을 수정 하지 못하게 하려면를 <xref:System.Windows.Controls.TextBox> 컨트롤을 설정 합니다 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2d7-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="fc2d7-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성에 사용자 입력에만 영향을 줍니다;에 설정 된 텍스트에는 영향을 주지 않습니다를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설명은 <xref:System.Windows.Controls.TextBox> 컨트롤 또는 통해 프로그래밍 방식으로 설정 하는 텍스트를 <xref:System.Windows.Controls.TextBox.Text%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="fc2d7-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="fc2d7-107">기본값인 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 됩니다 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2d7-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2d7-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc2d7-108">See also</span></span>
- [<span data-ttu-id="fc2d7-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="fc2d7-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="fc2d7-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="fc2d7-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
