---
title: '방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동하도록 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609829"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="cdc2c-102">방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동하도록 설정</span><span class="sxs-lookup"><span data-stu-id="cdc2c-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="cdc2c-103">사용자의 이동 하려면 TAB 키를 사용 하도록 설정 하려면 다음 절차는 <xref:System.Windows.Forms.ToolStrip> 탭 순서의 다음 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="cdc2c-104"><xref:System.Windows.Forms.ToolStrip> TAB 키와 화살표 키 선택 항목의 첫 번째 눌러 허용 된 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="cdc2c-105">사용자가 TAB 키를 두 번 누를 때 탭 순서에서 다음 컨트롤에 사용자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="cdc2c-106">다음 컨트롤로 ToolStrip 밖으로 이동 하려면 TAB 키를 눌러 사용자를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cdc2c-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
- <span data-ttu-id="cdc2c-107">설정 합니다 <xref:System.Windows.Forms.ToolStrip.TabStop%2A> 의 속성을 <xref:System.Windows.Forms.ToolStrip> 에 `true`.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc2c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdc2c-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="cdc2c-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cdc2c-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
