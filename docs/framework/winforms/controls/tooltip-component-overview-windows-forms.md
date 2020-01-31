---
title: ToolTip 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741909"
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="40ef4-102">ToolTip 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="40ef4-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="40ef4-103">Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소는 사용자가 컨트롤을 가리킬 때 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="40ef4-104">도구 설명은 모든 컨트롤에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="40ef4-105">이 구성 요소를 사용 하는 예: 폼의 공간을 절약 하기 위해 단추에 작은 아이콘을 표시 하 고 도구 설명을 사용 하 여 단추의 기능을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="40ef4-106">ToolTip 구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="40ef4-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="40ef4-107"><xref:System.Windows.Forms.ToolTip> 구성 요소는 Windows Form 또는 다른 컨테이너의 여러 컨트롤에 `ToolTip` 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="40ef4-108">예를 들어 폼에 하나의 <xref:System.Windows.Forms.ToolTip> 구성 요소를 배치한 경우 <xref:System.Windows.Forms.TextBox> 컨트롤의 경우 "여기에 이름 입력"을 표시 하 고 <xref:System.Windows.Forms.Button> 컨트롤의 경우 "여기를 클릭 하 여 변경 내용을 저장할 수 있습니다."를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="40ef4-109"><xref:System.Windows.Forms.ToolTip> 구성 요소의 주요 메서드는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 및 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="40ef4-110"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 사용 하 여 컨트롤에 대해 표시 되는 도구 설명을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="40ef4-111">자세한 내용은 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40ef4-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="40ef4-112">키 속성은 도구 설명이 나타나도록 `true`로 설정 해야 하 고, 도구 설명 문자열이 표시 되는 시간을 설정 하는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, 도구 설명에 표시 되는 컨트롤을 가리켜야 하는 시간, 다음 도구 설명 창이 표시 될 때까지 걸리는 시간을 설정 하는 <xref:System.Windows.Forms.ToolTip.Active%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="40ef4-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="40ef4-113">자세한 내용은 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40ef4-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ef4-114">참조</span><span class="sxs-lookup"><span data-stu-id="40ef4-114">See also</span></span>

- <xref:System.Windows.Forms.ToolTip>
- [<span data-ttu-id="40ef4-115">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="40ef4-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="40ef4-116">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="40ef4-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
