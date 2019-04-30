---
title: Windows Forms DataGridView 컨트롤의 성능 조정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 79f74db4ebd095156207a6218f59c0e9ae423085
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012648"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="593d2-102">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="593d2-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="593d2-103">많은 양의 데이터를 작업할 때의 `DataGridView` 신중 하 게 사용 하지 않는 한 컨트롤 많은 양의 메모리를에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="593d2-104">제한 된 메모리를 사용 하 여 클라이언트에 메모리가 많이 하는 기능은 사용 하지 않음으로써이 오버 헤드의 일부를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="593d2-105">데이터 유지 관리의 일부 또는 전부를 관리할 수도 있습니다 및 검색 시나리오에 대 한 메모리 사용량을 사용자 지정 하기 위해 가상 모드를 사용 하 여 직접 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="593d2-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="593d2-106">In This Section</span></span>  
 [<span data-ttu-id="593d2-107">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="593d2-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="593d2-108">사용 하는 방법에 설명 합니다 `DataGridView` 많은 양의 데이터를 사용 하 여 작업 하는 경우 불필요 한 메모리 사용량 및 성능 저하를 방지 하는 방식으로 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="593d2-109">Windows Forms DataGridView 컨트롤의 가상 모드</span><span class="sxs-lookup"><span data-stu-id="593d2-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="593d2-110">가상 모드를 사용 하 여 보완 하거나 표준 데이터 바인딩 메커니즘을 대체 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="593d2-111">연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="593d2-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="593d2-112">여러 가상 모드 이벤트에 대 한 처리기를 구현 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="593d2-113">또한 행 수준 rollback 및 commit 사용자 편집에 대 한 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="593d2-114">Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="593d2-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="593d2-115">사용 가능한 클라이언트 메모리에 저장할 수 있는 보다 표시할 데이터가 많은 경우에 유용 하는 요청 시 데이터를 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="593d2-116">참조</span><span class="sxs-lookup"><span data-stu-id="593d2-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="593d2-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="593d2-118">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="593d2-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593d2-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="593d2-119">See also</span></span>

- [<span data-ttu-id="593d2-120">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="593d2-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="593d2-121">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="593d2-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
