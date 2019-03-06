---
title: 프로그래밍 방식으로 RichTextBox의 선택 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: a85dc4baa8a59d25f577996c541a422bbe2af24e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367078"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="045be-102">프로그래밍 방식으로 RichTextBox의 선택 변경</span><span class="sxs-lookup"><span data-stu-id="045be-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="045be-103">현재 선택 영역을 프로그래밍 방식으로 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="045be-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="045be-104">이 옵션을이 선택 사용자의 사용자 인터페이스를 사용 하 여 콘텐츠를 선택한 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="045be-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="045be-105">예제</span><span class="sxs-lookup"><span data-stu-id="045be-105">Example</span></span>  
 <span data-ttu-id="045be-106">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 명명 된 코드에 설명 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="045be-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="045be-107">예제</span><span class="sxs-lookup"><span data-stu-id="045be-107">Example</span></span>  
 <span data-ttu-id="045be-108">사용자가 내부를 클릭할 때 프로그래밍 방식으로 다음 코드는 일부 임의 텍스트 선택의 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="045be-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="045be-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="045be-109">See also</span></span>
- [<span data-ttu-id="045be-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="045be-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="045be-111">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="045be-111">TextBox Overview</span></span>](textbox-overview.md)
