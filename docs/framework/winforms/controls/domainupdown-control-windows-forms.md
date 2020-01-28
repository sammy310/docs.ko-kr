---
title: DomainUpDown 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745833"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="4f678-102">DomainUpDown 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4f678-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="4f678-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 목록에서 위나 아래로 이동 하기 위한 텍스트 상자와 단추 쌍의 조합 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="4f678-104">컨트롤은 선택 목록에서 텍스트 문자열을 표시 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="4f678-105">사용자는 위로 및 아래로 단추를 클릭 하 여 목록에서 이동 하거나, 위쪽 및 아래쪽 화살표 키를 누르거나, 목록의 항목과 일치 하는 문자열을 입력 하 여 문자열을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="4f678-106">이 컨트롤의 한 가지 가능한 용도는 사전순으로 정렬 된 이름 목록에서 항목을 선택 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="4f678-107">(목록을 정렬 하려면 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`로 설정 합니다.) 이 컨트롤의 함수는 목록 상자나 콤보 상자와 매우 유사 하지만 공간을 거의 차지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="4f678-108">컨트롤의 키 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="4f678-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에는 텍스트 값이 컨트롤에 표시 되는 개체의 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="4f678-110"><xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> `false`로 설정 된 경우 컨트롤은 사용자가 입력 하 고 목록의 값과 일치 하는 텍스트를 자동으로 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="4f678-111"><xref:System.Windows.Forms.DomainUpDown.Wrap%2A>을 `true`로 설정 하면 마지막 항목을 벗어나 스크롤하면 목록의 첫 번째 항목으로 이동 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="4f678-112">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 하 고 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="4f678-113">이 컨트롤은 텍스트 문자열만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-113">This control displays only text strings.</span></span> <span data-ttu-id="4f678-114">숫자 값을 표시 하는 컨트롤을 사용 하려면 <xref:System.Windows.Forms.NumericUpDown> 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="4f678-115">자세한 내용은 [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f678-115">For more information, see [NumericUpDown Control](numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f678-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4f678-116">In This Section</span></span>  
 [<span data-ttu-id="4f678-117">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4f678-117">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="4f678-118">사용자가 텍스트 문자열 목록에서 탐색 하 고 선택할 수 있는 <xref:System.Windows.Forms.DomainUpDown> 컨트롤의 일반적인 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="4f678-119">방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="4f678-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="4f678-120"><xref:System.Windows.Forms.DomainUpDown> 컨트롤이 표시 해야 하는 텍스트 문자열을 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="4f678-121">방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="4f678-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="4f678-122">코드의 <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 항목을 삭제 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4f678-123">참조</span><span class="sxs-lookup"><span data-stu-id="4f678-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="4f678-124">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="4f678-125">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4f678-126">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="4f678-126">Related Sections</span></span>  
 [<span data-ttu-id="4f678-127">Windows Forms에서 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4f678-127">Controls You Can Use On Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="4f678-128">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f678-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
