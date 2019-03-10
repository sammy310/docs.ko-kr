---
title: Windows Forms DataGridView 컨트롤에 디자이너 사용
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 460dfa7a0bad4e3421ee32695cd57d8072a3cb0d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721946"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="2aeda-102">Windows Forms DataGridView 컨트롤에 디자이너 사용</span><span class="sxs-lookup"><span data-stu-id="2aeda-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2aeda-103">Visual Studio에 대 한 디자이너 지원을 제공 합니다 `DataGridView` 컨트롤 코드를 작성 하지 않고도 많은 설정 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="2aeda-104">이러한 작업에는 열을 수정할 데이터 원본에 컨트롤 데이터를 표시 하는 데 사용 되는 바인딩 및 컨트롤의 기본 동작과 모양을 조정 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2aeda-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2aeda-105">In This Section</span></span>  
 [<span data-ttu-id="2aeda-106">방법: 추가 하 고 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-107">사용 하는 방법에 설명 합니다 **열 추가** 및 **열 편집** 채우고 열 컬렉션을 수정 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="2aeda-108">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="2aeda-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-109">사용 하는 방법에 설명 합니다 **데이터 소스 선택** 데이터에 연결 하는 컨트롤의 스마트 태그 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="2aeda-110">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="2aeda-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-111">사용 하는 방법에 설명 합니다 **열 편집** 열 다시 정렬 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="2aeda-112">방법: 디자이너를 사용 하 여 Windows Forms Datagridview 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="2aeda-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="2aeda-113">사용 하는 방법에 설명 합니다 **열 편집** 열 유형을 변경 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="2aeda-114">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="2aeda-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-115">컨트롤의 스마트 태그를 사용 하 여 사용자가 열을 다시 정렬할 수 있도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="2aeda-116">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="2aeda-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-117">사용 하는 방법에 설명 합니다 **열 편집** 스크롤에서 특정 열을 방지 하기 위해 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="2aeda-118">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 숨기기</span><span class="sxs-lookup"><span data-stu-id="2aeda-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-119">사용 하는 방법에 설명 합니다 **열 편집** 특정 열을 숨기는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="2aeda-120">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤의 읽기 전용으로 열 만들기</span><span class="sxs-lookup"><span data-stu-id="2aeda-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-121">사용 하는 방법에 설명 합니다 **열 편집** 특정 열에 값을 편집 하지 못하게 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="2aeda-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="2aeda-122">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-123">컨트롤의 스마트 태그를 사용 하 여 사용자가 행 추가 또는 삭제 하지 못하도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="2aeda-124">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에 대 한 행 스타일 교대로 반복 되는 설정</span><span class="sxs-lookup"><span data-stu-id="2aeda-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2aeda-125">사용 하는 방법에 설명 합니다 **CellStyle 작성기** 대화 상자 컨트롤에는 장부를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="2aeda-126">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 및 데이터 형식 설정</span><span class="sxs-lookup"><span data-stu-id="2aeda-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="2aeda-127">사용 하는 방법에 설명 합니다 **CellStyle 작성기** 기본 모양 및 데이터 표시를 설정 하려면 대화 상자 컨트롤에 대 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2aeda-128">참조</span><span class="sxs-lookup"><span data-stu-id="2aeda-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2aeda-129"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2aeda-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aeda-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="2aeda-130">See also</span></span>
- [<span data-ttu-id="2aeda-131">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2aeda-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
