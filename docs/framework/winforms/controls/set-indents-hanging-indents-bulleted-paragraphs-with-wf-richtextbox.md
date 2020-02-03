---
title: RichTextBox 컨트롤을 사용 하 여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743009"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="64a75-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정</span><span class="sxs-lookup"><span data-stu-id="64a75-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="64a75-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 표시 되는 텍스트의 서식을 지정 하는 다양 한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="64a75-104"><xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 설정 하 여 선택한 단락의 서식을 글머리 기호 목록으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="64a75-105"><xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>및 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성을 사용 하 여 컨트롤의 왼쪽과 오른쪽 가장자리를 기준으로 단락 들여쓰기와 다른 텍스트 줄의 왼쪽 가장자리를 기준으로 단락 들여쓰기를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="64a75-106">단락의 서식을 글머리 기호 목록으로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="64a75-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="64a75-107"><xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="64a75-108">단락을 들여쓰려면</span><span class="sxs-lookup"><span data-stu-id="64a75-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="64a75-109"><xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> 속성을 컨트롤의 왼쪽 가장자리와 텍스트의 왼쪽 가장자리 사이의 거리를 픽셀 단위로 나타내는 정수로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="64a75-110"><xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성을 단락의 첫 번째 텍스트 줄의 왼쪽 가장자리와 동일한 단락에 있는 다음 줄의 왼쪽 가장자리 사이의 거리 (픽셀)를 나타내는 정수로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="64a75-111"><xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성의 값은 첫 번째 줄 아래에 래핑된 단락의 줄에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="64a75-112"><xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> 속성을 컨트롤의 오른쪽 가장자리와 텍스트의 오른쪽 가장자리 사이의 거리를 픽셀 단위로 나타내는 정수로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="64a75-113">이러한 모든 속성은 선택한 텍스트가 포함된 단락에 적용되며, 현재 삽입 지점 이후로 입력된 텍스트에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="64a75-114">예를 들어 사용자가 단락 내의 단어를 선택한 다음 들여쓰기를 조정하면, 이 단어가 포함된 전체 단락뿐만 아니라 선택한 단락 이후에 입력되는 모든 단락에도 새 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64a75-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="64a75-115">프로그래밍 방식으로 텍스트를 선택 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.Forms.TextBoxBase.Select%2A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64a75-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a75-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64a75-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="64a75-117">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="64a75-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="64a75-118">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="64a75-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
