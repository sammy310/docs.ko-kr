---
title: DataGridView 컨트롤에서 디자이너 사용
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 50e8bddb97c2dfb84cebdbb2ca4d42a6c5743304
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728360"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="23188-102">Windows Forms DataGridView 컨트롤에 디자이너 사용</span><span class="sxs-lookup"><span data-stu-id="23188-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="23188-103">Visual Studio는 코드를 작성 하지 않고도 많은 설치 작업을 수행할 수 있도록 하는 `DataGridView` 컨트롤에 대 한 디자이너 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="23188-104">이러한 작업에는 컨트롤을 데이터 원본에 바인딩하고, 데이터를 표시 하는 데 사용 되는 열을 수정 하 고, 컨트롤의 모양과 기본 동작을 조정 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23188-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23188-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="23188-105">In This Section</span></span>  
 [<span data-ttu-id="23188-106">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="23188-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-107">열 **추가** 및 **열 편집** 대화 상자를 사용 하 여 열 컬렉션을 채우고 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="23188-108">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="23188-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-109">컨트롤의 스마트 태그에서 **데이터 소스 선택** 옵션을 사용 하 여 데이터에 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="23188-110">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="23188-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-111">**열 편집** 대화 상자를 사용 하 여 열을 다시 정렬 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="23188-112">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="23188-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="23188-113">**열 편집** 대화 상자를 사용 하 여 열 형식을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="23188-114">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="23188-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-115">컨트롤의 스마트 태그를 사용 하 여 사용자가 열을 다시 정렬할 수 있도록 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="23188-116">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="23188-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-117">**열 편집** 대화 상자를 사용 하 여 특정 열의 스크롤을 방지 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="23188-118">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="23188-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-119">**열 편집** 대화 상자를 사용 하 여 특정 열을 숨기는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="23188-120">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="23188-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-121">**열 편집** 대화 상자를 사용 하 여 사용자가 특정 열의 값을 편집 하지 못하도록 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="23188-122">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="23188-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-123">컨트롤의 스마트 태그를 사용 하 여 사용자가 행을 추가 하거나 삭제 하지 못하도록 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="23188-124">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="23188-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="23188-125">**CellStyle 작성기** 대화 상자를 사용 하 여 컨트롤에서 장부 모양의 모양을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="23188-126">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정</span><span class="sxs-lookup"><span data-stu-id="23188-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="23188-127">**CellStyle 작성기** 대화 상자를 사용 하 여 컨트롤에 대 한 기본 모양 및 데이터 표시 형식을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="23188-128">참조</span><span class="sxs-lookup"><span data-stu-id="23188-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="23188-129"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23188-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23188-130">참조</span><span class="sxs-lookup"><span data-stu-id="23188-130">See also</span></span>

- [<span data-ttu-id="23188-131">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="23188-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
