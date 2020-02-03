---
title: ListView 컨트롤에 열 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744589"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="4a3ed-102">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="4a3ed-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="4a3ed-103">자세히 보기에서 <xref:System.Windows.Forms.ListView> 컨트롤은 각 목록 항목에 대해 여러 열을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="4a3ed-104">열을 사용 하 여 각 목록 항목에 대 한 여러 유형의 정보를 사용자에 게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="4a3ed-105">예를 들어 파일 목록에 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="4a3ed-106">열을 만든 후 채우는 방법에 대 한 자세한 내용은 [방법: Windows Forms ListView 컨트롤을 사용 하 여 열에 하위 항목 표시](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="4a3ed-107">프로그래밍 방식으로 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="4a3ed-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="4a3ed-108">컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="4a3ed-109">목록 뷰의 <xref:System.Windows.Forms.ListView.Columns%2A> 속성 <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="4a3ed-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a3ed-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="4a3ed-111">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4a3ed-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="4a3ed-112">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4a3ed-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
