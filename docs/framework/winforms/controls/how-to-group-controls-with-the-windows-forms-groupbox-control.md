---
title: '방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: d2bad0020d18cd262bc2fe3489a00209308bd7b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941325"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="abd60-102">방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="abd60-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="abd60-103">Windows Forms <xref:System.Windows.Forms.GroupBox> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="abd60-104">컨트롤을 그룹화 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="abd60-105">에 관련 된 일반 사용자 인터페이스에 대 한 폼 요소 시각적으로 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="abd60-106">그룹화 하려면 프로그래밍 방식으로 (예를 들어 라디오 단추).</span><span class="sxs-lookup"><span data-stu-id="abd60-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="abd60-107">하나의 단위로 디자인 타임에 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="abd60-108">컨트롤의 그룹을 만들려면</span><span class="sxs-lookup"><span data-stu-id="abd60-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="abd60-109">그리기는 <xref:System.Windows.Forms.GroupBox> 폼의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="abd60-110">그룹 상자 내에서 각 그리기 그룹 상자에 다른 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="abd60-111">그룹 상자의 묶으려는 기존 컨트롤에 있는 경우에 모든 컨트롤, 선택 클립보드로 잘라낸 수 있습니다는 <xref:System.Windows.Forms.GroupBox> 컨트롤 및 그룹 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="abd60-112">그룹 상자로 직접를 끌어 올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="abd60-113">설정 된 <xref:System.Windows.Forms.GroupBox.Text%2A> 속성을 적절 한 캡션에 그룹 상자의 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd60-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd60-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="abd60-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="abd60-115">GroupBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="abd60-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
