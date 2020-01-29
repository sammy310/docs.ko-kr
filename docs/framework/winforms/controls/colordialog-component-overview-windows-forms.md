---
title: ColorDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736971"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="d59ab-102">ColorDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d59ab-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d59ab-103">Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소는 사용자가 색상표에서 색을 선택 하 고 해당 색상표에 사용자 지정 색을 추가할 수 있는 미리 구성 된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="d59ab-104">이 구성 요소는 다른 Windows 기반 애플리케이션에서 색상 선택하는 데 사용하는 대화 상자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="d59ab-105">고유한 대화 상자를 구성하는 대신 Windows 기반 애플리케이션 내에서 간단한 솔루션으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="d59ab-106">대화 상자에서 선택한 색은 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="d59ab-107"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이 `false`로 설정 된 경우 "사용자 지정 색 정의" 단추를 사용할 수 없으며 사용자가 색상표의 미리 정의 된 색으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="d59ab-108"><xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`로 설정 된 경우 사용자는 디더링된 색을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="d59ab-109">대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d59ab-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59ab-110">참조</span><span class="sxs-lookup"><span data-stu-id="d59ab-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="d59ab-111">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d59ab-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="d59ab-112">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d59ab-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="d59ab-113">방법: Windows Forms ColorDialog 구성 요소의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="d59ab-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
