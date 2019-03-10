---
title: DomainUpDown 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 851c02747a2414e34a5e9d35bdc7d1df916efce0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718898"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="56455-102">DomainUpDown 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="56455-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="56455-103">Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 한 쌍의 목록에서 위로 또는 아래로 이동 단추 및 텍스트 상자를 나열 하는 기본적으로 조합 합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="56455-104">컨트롤이 표시 하 고 선택 목록에서 텍스트 문자열을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="56455-105">사용자 단추 목록에서 이동를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 눌러 또는 목록의 항목을 일치 하는 문자열을 입력 하 여 문자열을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56455-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="56455-106">이 컨트롤에 대 한 한 가지 가능한 용도 이름의 사전순으로 정렬된 된 목록에서 항목 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="56455-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56455-107">목록을 정렬 하려면 설정 합니다 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="56455-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="56455-108">이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="56455-109">키 속성</span><span class="sxs-lookup"><span data-stu-id="56455-109">Key Properties</span></span>  
 <span data-ttu-id="56455-110">컨트롤의 키 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>하십시오 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="56455-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤의 텍스트 값을 표시 하는 개체의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="56455-112">하는 경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자 형식과 값 목록에 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="56455-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="56455-113">하는 경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 지 나 스크롤 하면 첫 번째 항목 목록에서 이동 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="56455-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="56455-114">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 고 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="56455-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="56455-115">이 컨트롤에는 텍스트 문자열만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56455-115">This control displays only text strings.</span></span> <span data-ttu-id="56455-116">숫자 값을 표시 하는 컨트롤을 사용 합니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="56455-117">자세한 내용은 [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56455-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56455-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="56455-118">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="56455-119">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="56455-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
