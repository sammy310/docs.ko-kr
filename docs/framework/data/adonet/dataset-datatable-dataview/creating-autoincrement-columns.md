---
description: '자세한 정보: AutoIncrement 열 만들기'
title: AutoIncrement 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 7568b1013b7af5aef7a6fc1f28dc163a082743a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739640"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="850fc-103">AutoIncrement 열 만들기</span><span class="sxs-lookup"><span data-stu-id="850fc-103">Creating AutoIncrement Columns</span></span>

<span data-ttu-id="850fc-104">열에 고유 값을 지정하려면 테이블에 새 행을 추가할 때 열 값이 자동으로 증가하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="850fc-104">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="850fc-105">자동 증분을 만들려면 <xref:System.Data.DataColumn> <xref:System.Data.DataColumn.AutoIncrement%2A> 열의 속성을 **true** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="850fc-105">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="850fc-106"><xref:System.Data.DataColumn>그런 다음은 속성에 정의 된 값으로 시작 하 <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 고, 각 행을 추가 하 여 **AutoIncrement** 열의 값이 열의 속성에 정의 된 값 만큼 증가 합니다 <xref:System.Data.DataColumn.AutoIncrementStep%2A> .</span><span class="sxs-lookup"><span data-stu-id="850fc-106">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="850fc-107">**AutoIncrement** 열의 경우 <xref:System.Data.DataColumn.ReadOnly%2A> **DataColumn** 의 속성을 **true** 로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="850fc-107">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="850fc-108">다음 예제에서는 200으로 시작하여 3씩 증가하여 추가되는 열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="850fc-108">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="850fc-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="850fc-109">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="850fc-110">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="850fc-110">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="850fc-111">DataTables</span><span class="sxs-lookup"><span data-stu-id="850fc-111">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="850fc-112">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="850fc-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
