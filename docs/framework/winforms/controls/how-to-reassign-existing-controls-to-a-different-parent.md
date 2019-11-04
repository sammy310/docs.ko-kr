---
title: '방법: 다른 부모에 기존 컨트롤 다시 할당'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1767fcff1742f4ad630b4b996c709b7ded53a129
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459204"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="c618a-102">방법: 다른 부모에 기존 컨트롤 다시 할당</span><span class="sxs-lookup"><span data-stu-id="c618a-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="c618a-103">폼에 있는 컨트롤을 새 컨테이너 컨트롤에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="c618a-104">Visual Studio에서 **도구 상자** 의 세 가지 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="c618a-105">서로 정렬되지 않은 상태로 근처에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="c618a-106">**도구 상자**에서 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="c618a-107">(아이콘을 폼으로 끌어 오지 마세요.)</span><span class="sxs-lookup"><span data-stu-id="c618a-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="c618a-108">마우스 포인터를 세 <xref:System.Windows.Forms.Button> 컨트롤 쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="c618a-109">포인터가 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="c618a-110">마우스 단추를 길게 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="c618a-111">마우스 포인터를 끌어 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 윤곽선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="c618a-112">세 <xref:System.Windows.Forms.Button> 컨트롤 주위에 윤곽선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="c618a-113">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-113">Release the mouse button.</span></span>

   <span data-ttu-id="c618a-114">이제 세 <xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="c618a-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="c618a-115">참조</span><span class="sxs-lookup"><span data-stu-id="c618a-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="c618a-116">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="c618a-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="c618a-117">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="c618a-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
