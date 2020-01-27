---
title: TabControl의 모양 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746617"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="5ff6e-102">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="5ff6e-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="5ff6e-103"><xref:System.Windows.Forms.TabControl>의 속성과 컨트롤의 개별 탭을 구성 하는 <xref:System.Windows.Forms.TabPage> 개체를 사용 하 여 Windows Forms에서 탭의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="5ff6e-104">이러한 속성을 설정 하 여 탭에 이미지를 표시 하 고, 가로 대신 탭을 세로로 표시 하 고, 여러 개의 탭 행을 표시 하 고, 프로그래밍 방식으로 탭을 설정 또는 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="5ff6e-105">탭의 레이블 부분에 아이콘을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="5ff6e-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="5ff6e-106">폼에 <xref:System.Windows.Forms.ImageList> 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="5ff6e-107">이미지 목록에 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="5ff6e-108">이미지 목록에 대 한 자세한 내용은 [Imagelist 구성 요소](imagelist-component-windows-forms.md) 및 [방법: Windows Forms imagelist 구성 요소를 사용 하 여 이미지 추가 또는 제거](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="5ff6e-109"><xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.ImageList%2A> 속성을 <xref:System.Windows.Forms.ImageList> 컨트롤로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="5ff6e-110"><xref:System.Windows.Forms.TabPage>의 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 속성을 목록에 있는 적절 한 이미지의 인덱스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="5ff6e-111">탭의 여러 행을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5ff6e-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="5ff6e-112">원하는 탭 페이지 수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="5ff6e-113"><xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Multiline%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="5ff6e-114">탭이 여러 행에 표시 되지 않는 경우 <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.Control.Width%2A> 속성을 모든 탭 보다 좁게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="5ff6e-115">컨트롤의 측면에 탭을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="5ff6e-115">To arrange tabs on the side of the control</span></span>  
  
- <span data-ttu-id="5ff6e-116"><xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Alignment%2A> 속성을 <xref:System.Windows.Forms.TabAlignment.Left> 또는 <xref:System.Windows.Forms.TabAlignment.Right>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="5ff6e-117">탭에서 프로그래밍 방식으로 모든 컨트롤을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5ff6e-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="5ff6e-118"><xref:System.Windows.Forms.TabPage>의 <xref:System.Windows.Forms.TabPage.Enabled%2A> 속성을 `true` 또는 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="5ff6e-119">탭을 단추로 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="5ff6e-119">To display tabs as buttons</span></span>  
  
- <span data-ttu-id="5ff6e-120"><xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Appearance%2A> 속성을 <xref:System.Windows.Forms.TabAppearance.Buttons> 또는 <xref:System.Windows.Forms.TabAppearance.FlatButtons>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff6e-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff6e-121">참조</span><span class="sxs-lookup"><span data-stu-id="5ff6e-121">See also</span></span>

- [<span data-ttu-id="5ff6e-122">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5ff6e-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="5ff6e-123">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5ff6e-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="5ff6e-124">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5ff6e-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="5ff6e-125">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5ff6e-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="5ff6e-126">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="5ff6e-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
