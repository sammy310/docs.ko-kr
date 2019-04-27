---
title: '방법: MDI 애플리케이션에 대한 자동 메뉴 병합 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013025"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="1e094-102">방법: MDI 애플리케이션에 대한 자동 메뉴 병합 설정</span><span class="sxs-lookup"><span data-stu-id="1e094-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="1e094-103">다음 절차 (MDI) 다중 문서 인터페이스 응용 프로그램에 자동 병합 설정에 대 한 기본 단계를 제공 <xref:System.Windows.Forms.MenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="1e094-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="1e094-104">자동 메뉴 병합 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1e094-104">To set up automatic menu merging</span></span>  
  
1. <span data-ttu-id="1e094-105">설정 하 여 MDI 부모 폼을 만드는 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e094-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="1e094-106">추가 된 <xref:System.Windows.Forms.MenuStrip> 설정 MDI 부모에 해당 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성을 <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="1e094-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3. <span data-ttu-id="1e094-107">MDI 자식 폼을 만들고 설정 해당 <xref:System.Windows.Forms.Form.MdiParent%2A> 속성을 부모 폼의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1e094-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4. <span data-ttu-id="1e094-108">추가 된 <xref:System.Windows.Forms.MenuStrip> MDI 자식 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="1e094-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5. <span data-ttu-id="1e094-109">자식 폼을 설정 합니다 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 의 속성을 <xref:System.Windows.Forms.MenuStrip> 에 `false`.</span><span class="sxs-lookup"><span data-stu-id="1e094-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6. <span data-ttu-id="1e094-110">자식 폼의 메뉴 항목을 추가할 <xref:System.Windows.Forms.MenuStrip> 부모 폼의 병합 하려는 <xref:System.Windows.Forms.MenuStrip> 자식 폼이 활성화 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="1e094-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7. <span data-ttu-id="1e094-111">사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 자식 폼의 메뉴에서 속성 항목 <xref:System.Windows.Forms.MenuStrip> 부모 폼에 병합 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e094-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e094-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e094-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="1e094-113">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1e094-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
