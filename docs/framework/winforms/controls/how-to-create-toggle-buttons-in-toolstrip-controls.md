---
title: '방법: ToolStrip 컨트롤에서 설정/해제 단추 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: e688e9a220e6c82caa2d107589b5ca9a1e59e72b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052161"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="298c7-102">방법: ToolStrip 컨트롤에서 설정/해제 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="298c7-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="298c7-103">사용자가 토글 단추를 클릭 하면 오목 하 게 표시 하 고 사용자가 단추를 다시 클릭 될 때까지 오목한 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="298c7-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="298c7-104">토글 ToolStripButton를 만들려면</span><span class="sxs-lookup"><span data-stu-id="298c7-104">To create a toggling ToolStripButton</span></span>  
  
- <span data-ttu-id="298c7-105">다음 코드 예제와 같은 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="298c7-105">Use code such as the following code example.</span></span> <span data-ttu-id="298c7-106">이 코드는 폼에 포함 되어 있다고 가정를 <xref:System.Windows.Forms.ToolStrip> 제어 및는 해당 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션에는 <xref:System.Windows.Forms.ToolStripButton> 호출 `toolStripButton1`합니다.</span><span class="sxs-lookup"><span data-stu-id="298c7-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="298c7-107">또한 이벤트 처리기 호출 되었다고 가정 `toolStripButton1_CheckedChanged`합니다.</span><span class="sxs-lookup"><span data-stu-id="298c7-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="298c7-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="298c7-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="298c7-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="298c7-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
