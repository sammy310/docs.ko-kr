---
title: DataView 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151106"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="684fa-102">DataView 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="684fa-102">Handling DataView Events</span></span>
<span data-ttu-id="684fa-103"><xref:System.Data.DataView.ListChanged>의 <xref:System.Data.DataView> 이벤트를 사용하여 뷰가 업데이트되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="684fa-104">이벤트를 발생시키는 업데이트에는 원본으로 사용하는 테이블에서의 행 추가, 삭제 또는 수정과 원본으로 사용하는 테이블 스키마에서의 열 추가 또는 삭제, 그리고 부모 또는 자식 관계의 변경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="684fa-105">**또한 ListChanged** 이벤트는 새 정렬 순서 또는 필터의 응용 프로그램으로 인해 보고 있는 행 목록이 크게 변경되었는지 도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="684fa-106">**ListChanged** 이벤트는 <xref:System.ComponentModel> 네임스페이스의 **ListChangedEventHandler 대리자를** 구현하고 <xref:System.ComponentModel.ListChangedEventArgs> 개체를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="684fa-107"><xref:System.ComponentModel.ListChangedType> **ListChangedEventArgs** 개체의 **ListChangedType** 속성에서 열거 값을 사용하여 발생한 변경 유형을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="684fa-108">행추가, 삭제 또는 이동과 관련된 변경 사항의 경우 추가되거나 이동된 행의 새 인덱스와 삭제된 행의 이전 인덱스는 **ListChangedEventArgs** 개체의 **NewIndex** 속성을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="684fa-109">이동된 행의 경우 **ListChangedEventArgs** 개체의 **OldIndex** 속성을 사용하여 이동된 행의 이전 인덱스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="684fa-110">**DataViewManager는** 또한 테이블이 추가 또는 제거되었는지 또는 기본 **DataSet의** **관계** 컬렉션이 변경된 경우 이를 알리기 위해 **ListChanged** 이벤트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="684fa-111">다음 코드 예제에서는 **ListChanged** 이벤트 처리기를 추가 하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="684fa-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="684fa-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="684fa-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="684fa-113">DataView</span><span class="sxs-lookup"><span data-stu-id="684fa-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="684fa-114">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="684fa-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
