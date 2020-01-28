---
title: DomainUpDown 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745852"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="9f56f-102">DomainUpDown 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9f56f-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="9f56f-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 기본적으로 텍스트 상자와 목록에서 위로 또는 아래로 이동 하는 단추 쌍의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="9f56f-104">컨트롤은 선택 목록에서 텍스트 문자열을 표시 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="9f56f-105">사용자는 위로 및 아래로 단추를 클릭 하 여 목록에서 이동 하거나, 위쪽 및 아래쪽 화살표 키를 누르거나, 목록의 항목과 일치 하는 문자열을 입력 하 여 문자열을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="9f56f-106">이 컨트롤의 한 가지 가능한 용도는 사전순으로 정렬 된 이름 목록에서 항목을 선택 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f56f-107">목록을 정렬 하려면 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="9f56f-108">이 컨트롤의 함수는 목록 상자나 콤보 상자와 매우 유사 하지만 공간을 거의 차지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="9f56f-109">키 속성</span><span class="sxs-lookup"><span data-stu-id="9f56f-109">Key Properties</span></span>  
 <span data-ttu-id="9f56f-110">컨트롤의 키 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="9f56f-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에는 텍스트 값이 컨트롤에 표시 되는 개체의 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="9f56f-112"><xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> `false`로 설정 된 경우 컨트롤은 사용자가 입력 하 고 목록의 값과 일치 하는 텍스트를 자동으로 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="9f56f-113"><xref:System.Windows.Forms.DomainUpDown.Wrap%2A>을 `true`로 설정 하면 마지막 항목을 벗어나 스크롤하면 목록의 첫 번째 항목으로 이동 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="9f56f-114">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 하 고 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="9f56f-115">이 컨트롤은 텍스트 문자열만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-115">This control displays only text strings.</span></span> <span data-ttu-id="9f56f-116">숫자 값을 표시 하는 컨트롤을 사용 하려면 <xref:System.Windows.Forms.NumericUpDown> 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f56f-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="9f56f-117">자세한 내용은 [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f56f-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f56f-118">참조</span><span class="sxs-lookup"><span data-stu-id="9f56f-118">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="9f56f-119">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9f56f-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
