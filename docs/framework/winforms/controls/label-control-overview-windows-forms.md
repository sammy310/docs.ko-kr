---
title: Label 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745290"
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="95b9a-102">Label 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="95b9a-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="95b9a-103">Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 사용자가 편집할 수 없는 텍스트 또는 이미지를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="95b9a-104">이러한 항목은 폼의 개체를 식별 하는 데 사용 됩니다. 예를 들어 클릭 하면 특정 컨트롤이 수행할 작업에 대 한 설명을 제공 하거나 응용 프로그램의 런타임 이벤트 또는 프로세스에 대 한 응답으로 정보를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="95b9a-105">예를 들어 레이블을 사용 하 여 텍스트 상자, 목록 상자, 콤보 상자 등에 설명 캡션을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="95b9a-106">런타임에 이벤트에 대 한 응답으로 레이블에 표시 되는 텍스트를 변경 하는 코드를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="95b9a-107">예를 들어 응용 프로그램에서 변경 내용을 처리 하는 데 몇 분이 소요 되는 경우 레이블에 처리 상태 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="95b9a-108">레이블 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="95b9a-108">Working with the Label Control</span></span>  
 <span data-ttu-id="95b9a-109"><xref:System.Windows.Forms.Label> 컨트롤은 포커스를 받을 수 없기 때문에 다른 컨트롤에 대 한 액세스 키를 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="95b9a-110">액세스 키를 사용 하면 사용자가 선택 키로 ALT 키를 눌러 다른 컨트롤을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="95b9a-111">자세한 내용은 [Windows Forms 컨트롤에 대 한 선택 키 만들기](how-to-create-access-keys-for-windows-forms-controls.md) 및 [방법: Windows Forms 레이블 컨트롤을 사용 하 여 선택 키 만들기](how-to-create-access-keys-with-windows-forms-label-controls.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b9a-111">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="95b9a-112">레이블에 표시 되는 캡션은 <xref:System.Windows.Forms.Label.Text%2A> 속성에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="95b9a-113"><xref:System.Windows.Forms.Label.TextAlign%2A> 속성을 사용 하면 레이블 내의 텍스트 맞춤을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9a-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="95b9a-114">자세한 내용은 [방법: Windows Forms 컨트롤에 표시 되는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b9a-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b9a-115">참조</span><span class="sxs-lookup"><span data-stu-id="95b9a-115">See also</span></span>

- <xref:System.Windows.Forms.Label>
- [<span data-ttu-id="95b9a-116">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="95b9a-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="95b9a-117">방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="95b9a-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
