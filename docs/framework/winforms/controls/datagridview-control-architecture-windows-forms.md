---
title: DataGridView 컨트롤 아키텍처
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742533"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="3a4d1-102">DataGridView 컨트롤 아키텍처(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3a4d1-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="3a4d1-103"><xref:System.Windows.Forms.DataGridView> 컨트롤과 관련 클래스는 테이블 형식 데이터를 표시 하 고 편집 하기 위한 유연 하 고 확장 가능한 시스템으로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="3a4d1-104">이러한 클래스는 모두 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스에 포함 되며 모두 "DataGridView" 접두사를 사용 하 여 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="3a4d1-105">아키텍처 요소</span><span class="sxs-lookup"><span data-stu-id="3a4d1-105">Architecture Elements</span></span>  
 <span data-ttu-id="3a4d1-106">기본 <xref:System.Windows.Forms.DataGridView> 동반 클래스는 <xref:System.Windows.Forms.DataGridViewElement>에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="3a4d1-107">다음 개체 모델은 <xref:System.Windows.Forms.DataGridViewElement> 상속 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![DataGridViewElement 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="3a4d1-109"><xref:System.Windows.Forms.DataGridViewElement> 클래스는 부모 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대 한 참조를 제공 하 고 <xref:System.Windows.Forms.DataGridViewElementStates> 열거형의 값 조합을 나타내는 값을 포함 하는 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="3a4d1-110">다음 섹션에서는 <xref:System.Windows.Forms.DataGridView> 동반 클래스에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="3a4d1-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="3a4d1-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="3a4d1-112"><xref:System.Windows.Forms.DataGridViewElementStates> 열거는 다음 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="3a4d1-113">이 열거형의 값은 비트 논리 연산자와 함께 사용할 수 있으므로 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성은 한 번에 둘 이상의 상태를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="3a4d1-114">예를 들어 <xref:System.Windows.Forms.DataGridViewElement>은 동시에 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>및 <xref:System.Windows.Forms.DataGridViewElementStates.Visible>수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="3a4d1-115">셀 및 밴드</span><span class="sxs-lookup"><span data-stu-id="3a4d1-115">Cells and Bands</span></span>  
 <span data-ttu-id="3a4d1-116"><xref:System.Windows.Forms.DataGridView> 컨트롤은 두 가지 기본 개체인 셀과 밴드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="3a4d1-117">모든 셀은 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="3a4d1-118">두 종류의 밴드, <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewRow>는 모두 <xref:System.Windows.Forms.DataGridViewBand> 기본 클래스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="3a4d1-119"><xref:System.Windows.Forms.DataGridView> 컨트롤은 여러 클래스와 상호 운용 되지만 가장 일반적으로 발생 하는 것은 <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>및 <xref:System.Windows.Forms.DataGridViewRow>입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="3a4d1-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="3a4d1-120">DataGridViewCell</span></span>  
 <span data-ttu-id="3a4d1-121">셀은 <xref:System.Windows.Forms.DataGridView>의 기본 상호 작용 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="3a4d1-122">표시는 셀 가운데에 표시 되 고 데이터 항목은 종종 셀을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="3a4d1-123"><xref:System.Windows.Forms.DataGridViewRow> 클래스의 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 컬렉션을 사용 하 여 셀에 액세스할 수 있으며, <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션을 사용 하 여 선택한 셀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3a4d1-124">다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewCell> 상속 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![DataGridViewCell 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="3a4d1-126"><xref:System.Windows.Forms.DataGridViewCell> 형식은 모든 셀 형식이 파생 되는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="3a4d1-127"><xref:System.Windows.Forms.DataGridViewCell> 및 파생 된 형식은 Windows Forms 컨트롤이 아니지만 일부 호스트 Windows Forms 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="3a4d1-128">셀에서 지원 되는 모든 편집 기능은 일반적으로 호스팅된 컨트롤에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="3a4d1-129"><xref:System.Windows.Forms.DataGridViewCell> 개체는 Windows Forms 컨트롤과 같은 방식으로 자체 모양과 그리기 기능을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="3a4d1-130">대신 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewCell> 개체의 모양을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="3a4d1-131"><xref:System.Windows.Forms.DataGridView> 컨트롤의 속성 및 이벤트와 상호 작용 하 여 셀의 모양과 동작에 크게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="3a4d1-132"><xref:System.Windows.Forms.DataGridView> 컨트롤의 기능을 벗어나는 사용자 지정 항목에 대 한 특별 한 요구 사항이 있는 경우 <xref:System.Windows.Forms.DataGridViewCell> 또는 해당 자식 클래스 중 하나에서 파생 되는 고유한 클래스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="3a4d1-133">다음 목록에서는 <xref:System.Windows.Forms.DataGridViewCell>에서 파생 된 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="3a4d1-134">사용자 지정 셀 형식</span><span class="sxs-lookup"><span data-stu-id="3a4d1-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="3a4d1-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="3a4d1-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="3a4d1-136"><xref:System.Windows.Forms.DataGridView> 컨트롤의 연결 된 데이터 저장소의 스키마는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="3a4d1-137"><xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="3a4d1-138"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션을 사용 하 여 선택한 열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="3a4d1-139">다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewColumn> 상속 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![DataGridViewColumn 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="3a4d1-141">일부 키 셀 형식에는 해당 하는 열 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="3a4d1-142">이러한 클래스는 <xref:System.Windows.Forms.DataGridViewColumn> 기본 클래스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="3a4d1-143">다음 목록에서는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생 된 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="3a4d1-144">사용자 지정 열 형식</span><span class="sxs-lookup"><span data-stu-id="3a4d1-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="3a4d1-145">DataGridView 편집 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3a4d1-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="3a4d1-146">고급 편집 기능을 지 원하는 셀은 일반적으로 Windows Forms 컨트롤에서 파생 된 호스트 된 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="3a4d1-147">이러한 컨트롤은 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스도 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="3a4d1-148">다음 개체 모델에서는 이러한 컨트롤을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![DataGridView 편집 컨트롤 개체 모델 계층 구조를 보여 주는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="3a4d1-150">다음 편집 컨트롤은 <xref:System.Windows.Forms.DataGridView> 컨트롤과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="3a4d1-151">사용자 고유의 편집 컨트롤을 만드는 방법에 대 한 자세한 내용은 [방법: Windows Forms DataGridView 셀의 호스트 컨트롤](how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="3a4d1-152">다음 표에서는 셀 형식, 열 형식 및 편집 컨트롤 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="3a4d1-153">셀 형식</span><span class="sxs-lookup"><span data-stu-id="3a4d1-153">Cell type</span></span>|<span data-ttu-id="3a4d1-154">호스팅된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3a4d1-154">Hosted control</span></span>|<span data-ttu-id="3a4d1-155">열 유형</span><span class="sxs-lookup"><span data-stu-id="3a4d1-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="3a4d1-156">N/A</span><span class="sxs-lookup"><span data-stu-id="3a4d1-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="3a4d1-157">N/A</span><span class="sxs-lookup"><span data-stu-id="3a4d1-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="3a4d1-158">N/A</span><span class="sxs-lookup"><span data-stu-id="3a4d1-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="3a4d1-159">N/A</span><span class="sxs-lookup"><span data-stu-id="3a4d1-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="3a4d1-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="3a4d1-160">DataGridViewRow</span></span>  
 <span data-ttu-id="3a4d1-161"><xref:System.Windows.Forms.DataGridViewRow> 클래스는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 연결 된 데이터 저장소에서 레코드의 데이터 필드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="3a4d1-162"><xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 행에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="3a4d1-163"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 컬렉션을 사용 하 여 선택 된 행에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="3a4d1-164">다음 개체 모델에서는이 사용법을 보여 주고 <xref:System.Windows.Forms.DataGridViewRow> 상속 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![DataGridViewRow 개체 모델 계층 구조를 표시 하는 다이어그램입니다.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="3a4d1-166">일반적으로 필요 하지는 않지만 <xref:System.Windows.Forms.DataGridViewRow> 클래스에서 고유한 형식을 파생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="3a4d1-167"><xref:System.Windows.Forms.DataGridView> 컨트롤에는 <xref:System.Windows.Forms.DataGridViewRow> 개체의 동작을 사용자 지정 하기 위한 몇 가지 행 관련 이벤트와 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="3a4d1-168"><xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 사용 하도록 설정 하면 새 행을 추가 하는 특수 행이 마지막 행으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="3a4d1-169">이 행은 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션의 일부 이지만 주의가 필요한 특수 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="3a4d1-170">자세한 내용은 [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4d1-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4d1-171">참조</span><span class="sxs-lookup"><span data-stu-id="3a4d1-171">See also</span></span>

- [<span data-ttu-id="3a4d1-172">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3a4d1-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="3a4d1-173">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3a4d1-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3a4d1-174">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="3a4d1-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
