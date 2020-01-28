---
title: DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745776"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="9d38f-102">방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="9d38f-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9d38f-103">셀 복사를 사용하면 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터가 <xref:System.Windows.Forms.Clipboard>를 통해 다른 애플리케이션에 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="9d38f-104">선택된 셀의 값은 문자열로 변환되고 메모장 및 Excel 같은 애플리케이션에 붙여넣도록 탭으로 구분된 텍스트 값으로 클립보드에 추가되거나 Word 같은 애플리케이션에 붙여넣도록 HTML 형식 테이블로 클립보드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="9d38f-105">셀 값만 복사하거나 클립보드 데이터에 행 및 열 머리글 텍스트를 포함하거나 사용자가 전체 행이나 열을 선택할 때만 머리글을 포함하도록 셀 복사를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="9d38f-106">선택 모드에 따라 사용자는 연결이 끊어진 셀 그룹 여러 개를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="9d38f-107">사용자가 셀을 클립보드에 복사할 때 셀이 선택되지 않은 행과 열은 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="9d38f-108">모든 다른 행 또는 열은 클립보드에 복사된 데이터 테이블의 행과 열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="9d38f-109">이들 행이나 열에서 선택되지 않은 셀은 빈 자리 표시자로 클립보드에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="9d38f-110">셀 복사를 사용하도록 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-110">To enable cell copying</span></span>  
  
- <span data-ttu-id="9d38f-111"><xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="9d38f-112">예</span><span class="sxs-lookup"><span data-stu-id="9d38f-112">Example</span></span>  
 <span data-ttu-id="9d38f-113">다음 전체 코드 예제에서는 셀을 클립보드에 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="9d38f-114">이 예제는 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> 메서드를 사용하여 선택된 셀을 클립보드에 복사하는 단추를 포함하고 클립보드 내용을 텍스트 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d38f-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9d38f-115">Compiling the Code</span></span>  
 <span data-ttu-id="9d38f-116">이 코드에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d38f-116">This code requires:</span></span>  
  
- <span data-ttu-id="9d38f-117">N:System 및 N:System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="9d38f-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d38f-118">참조</span><span class="sxs-lookup"><span data-stu-id="9d38f-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="9d38f-119">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="9d38f-119">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
