---
title: GroupBox 컨트롤을 사용 하 여 컨트롤 그룹화
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736655"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="5f751-102">방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="5f751-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="5f751-103">Windows Forms <xref:System.Windows.Forms.GroupBox> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="5f751-104">컨트롤을 그룹화 하는 세 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="5f751-105">일반 사용자 인터페이스에 대 한 관련 폼 요소의 시각적 그룹화를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="5f751-106">프로그래밍 방식 그룹화 (예: 라디오 단추)를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5f751-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="5f751-107">디자인 타임에 컨트롤을 하나의 단위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="5f751-108">컨트롤 그룹을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5f751-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="5f751-109">폼에 <xref:System.Windows.Forms.GroupBox> 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="5f751-110">그룹 상자에 다른 컨트롤을 추가 하 고 각 컨트롤을 그룹 상자 안에 그립니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="5f751-111">그룹 상자에 포함 하려는 기존 컨트롤이 있는 경우 모든 컨트롤을 선택 하 고 클립보드로 잘라내고 <xref:System.Windows.Forms.GroupBox> 컨트롤을 선택한 다음 그룹 상자에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="5f751-112">그룹 상자에 끌어서 놓을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="5f751-113">그룹 상자의 <xref:System.Windows.Forms.GroupBox.Text%2A> 속성을 적절 한 캡션으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f751-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f751-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f751-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="5f751-115">GroupBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5f751-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
