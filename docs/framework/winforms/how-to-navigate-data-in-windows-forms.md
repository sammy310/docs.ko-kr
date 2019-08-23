---
title: '방법: Windows Forms에서 데이터 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: eb973497f51592b5d34c22e62da77612aec23c35
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964272"
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="ef143-102">방법: Windows Forms에서 데이터 탐색</span><span class="sxs-lookup"><span data-stu-id="ef143-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="ef143-103">Windows 응용 프로그램에서 데이터 원본의 레코드를 탐색 하는 가장 쉬운 방법은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 소스에 바인딩한 다음 컨트롤 <xref:System.Windows.Forms.BindingSource>을에 바인딩하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="ef143-104"><xref:System.Windows.Forms.BindingSource> 그런 다음 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, 및의기본제공탐색메서드를사용할수있습니다.<xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> <xref:System.Windows.Forms.BindingSource.MoveFirst%2A></span><span class="sxs-lookup"><span data-stu-id="ef143-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="ef143-105">이러한 메서드를 사용 하면의 <xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 속성을 적절 하 게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="ef143-106">항목을 찾아 속성을 <xref:System.Windows.Forms.BindingSource.Position%2A> 설정 하 여 현재 항목으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="ef143-107">데이터 원본에서 위치를 증가 시키려면</span><span class="sxs-lookup"><span data-stu-id="ef143-107">To increment the position in a data source</span></span>  
  
1. <span data-ttu-id="ef143-108">바인딩되는 데이터 <xref:System.Windows.Forms.BindingSource> 에 대 한의 속성을이동할레코드위치로설정합니다.<xref:System.Windows.Forms.BindingSource.Position%2A></span><span class="sxs-lookup"><span data-stu-id="ef143-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="ef143-109">다음 예제에서는 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 의 메서드 <xref:System.Windows.Forms.BindingSource> 를 사용 하 여를 `nextButton` 클릭할 때 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 증가 시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="ef143-110">는 <xref:System.Windows.Forms.BindingSource> 데이터 `Customers` 집합`Northwind`의 테이블에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef143-111"><xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 첫 번째 또는 마지막 레코드 이외의 값으로 설정 하면 오류가 발생 하지 않습니다. .NET Framework는 목록 범위 밖의 값으로 위치를 설정할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the .NET Framework will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="ef143-112">응용 프로그램에서 첫 번째 또는 마지막 레코드를 넘어가는 지 여부를 확인 하는 것이 중요 한 경우에는 데이터 요소 수를 초과 하는지 여부를 테스트 하는 논리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="ef143-113">끝을 통과 했는지 여부를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ef143-113">To check whether you have passed the end or beginning</span></span>  
  
1. <span data-ttu-id="ef143-114"><xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="ef143-115">처리기에서 제안 된 위치 값이 실제 데이터 요소 수를 초과 했는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="ef143-116">다음 예제에서는 마지막 데이터 요소에 도달 했는지 여부를 테스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="ef143-117">예제에서 마지막 요소에 있는 경우 폼의 **다음** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef143-118">코드에서 탐색 하는 목록을 변경 하는 경우 사용자가 새 목록의 전체 길이를 검색할 수 있도록 **다음** 단추를 다시 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="ef143-119">또한 작업 하는 특정 <xref:System.Windows.Forms.BindingSource.PositionChanged> <xref:System.Windows.Forms.BindingSource> 에 대 한 위의 이벤트를 해당 이벤트 처리 메서드와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="ef143-120">다음은 이벤트를 <xref:System.Windows.Forms.BindingSource.PositionChanged> 처리 하는 메서드의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="ef143-121">항목을 찾아서 현재 항목으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ef143-121">To find an item and set it as the current item</span></span>  
  
1. <span data-ttu-id="ef143-122">현재 항목으로 설정 하려는 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="ef143-123">데이터 소스가를 구현 <xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.ComponentModel.IBindingList>하는 경우 <xref:System.Windows.Forms.BindingSource>의 메서드를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="ef143-124">을 구현 <xref:System.ComponentModel.IBindingList> 하는 데이터 원본의 몇 가지 예 <xref:System.Data.DataView>는 <xref:System.ComponentModel.BindingList%601> 및입니다.</span><span class="sxs-lookup"><span data-stu-id="ef143-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ef143-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef143-125">See also</span></span>

- [<span data-ttu-id="ef143-126">Windows Forms에서 지원하는 데이터 소스</span><span class="sxs-lookup"><span data-stu-id="ef143-126">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)
- [<span data-ttu-id="ef143-127">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="ef143-127">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="ef143-128">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef143-128">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
- [<span data-ttu-id="ef143-129">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="ef143-129">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
