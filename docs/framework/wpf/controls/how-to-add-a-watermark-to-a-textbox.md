---
title: '방법: TextBox에 워터마크 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: ef2536f03ba6ed08e27d2fcf30cd1f72df2cf460
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142417"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="72ba5-102">방법: TextBox에 워터마크 추가</span><span class="sxs-lookup"><span data-stu-id="72ba5-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="72ba5-103">다음 예제에서는의 유용성을 <xref:System.Windows.Controls.TextBox> 내부의 설명 배경 이미지를 표시 하 여는 <xref:System.Windows.Controls.TextBox> 이미지 제거 되는 시점까지 사용자가 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="72ba5-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="72ba5-104">또한 사용자가 입력을 제거 하는 경우 배경 이미지가 다시 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72ba5-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="72ba5-105">아래 그림을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72ba5-105">See illustration below.</span></span>  
  
 <span data-ttu-id="72ba5-106">![배경 이미지가 있는 TextBox](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="72ba5-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72ba5-107">배경 이미지 조작 대신 다음 단순히이 예에서 사용 되는 이유는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 <xref:System.Windows.Controls.TextBox>는 배경 이미지를 데이터 바인딩에 방해 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72ba5-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72ba5-108">예제</span><span class="sxs-lookup"><span data-stu-id="72ba5-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="72ba5-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="72ba5-109">See also</span></span>

- [<span data-ttu-id="72ba5-110">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="72ba5-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="72ba5-111">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="72ba5-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
