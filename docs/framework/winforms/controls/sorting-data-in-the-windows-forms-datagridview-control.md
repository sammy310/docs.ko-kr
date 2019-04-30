---
title: Windows Forms DataGridView 컨트롤의 데이터 정렬
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012154"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="47f6f-102">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="47f6f-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="47f6f-103">기본적으로 사용자의 데이터를 정렬할 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 텍스트 상자 열 머리글을 클릭 하 여 (또는.NET Framework 4.7.2 이상에서 텍스트 상자 셀 포커스가 F3 키를 눌러).</span><span class="sxs-lookup"><span data-stu-id="47f6f-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="47f6f-104">수정할 수는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 이렇게 하려면 적합 한 경우 다른 열 유형에 정렬할 수 있도록 특정 열 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="47f6f-105">정렬할 수 있습니다도 데이터를 프로그래밍 방식으로 모든 열 또는 여러 열을 기준으로.</span><span class="sxs-lookup"><span data-stu-id="47f6f-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="47f6f-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="47f6f-106">In this section</span></span>

[<span data-ttu-id="47f6f-107">Windows Forms DataGridView 컨트롤의 열 정렬 모드</span><span class="sxs-lookup"><span data-stu-id="47f6f-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="47f6f-108">컨트롤의 데이터 정렬에 대 한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="47f6f-109">방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정</span><span class="sxs-lookup"><span data-stu-id="47f6f-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="47f6f-110">기본적으로 정렬 가능 하지 않은 열을 정렬할 수 있도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="47f6f-111">방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="47f6f-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="47f6f-112">프로그래밍 방식으로 데이터를 정렬 하는 방법 및 사용 하 여 정렬 사용자 지정 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 이벤트 또는 구현 하 여는 <xref:System.Collections.IComparer> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="47f6f-113">참조</span><span class="sxs-lookup"><span data-stu-id="47f6f-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="47f6f-114"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="47f6f-115">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="47f6f-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="47f6f-116">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="47f6f-117">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="47f6f-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="47f6f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="47f6f-118">See also</span></span>

- [<span data-ttu-id="47f6f-119">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="47f6f-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="47f6f-120">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="47f6f-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
