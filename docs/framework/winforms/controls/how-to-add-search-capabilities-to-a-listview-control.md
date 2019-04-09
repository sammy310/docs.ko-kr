---
title: '방법: ListView 컨트롤에 검색 기능 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: c1c59c3d4bb5d0d35103371575ebdd49d3559bbe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108552"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="95d79-102">방법: ListView 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="95d79-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="95d79-103">에 있는 항목의 큰 목록으로 작업 하는 경우에 종종는 <xref:System.Windows.Forms.ListView> 사용자에 게 검색 기능을 제공 하려는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="95d79-104"><xref:System.Windows.Forms.ListView> 두 가지 방법으로이 기능을 제공 하는 컨트롤: 텍스트 일치 및 위치를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="95d79-105">합니다 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 사용 하면 텍스트 검색을 수행할 수 있습니다는 <xref:System.Windows.Forms.ListView> 목록 또는 세부 정보 보기에서 검색 문자열 및 선택적 시작 및 끝 인덱스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="95d79-106">반면, 합니다 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 사용 하면에서 항목을 찾을 수 있습니다는 <xref:System.Windows.Forms.ListView> 아이콘 또는 타일 보기에서 지정 된 x 좌표와 y 좌표와 검색할 방향을 집합.</span><span class="sxs-lookup"><span data-stu-id="95d79-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="95d79-107">텍스트를 사용 하 여 항목을 찾으려면</span><span class="sxs-lookup"><span data-stu-id="95d79-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="95d79-108">만들기는 <xref:System.Windows.Forms.ListView> 사용 하 여는 <xref:System.Windows.Forms.ListView.View%2A> 속성이로 설정 <xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.List>를 입력 합니다 <xref:System.Windows.Forms.ListView> 항목과 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="95d79-109">호출 된 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 찾으려면 원하는 항목의 텍스트를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="95d79-110">다음 코드 예제를 만드는 방법을 보여 줍니다. <xref:System.Windows.Forms.ListView>, 항목을 사용 하 여 채우기 및 사용자가 입력 한 텍스트를 사용 하 여 목록에서 항목을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="95d79-111">X 좌표와 y 좌표를 사용 하 여 항목을 찾으려면</span><span class="sxs-lookup"><span data-stu-id="95d79-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="95d79-112">만들기는 <xref:System.Windows.Forms.ListView> 사용 하 여는 <xref:System.Windows.Forms.View> 속성이로 설정 <xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>를 입력 합니다 <xref:System.Windows.Forms.ListView> 항목과 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="95d79-113">호출 된 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 검색 하려는 방향과 원하는 x 및 y 좌표를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="95d79-114">다음 코드 예제에서는 기본 아이콘을 만드는 방법을 보여 줍니다 <xref:System.Windows.Forms.ListView>, 항목 및 캡처를 사용 하 여 채우기는 <xref:System.Windows.Forms.Control.MouseDown> 위쪽 방향으로 가장 가까운 항목을 찾으려면 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="95d79-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="95d79-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="95d79-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="95d79-116">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="95d79-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="95d79-117">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="95d79-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="95d79-118">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="95d79-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
