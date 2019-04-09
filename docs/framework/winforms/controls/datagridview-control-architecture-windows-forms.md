---
title: DataGridView 컨트롤 아키텍처(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 892168ec282fbf168c43515e0718fe5486a345a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130262"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="5987b-102">DataGridView 컨트롤 아키텍처(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5987b-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="5987b-103"><xref:System.Windows.Forms.DataGridView> 컨트롤과 관련 된 클래스는 테이블 형식 데이터 표시 및 편집에 대 한 유연 하 고 확장 가능한 시스템을 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="5987b-104">이러한 클래스에 포함 된 모든는 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스 및 이러한 모든 "DataGridView" 접두사를 사용 하 여 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="5987b-105">아키텍처 요소</span><span class="sxs-lookup"><span data-stu-id="5987b-105">Architecture Elements</span></span>  
 <span data-ttu-id="5987b-106">주 <xref:System.Windows.Forms.DataGridView> 도우미 클래스에서 파생 <xref:System.Windows.Forms.DataGridViewElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="5987b-107">다음 개체 모델을 보여 줍니다는 <xref:System.Windows.Forms.DataGridViewElement> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![DataGridViewElement 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="5987b-109"><xref:System.Windows.Forms.DataGridViewElement> 클래스는 부모에 대 한 참조를 제공 <xref:System.Windows.Forms.DataGridView> 제어 하 고이 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성에서 값의 조합을 나타내는 값을 보유 하는 <xref:System.Windows.Forms.DataGridViewElementStates> 열거형.</span><span class="sxs-lookup"><span data-stu-id="5987b-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="5987b-110">다음 섹션에서는 <xref:System.Windows.Forms.DataGridView> 도우미 자세히 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="5987b-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="5987b-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="5987b-112"><xref:System.Windows.Forms.DataGridViewElementStates> 열거형 다음 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="5987b-113">이 열거형의 값 비트 논리 연산자를 함께 사용할 수 있으므로 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성은 둘 이상의 상태를 한 번에 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="5987b-114">예를 들어, 한 <xref:System.Windows.Forms.DataGridViewElement> 동시에 사용할 수 있습니다 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, 및 <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="5987b-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="5987b-115">셀 및 밴드</span><span class="sxs-lookup"><span data-stu-id="5987b-115">Cells and Bands</span></span>  
 <span data-ttu-id="5987b-116"><xref:System.Windows.Forms.DataGridView> 컨트롤 구성 개체의 두 가지 기본적인 종류: 셀 및 밴드입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="5987b-117">모든 셀에서 파생 된 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="5987b-118">두 종류의 밴드 <xref:System.Windows.Forms.DataGridViewColumn> 하 고 <xref:System.Windows.Forms.DataGridViewRow>에서 파생 되는 <xref:System.Windows.Forms.DataGridViewBand> 기본 클래스.</span><span class="sxs-lookup"><span data-stu-id="5987b-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="5987b-119">합니다 <xref:System.Windows.Forms.DataGridView> 여러 클래스와 상호 운용 제어 되지만 가장 일반적으로 발생 <xref:System.Windows.Forms.DataGridViewCell>를 <xref:System.Windows.Forms.DataGridViewColumn>, 및 <xref:System.Windows.Forms.DataGridViewRow>합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="5987b-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="5987b-120">DataGridViewCell</span></span>  
 <span data-ttu-id="5987b-121">셀이에 대 한 상호 작용의 기본 단위는 <xref:System.Windows.Forms.DataGridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="5987b-122">표시는 셀을 중심으로 하 고 데이터 항목은 대개 셀을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="5987b-123">사용 하 여 셀에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 의 컬렉션을 <xref:System.Windows.Forms.DataGridViewRow> 클래스를 사용 하 여 선택한 셀에 액세스할 수는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 의 컬렉션은 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5987b-124">다음 개체 모델이이 사용법을 보여 줍니다 및 표시를 <xref:System.Windows.Forms.DataGridViewCell> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![DataGridViewCell 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="5987b-126"><xref:System.Windows.Forms.DataGridViewCell> 유형 셀 형식도 파생 되는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <xref:System.Windows.Forms.DataGridViewCell> <span data-ttu-id="5987b-127">및 Windows Forms 컨트롤, 하지만 일부 호스트 Windows Forms 컨트롤 파생된 형식에 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-127">and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="5987b-128">셀에서 지 원하는 모든 편집 기능은 호스트 된 컨트롤에서 일반적으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell> <span data-ttu-id="5987b-129">개체 제어 하지 않습니다 고유한 모양과 그리기 기능 동일한 방식으로 Windows Forms 컨트롤로.</span><span class="sxs-lookup"><span data-stu-id="5987b-129">objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="5987b-130">대신 합니다 <xref:System.Windows.Forms.DataGridView> 모양의 담당 해당 <xref:System.Windows.Forms.DataGridViewCell> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="5987b-131">상호 작용 하 여 셀의 동작과 모양을 향상 시킬 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 속성 및 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="5987b-132">사용자 지정 기능에 대 한 특별 한 요구 사항이 있는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 파생 되는 고유한 클래스를 구현할 수 있습니다 <xref:System.Windows.Forms.DataGridViewCell> 또는 해당 자식 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="5987b-133">다음 목록에서 파생 된 클래스를 보여 줍니다. <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="5987b-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="5987b-134">사용자 지정 셀 형식</span><span class="sxs-lookup"><span data-stu-id="5987b-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="5987b-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="5987b-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="5987b-136">스키마를 <xref:System.Windows.Forms.DataGridView> 제어의 연결 된 데이터 저장소로 표현 됩니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="5987b-137">액세스할 수 있습니다 합니다 <xref:System.Windows.Forms.DataGridView> 를 사용 하 여 컨트롤의 열을 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="5987b-138">사용 하 여 선택한 열에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="5987b-139">다음 개체 모델이이 사용법을 보여 줍니다 및 표시를 <xref:System.Windows.Forms.DataGridViewColumn> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![DataGridViewColumn 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="5987b-141">키 셀 형식 중 일부에 해당 열 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="5987b-142">파생 된 이러한는 <xref:System.Windows.Forms.DataGridViewColumn> 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="5987b-143">다음 목록에서 파생 된 클래스를 보여 줍니다. <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="5987b-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="5987b-144">사용자 지정 열 형식</span><span class="sxs-lookup"><span data-stu-id="5987b-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="5987b-145">DataGridView 편집 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5987b-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="5987b-146">고급 편집 기능을 일반적으로 지원 되는 셀 Windows Forms 컨트롤에서 파생 되는 호스트 된 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="5987b-147">이러한 컨트롤을 구현할 수도 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="5987b-148">다음 개체 모델에서는 이러한 컨트롤의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![DataGridView 편집 컨트롤 개체 모델 계층을 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="5987b-150">다음과 같은 편집 컨트롤을 함께 제공 되는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="5987b-151">고유한 편집 컨트롤을 만드는 방법에 대 한 자세한 내용은 [방법: DataGridView 셀에서 Windows Forms 컨트롤 호스팅](how-to-host-controls-in-windows-forms-datagridview-cells.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="5987b-152">다음 표에서 셀 형식, 열 형식 및 편집 컨트롤 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="5987b-153">셀 형식</span><span class="sxs-lookup"><span data-stu-id="5987b-153">Cell type</span></span>|<span data-ttu-id="5987b-154">호스팅된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5987b-154">Hosted control</span></span>|<span data-ttu-id="5987b-155">열 유형</span><span class="sxs-lookup"><span data-stu-id="5987b-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="5987b-156">N/A</span><span class="sxs-lookup"><span data-stu-id="5987b-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="5987b-157">N/A</span><span class="sxs-lookup"><span data-stu-id="5987b-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="5987b-158">N/A</span><span class="sxs-lookup"><span data-stu-id="5987b-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="5987b-159">N/A</span><span class="sxs-lookup"><span data-stu-id="5987b-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="5987b-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="5987b-160">DataGridViewRow</span></span>  
 <span data-ttu-id="5987b-161"><xref:System.Windows.Forms.DataGridViewRow> 저장소에 있는 데이터에서 레코드의 데이터 필드 클래스 표시는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="5987b-162">액세스할 수 있습니다 합니다 <xref:System.Windows.Forms.DataGridView> 사용 하 여 컨트롤의 행을 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="5987b-163">사용 하 여 선택한 행에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="5987b-164">다음 개체 모델이이 사용법을 보여 줍니다 및 표시를 <xref:System.Windows.Forms.DataGridViewRow> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![DataGridViewRow 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="5987b-166">사용자 고유의 형식을 파생 시킬 수 있습니다는 <xref:System.Windows.Forms.DataGridViewRow> 클래스를이 일반적으로 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="5987b-167">합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤에 행 관련 이벤트 및 동작을 사용자 지정에 대 한 속성 몇 가지 해당 <xref:System.Windows.Forms.DataGridViewRow> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="5987b-168">사용 하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 새 행을 추가 하기 위한 특별 한 행이 마지막 행으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="5987b-169">이 행의 일부인는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션 하지만 주의가 필요할 수 있는 특별 한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="5987b-170">자세한 내용은 [Windows Forms DataGridView 컨트롤에서 새 레코드에 대 한 행을 사용 하 여](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5987b-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5987b-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="5987b-171">See also</span></span>

- [<span data-ttu-id="5987b-172">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5987b-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="5987b-173">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5987b-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5987b-174">Windows Forms DataGridView 컨트롤에서 새 레코드에 대한 행 사용</span><span class="sxs-lookup"><span data-stu-id="5987b-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
