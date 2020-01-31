---
title: TabControl 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 2668169488b4087673fbf2552650c23cda780642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742834"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="6af9a-102">TabControl 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6af9a-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="6af9a-103">Windows Forms <xref:System.Windows.Forms.TabControl>은 파일 캐비닛의 폴더 집합에 노트북 또는 레이블의 구분선과 같은 여러 탭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="6af9a-104">탭에는 사진 및 기타 컨트롤이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="6af9a-105">탭 컨트롤을 사용 하 여 Windows 운영 체제에 표시 되는 여러 페이지 (예: 제어판 표시 속성)의 여러 대화 상자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="6af9a-106">또한 <xref:System.Windows.Forms.TabControl>를 사용 하 여 관련 속성 그룹을 설정 하는 데 사용 되는 속성 페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="6af9a-107">TabControl 사용</span><span class="sxs-lookup"><span data-stu-id="6af9a-107">Working with TabControl</span></span>  
 <span data-ttu-id="6af9a-108"><xref:System.Windows.Forms.TabControl>의 가장 중요 한 속성은 개별 탭이 포함 된 <xref:System.Windows.Forms.TabControl.TabPages%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="6af9a-109">각 개별 탭은 <xref:System.Windows.Forms.TabPage> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="6af9a-110">탭을 클릭 하면 해당 <xref:System.Windows.Forms.TabPage> 개체에 대 한 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af9a-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af9a-111">참조</span><span class="sxs-lookup"><span data-stu-id="6af9a-111">See also</span></span>

- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="6af9a-112">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6af9a-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="6af9a-113">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="6af9a-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="6af9a-114">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="6af9a-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="6af9a-115">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="6af9a-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="6af9a-116">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6af9a-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="6af9a-117">Windows Forms 대화 상자</span><span class="sxs-lookup"><span data-stu-id="6af9a-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
