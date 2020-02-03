---
title: '방법: 키 컬렉션 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739620"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="37825-102">방법: Windows Forms에서 키 컬렉션 액세스</span><span class="sxs-lookup"><span data-stu-id="37825-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="37825-103">키를 사용 하 여 개별 컬렉션 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37825-103">You can access individual collection items by key.</span></span> <span data-ttu-id="37825-104">이 기능은 Windows Forms 응용 프로그램에서 일반적으로 사용 되는 많은 컬렉션 클래스에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37825-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="37825-105">다음 목록에서는 액세스할 수 있는 키가 있는 컬렉션을 포함 하는 몇 가지 컬렉션 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37825-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="37825-106">컬렉션의 항목과 연결 된 키는 일반적으로 항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="37825-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="37825-107">다음 절차에서는 컬렉션 클래스를 사용 하 여 일반적인 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37825-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="37825-108">컨트롤 컬렉션에서 중첩 된 컨트롤을 찾고 포커스를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="37825-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="37825-109"><xref:System.Windows.Forms.Control.ControlCollection.Find%2A> 및 <xref:System.Windows.Forms.Control.Focus%2A> 메서드를 사용 하 여 찾을 컨트롤의 이름을 지정 하 고 포커스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37825-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="37825-110">이미지 컬렉션의 이미지에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="37825-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="37825-111"><xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> 속성을 사용 하 여 액세스 하려는 이미지의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37825-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="37825-112">탭 페이지를 선택 된 탭으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="37825-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="37825-113"><xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> 속성과 함께 <xref:System.Windows.Forms.TabControl.SelectedTab%2A> 속성을 사용 하 여 선택 된 탭으로 설정할 탭 페이지의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37825-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="37825-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37825-114">See also</span></span>

- [<span data-ttu-id="37825-115">Windows Forms 시작</span><span class="sxs-lookup"><span data-stu-id="37825-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="37825-116">방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="37825-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
