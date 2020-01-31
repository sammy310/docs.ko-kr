---
title: PrintPreviewControl 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741442"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="2f6e1-102">PrintPreviewControl 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2f6e1-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="2f6e1-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewControl>은 인쇄 될 때 표시 되는 [PrintDocument](printdocument-component-windows-forms.md) 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="2f6e1-104">이 컨트롤에는 단추나 다른 사용자 인터페이스 요소가 없으므로, 일반적으로 고유한 인쇄 미리 보기 사용자 인터페이스를 작성하려는 경우에만 <xref:System.Windows.Forms.PrintPreviewControl>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="2f6e1-105">표준 사용자 인터페이스를 사용 하려면 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용 합니다. 개요는 [PrintPreviewDialog 컨트롤 개요](printpreviewdialog-control-overview-windows-forms.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="2f6e1-106">키 속성</span><span class="sxs-lookup"><span data-stu-id="2f6e1-106">Key Properties</span></span>  
 <span data-ttu-id="2f6e1-107">컨트롤의 키 속성은 미리 볼 문서를 설정 하는 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="2f6e1-108">문서는 <xref:System.Drawing.Printing.PrintDocument> 개체 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="2f6e1-109">인쇄용 문서 만들기에 대 한 개요는 [PrintDocument 구성 요소 개요](printdocument-component-overview-windows-forms.md) 및 [Windows Forms 인쇄 지원](../advanced/windows-forms-print-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="2f6e1-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성은 컨트롤에서 가로 및 세로로 표시 되는 페이지 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="2f6e1-111">앤티앨리어싱을 사용 하면 텍스트가 더 부드럽게 표시 될 수 있지만 표시 속도가 느려질 수도 있습니다. 이를 사용 하려면 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6e1-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6e1-112">참조</span><span class="sxs-lookup"><span data-stu-id="2f6e1-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="2f6e1-113">PrintPreviewDialog 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="2f6e1-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="2f6e1-114">PrintPreviewControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2f6e1-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="2f6e1-115">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2f6e1-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
