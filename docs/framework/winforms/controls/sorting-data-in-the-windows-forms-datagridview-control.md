---
title: DataGridView 컨트롤의 데이터 정렬
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742950"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c8033-102">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="c8033-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="c8033-103">기본적으로 사용자는 입력란 열의 머리글을 클릭 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터를 정렬 하거나 텍스트 상자 셀이 .NET Framework 4.7.2 이상 버전에 초점을 맞춘 경우 F3 키를 눌러 데이터를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="c8033-104">특정 열의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 속성을 수정 하 여 사용자가이 작업을 수행 하는 데 적합 한 경우 다른 열 형식으로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="c8033-105">열 또는 여러 열을 기준으로 프로그래밍 방식으로 데이터를 정렬할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c8033-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c8033-106">In this section</span></span>

[<span data-ttu-id="c8033-107">Windows Forms DataGridView 컨트롤의 열 정렬 모드</span><span class="sxs-lookup"><span data-stu-id="c8033-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="c8033-108">컨트롤의 데이터를 정렬 하기 위한 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="c8033-109">방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정</span><span class="sxs-lookup"><span data-stu-id="c8033-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="c8033-110">기본적으로 정렬할 수 없는 열을 기준으로 정렬할 수 있도록 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="c8033-111">방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c8033-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="c8033-112">프로그래밍 방식으로 데이터를 정렬 하는 방법과 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 이벤트를 사용 하거나 <xref:System.Collections.IComparer> 인터페이스를 구현 하 여 정렬을 사용자 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="c8033-113">참조</span><span class="sxs-lookup"><span data-stu-id="c8033-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="c8033-114"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="c8033-115"><xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="c8033-116"><xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="c8033-117"><xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8033-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8033-118">참조</span><span class="sxs-lookup"><span data-stu-id="c8033-118">See also</span></span>

- [<span data-ttu-id="c8033-119">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c8033-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="c8033-120">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="c8033-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
