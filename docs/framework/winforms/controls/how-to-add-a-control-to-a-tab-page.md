---
title: '방법: 탭 페이지에 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 6eb509fd10a5000a5423d624cec5b6d126990d73
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723949"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="ed777-102">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ed777-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="ed777-103">Windows Forms를 사용할 수 있습니다 <xref:System.Windows.Forms.TabControl> 구성 된 방식으로 다른 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed777-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="ed777-104">다음 절차에는 첫 번째 탭에 단추를 추가 하는 방법을 보여 줍니다. 탭 페이지의 레이블 부분에 아이콘을 추가 하는 방법에 대 한 내용은 [방법: Windows Forms TabControl의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed777-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="ed777-105">프로그래밍 방식으로 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ed777-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="ed777-106">사용 합니다 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 에서 반환 된 컬렉션의 메서드는 <xref:System.Windows.Forms.Control.Controls%2A> 속성을 <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="ed777-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ed777-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed777-107">See also</span></span>
- [<span data-ttu-id="ed777-108">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ed777-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="ed777-109">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ed777-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="ed777-110">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="ed777-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="ed777-111">방법: 탭 페이지를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ed777-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="ed777-112">방법: Windows Forms TabControl 사용 하 여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="ed777-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
