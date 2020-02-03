---
title: 레이블 컨트롤을 사용 하 여 액세스 키 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731057"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="5ca93-102">방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="5ca93-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="5ca93-103">Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 다른 컨트롤에 대 한 선택 키를 정의 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="5ca93-104">레이블 컨트롤에서 선택 키를 정의 하는 경우 사용자는 ALT 키와 지정한 문자를 눌러 탭 순서에서 뒤에 오는 컨트롤로 포커스를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="5ca93-105">레이블은 포커스를 받을 수 없기 때문에 포커스가 탭 순서의 다음 컨트롤로 자동 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="5ca93-106">이 방법을 사용 하 여 텍스트 상자, 콤보 상자, 목록 상자 및 데이터 표에 액세스 키를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="5ca93-107">레이블이 있는 컨트롤에 액세스 키를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="5ca93-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="5ca93-108">먼저 레이블을 그린 다음 다른 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="5ca93-109">또는</span><span class="sxs-lookup"><span data-stu-id="5ca93-109">-or-</span></span>  
  
     <span data-ttu-id="5ca93-110">컨트롤을 임의의 순서로 그리고 레이블의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 다른 컨트롤 보다 하나 작은 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="5ca93-111">레이블의 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="5ca93-112">레이블의 <xref:System.Windows.Forms.Label.Text%2A> 속성에서 앰퍼샌드 (&)를 사용 하 여 레이블에 대 한 액세스 키를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="5ca93-113">자세한 내용은 [Windows Forms 컨트롤에 대 한 선택 키 만들기](how-to-create-access-keys-for-windows-forms-controls.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ca93-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5ca93-114">앰퍼샌드를 사용 하 여 액세스 키를 만드는 대신 앰퍼샌드를 레이블 컨트롤에 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="5ca93-115">이 문제는 데이터에 앰퍼샌드가 포함 된 레코드 집합의 필드에 레이블 컨트롤을 바인딩하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="5ca93-116">레이블 컨트롤에 앰퍼샌드를 표시 하려면 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="5ca93-117">앰퍼샌드를 표시 하 고 액세스 키도 포함 하려면 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`로 설정 하 고 앰퍼샌드 (&)와 앰퍼샌드 (두 개의 앰퍼샌드)를 사용 하 여 선택 키를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca93-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ca93-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ca93-118">See also</span></span>

- [<span data-ttu-id="5ca93-119">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="5ca93-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="5ca93-120">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5ca93-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="5ca93-121">레이블 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5ca93-121">Label Control</span></span>](label-control-windows-forms.md)
