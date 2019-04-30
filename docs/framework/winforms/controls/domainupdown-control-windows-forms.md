---
title: DomainUpDown 컨트롤(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: 83d674e3fb7ff7e715b75c635b891cd4e9703a21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972057"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="3d15c-102">DomainUpDown 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3d15c-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="3d15c-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤 같습니다 조합을 텍스트 상자 및 단추 쌍 목록을 통해 위로 또는 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="3d15c-104">컨트롤이 표시 하 고 선택 목록에서 텍스트 문자열을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="3d15c-105">사용자 단추 목록에서 이동를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 눌러 또는 목록의 항목을 일치 하는 문자열을 입력 하 여 문자열을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="3d15c-106">이 컨트롤에 대 한 한 가지 가능한 용도 이름의 사전순으로 정렬된 된 목록에서 항목 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="3d15c-107">(목록을 정렬 하려면 설정 합니다 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`.) 이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="3d15c-108">컨트롤의 키 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>하십시오 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="3d15c-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤의 텍스트 값을 표시 하는 개체의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="3d15c-110">하는 경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자 형식과 값 목록에 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="3d15c-111">하는 경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 지 나 스크롤 하면 첫 번째 항목 목록에서 이동 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="3d15c-112">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 고 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="3d15c-113">이 컨트롤에는 텍스트 문자열만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-113">This control displays only text strings.</span></span> <span data-ttu-id="3d15c-114">숫자 값을 표시 하는 컨트롤을 사용 합니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="3d15c-115">자세한 내용은 [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-115">For more information, see [NumericUpDown Control](numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d15c-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3d15c-116">In This Section</span></span>  
 [<span data-ttu-id="3d15c-117">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3d15c-117">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="3d15c-118">일반적인 개념을 소개 합니다 <xref:System.Windows.Forms.DomainUpDown> 컨트롤을 탐색 하 고 텍스트 문자열의 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="3d15c-119">방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="3d15c-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="3d15c-120">텍스트 문자열을 지정 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DomainUpDown> 컨트롤이 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="3d15c-121">방법: Windows Forms DomainUpDown 컨트롤에서 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="3d15c-122">항목을 삭제 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3d15c-123">참조</span><span class="sxs-lookup"><span data-stu-id="3d15c-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="3d15c-124">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="3d15c-125">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크가 있습니다...</span><span class="sxs-lookup"><span data-stu-id="3d15c-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d15c-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3d15c-126">Related Sections</span></span>  
 [<span data-ttu-id="3d15c-127">Windows Forms에서 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3d15c-127">Controls You Can Use On Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="3d15c-128">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d15c-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
