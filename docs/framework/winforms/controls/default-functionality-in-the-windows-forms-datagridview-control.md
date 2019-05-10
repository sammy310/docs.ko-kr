---
title: Windows Forms DataGridView 컨트롤의 기본 기능
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b84d5a279bfe7cd99262ca904daeceabc9d0355d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648065"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6db03-102">Windows Forms DataGridView 컨트롤의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="6db03-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6db03-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 상당한 양의 기본 기능을 사용 하 여 사용자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="6db03-104">기본 기능</span><span class="sxs-lookup"><span data-stu-id="6db03-104">Default Functionality</span></span>  
 <span data-ttu-id="6db03-105">기본적으로 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="6db03-106">열 머리글 및 테이블을 세로로 스크롤할 때 계속 표시 되는 행 머리글을 자동으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="6db03-107">현재 행에 대 한 선택 표시기를 포함 하는 행 머리글을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="6db03-108">선택 영역 직사각형을 첫 번째 셀에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="6db03-109">열 구분선을 두 번 클릭할 때 자동으로 조정 하는 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="6db03-110">자동으로 Windows XP 및 Windows Server 2003 제품군에서 비주얼 스타일을 지 원하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드는 응용 프로그램에서 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6db03-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="6db03-111">내용을 또한는 <xref:System.Windows.Forms.DataGridView> 기본적으로 컨트롤을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="6db03-112">사용자가 두 번 클릭 또는 셀에서 f2 키를 누를 경우 컨트롤 자동으로 셀을 편집 모드로 전환 하 고 사용자가 셀의 내용을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="6db03-113">눈금의 끝에 사용자를 스크롤하면 하는 경우 사용자는 새 레코드를 추가 하는 것에 대 한 행이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="6db03-114">사용자가이 행에 새 행에 추가 됩니다는 <xref:System.Windows.Forms.DataGridView> 기본값을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="6db03-115">사용자가 esc 키를 누를 때 새 행이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="6db03-116">사용자가 행 머리글을 클릭 하면 전체 행이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="6db03-117">바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 설정 하 여 데이터 소스는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성, 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="6db03-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="6db03-118">자동 데이터 원본의 열 이름으로 열 머리글 텍스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="6db03-119">데이터 원본 내용으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="6db03-120"><xref:System.Windows.Forms.DataGridView> 열은 데이터 원본의 각 열에 대해 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="6db03-121">테이블에 표시 되는 각 행에 대 한 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="6db03-122">열 머리글을 마우스 오른쪽 단추로 클릭할 때 기본 데이터를 기준으로 행을 자동으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db03-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db03-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="6db03-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="6db03-124">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6db03-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
