---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 표시하는 텍스트 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337957"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="b3c8f-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="b3c8f-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="b3c8f-103">일반적으로 Windows Forms 컨트롤이 컨트롤의 기본 함수에 관련 된 일부 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="b3c8f-104">예를 들어, 한 <xref:System.Windows.Forms.Button> 컨트롤에는 일반적으로 단추를 클릭할 때 작업을 수행할지 여부를 나타내는 캡션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="b3c8f-105">모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="b3c8f-106"><xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="b3c8f-107">디자이너를 사용 하 여 글꼴 및 텍스트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b3c8f-107">To set the text and font with the designer</span></span>  
  
1. <span data-ttu-id="b3c8f-108">속성 창에서 설정 된 <xref:System.Windows.Forms.Control.Text%2A> 적절 한 문자열을 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="b3c8f-109">밑줄된 바로 가기 키를 만들려면 앰퍼샌드가 포함 (&) 문자를 바로 가기 키가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2. <span data-ttu-id="b3c8f-110">속성 창에서 줄임표 단추를 클릭 합니다. (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.Control.Font%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="b3c8f-111">표준 글꼴 대화 상자, 글꼴, 글꼴 스타일, 크기, 부작용 (예: 취소선, 밑줄) 및 스크립트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c8f-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c8f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3c8f-112">See also</span></span>

- [<span data-ttu-id="b3c8f-113">방법: 설정 하 여 표시 되는 텍스트는 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3c8f-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="b3c8f-114">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="b3c8f-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="b3c8f-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="b3c8f-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
