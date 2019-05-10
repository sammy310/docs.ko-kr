---
title: Windows Forms에서 컨트롤 정렬
ms.date: 03/30/2017
f1_keywords:
- VisualSelection
helpviewer_keywords:
- controls [Windows Forms], positioning
- Windows Forms controls, positioning on form
ms.assetid: b2d62ed8-c391-4a7e-b72e-6bbabfca73dc
ms.openlocfilehash: 7a131df84cb7e02bb23558c7f1d2a6d3f0cfadd3
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211226"
---
# <a name="arranging-controls-on-windows-forms"></a><span data-ttu-id="5cfb8-102">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5cfb8-102">Arranging Controls on Windows Forms</span></span>
<span data-ttu-id="5cfb8-103">다양한 방법으로 양식에 컨트롤을 배치하고 조작함으로써 사용자가 직관적이고 기능적으로 사용할 수 있는 사용자 인터페이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-103">By placing and manipulating controls on forms in different ways, you can create user interfaces that are both intuitive and functional for users.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5cfb8-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5cfb8-104">In This Section</span></span>
 <span data-ttu-id="5cfb8-105">[방법: Windows Forms에서 여러 컨트롤 맞춤](how-to-align-multiple-controls-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-105">[How to: Align Multiple Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-106">Windows Form에서 여러 컨트롤의 위치를 정렬하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-106">Gives directions for lining up the position of a number of controls on your Windows Form.</span></span>

 <span data-ttu-id="5cfb8-107">[방법: Windows Forms에서 컨트롤 고정](how-to-anchor-controls-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-107">[How to: Anchor Controls on Windows Forms](how-to-anchor-controls-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-108">런타임에 동적으로 크기를 조정하는 컨트롤을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-108">Gives directions for setting controls to resize dynamically at run time.</span></span>

 <span data-ttu-id="5cfb8-109">[방법: Windows Forms 간에 컨트롤 복사](how-to-copy-controls-between-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-109">[How to: Copy Controls Between Windows Forms](how-to-copy-controls-between-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-110">양식 간에 컨트롤을 복제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-110">Gives directions for duplicating controls between forms.</span></span>

 <span data-ttu-id="5cfb8-111">[방법: Windows Forms에 컨트롤 도킹](how-to-dock-controls-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-111">[How to: Dock Controls on Windows Forms](how-to-dock-controls-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-112">양식의 표면에 컨트롤을 "고정"하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-112">Gives directions for making controls "stick" to the side(s) of a form.</span></span>

 <span data-ttu-id="5cfb8-113">[방법: Windows Forms에서 개체 계층화](how-to-layer-objects-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-113">[How to: Layer Objects on Windows Forms](how-to-layer-objects-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-114">z 축(z 좌표)을 기준으로 위쪽에 있는 컨트롤을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-114">Gives directions for establishing which controls are on top relative to the z-axis (z-order).</span></span>

 <span data-ttu-id="5cfb8-115">[방법: Windows Forms에 컨트롤 잠금](how-to-lock-controls-to-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-115">[How to: Lock Controls to Windows Forms](how-to-lock-controls-to-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-116">컨트롤을 양식에 영구적으로 고정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-116">Gives directions for fastening controls permanently to the form.</span></span>

 <span data-ttu-id="5cfb8-117">[방법: Windows Forms에서 컨트롤 위치](how-to-position-controls-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-117">[How to: Position Controls on Windows Forms](how-to-position-controls-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-118">양식에 컨트롤의 좌표를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-118">Gives directions for setting the coordinates of the controls on a form.</span></span>

 <span data-ttu-id="5cfb8-119">[방법: Windows Forms에서 컨트롤 크기 조정](how-to-resize-controls-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-119">[How to: Resize Controls on Windows Forms](how-to-resize-controls-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-120">양식에 컨트롤의 크기를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-120">Gives directions for setting the size of controls on a form.</span></span>

 <span data-ttu-id="5cfb8-121">[방법: 모든 Windows Forms에 대 한 모눈 옵션 설정](how-to-set-grid-options-for-all-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-121">[How to: Set Grid Options for All Windows Forms](how-to-set-grid-options-for-all-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-122">양식을 덮고 있는 모눈의 크기를 조정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-122">Gives directions for calibrating the size of the grid that covers a form.</span></span>

 <span data-ttu-id="5cfb8-123">[방법: Windows Forms에서 탭 순서 설정](how-to-set-the-tab-order-on-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-123">[How to: Set the Tab Order on Windows Forms](how-to-set-the-tab-order-on-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-124">사용자가 Tab 키를 누를 때 포커스를 맞출 컨트롤의 순서를 조정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-124">Gives directions for regulating the order in which controls will have focus when the user presses TAB.</span></span>

 <span data-ttu-id="5cfb8-125">[방법: 맞춤선과 모눈 Windows Forms에서 컨트롤 정렬](how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-125">[How to: Arrange Controls with Snaplines and the Grid in Windows Forms](how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="5cfb8-126">양식의 모눈에 컨트롤을 배치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-126">Gives directions for affixing controls to the grid on a form.</span></span>

 <span data-ttu-id="5cfb8-127">[방법: 다른 부모에 기존 컨트롤 다시 할당](how-to-reassign-existing-controls-to-a-different-parent.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-127">[How to: Reassign Existing Controls to a Different Parent](how-to-reassign-existing-controls-to-a-different-parent.md)\\</span></span>
 <span data-ttu-id="5cfb8-128">기존 컨트롤을 새 부모 컨테이너에 할당하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-128">Gives directions for assigning existing controls to a new parent container.</span></span>

 <span data-ttu-id="5cfb8-129">[연습: Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성을 사용 하 여 레이아웃](windows-forms-controls-padding-autosize.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-129">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md)\\</span></span>
 <span data-ttu-id="5cfb8-130">사용 하 여 폼에 컨트롤을 배치 하는 방법을 설명 합니다는 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 내의 속성을 **Forms 디자이너** Visual Studio에서.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-130">Describes how you can place controls on your forms by using the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties within the **Forms Designer** in Visual Studio.</span></span>

 <span data-ttu-id="5cfb8-131">[연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-131">[Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)\\</span></span>
 <span data-ttu-id="5cfb8-132">맞춤선으로 수행하는 다양한 레이아웃 역할을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-132">Demonstrates the various layout roles fulfilled by snaplines.</span></span>

## <a name="related-sections"></a><span data-ttu-id="5cfb8-133">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5cfb8-133">Related Sections</span></span>
 <span data-ttu-id="5cfb8-134">[방법: Windows Forms 단추를 디자이너를 사용 하는 취소 단추로 지정](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-134">[How to: Designate a Windows Forms Button as the Cancel Button Using the Designer](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)\\</span></span>
 <span data-ttu-id="5cfb8-135">양식을 취소하는 컨트롤로 단추를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-135">Gives directions for establishing a button as the control to cancel the form.</span></span>

 <span data-ttu-id="5cfb8-136">[방법: Windows Forms 단추를 디자이너를 사용 하 여 적용 단추로 지정](designate-a-wf-button-as-the-accept-button-using-the-designer.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-136">[How to: Designate a Windows Forms Button as the Accept Button Using the Designer](designate-a-wf-button-as-the-accept-button-using-the-designer.md)\\</span></span>
 <span data-ttu-id="5cfb8-137">대화 상자에서 포커스가 있는 위치에 관계 없이 Enter 키를 누를 때 해당 단추(종종 "확인" 단추)를 "입력 허용" 단추로 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-137">Gives directions for establishing a button (often an "OK" button) as the "accept input" button when ENTER is pressed regardless of where focus is at the time in the dialog box.</span></span>

 <span data-ttu-id="5cfb8-138">[방법: 함수 집합으로 그룹 Windows Forms RadioButton 컨트롤](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-138">[How to: Group Windows Forms RadioButton Controls to Function as a Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)\\</span></span>
 <span data-ttu-id="5cfb8-139">서로 관련되도록 `RadioButton` 컨트롤의 집합을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-139">Gives directions for establishing a set of `RadioButton` controls as being related to one another.</span></span>

 <span data-ttu-id="5cfb8-140">[Windows Forms 컨트롤](index.md)\\</span><span class="sxs-lookup"><span data-stu-id="5cfb8-140">[Windows Forms Controls](index.md)\\</span></span>
 <span data-ttu-id="5cfb8-141">컨트롤에 대한 일반 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb8-141">Provides general information about controls.</span></span>
