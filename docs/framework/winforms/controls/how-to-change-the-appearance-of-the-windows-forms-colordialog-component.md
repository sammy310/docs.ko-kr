---
title: ColorDialog 구성 요소의 모양 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746642"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="45a1b-102">방법: Windows Forms ColorDialog 구성 요소의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="45a1b-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="45a1b-103">여러 가지 속성을 사용 하 여 Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소의 모양을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="45a1b-104">이 대화 상자에는 기본 색을 보여 주는 두 개의 섹션과 사용자 지정 색을 정의할 수 있는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="45a1b-105">대부분의 속성은 사용자가 대화 상자에서 선택할 수 있는 색을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="45a1b-106"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이 `true`로 설정 된 경우 사용자는 사용자 지정 색을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="45a1b-107">사용자 지정 색을 정의 하도록 대화 상자를 확장 하면 <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> 속성이 `true` 됩니다. 그렇지 않으면 사용자가 "사용자 지정 색 정의" 단추를 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="45a1b-108"><xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 속성이 `true`으로 설정 되 면 대화 상자에 기본 색 집합에서 사용 가능한 모든 색이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="45a1b-109"><xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`로 설정 된 경우 사용자는 디더링된 색을 선택할 수 없습니다. 단색만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="45a1b-110"><xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성이 `true`로 설정 된 경우 대화 상자에 도움말 단추가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="45a1b-111">사용자가 도움말 단추를 클릭 하면 <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="45a1b-112">색 대화 상자의 모양을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="45a1b-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="45a1b-113"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>및 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a1b-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="45a1b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45a1b-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="45a1b-115">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="45a1b-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="45a1b-116">ColorDialog 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="45a1b-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
