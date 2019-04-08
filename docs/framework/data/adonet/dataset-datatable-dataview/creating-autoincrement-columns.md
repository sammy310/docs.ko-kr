---
title: AutoIncrement 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090942"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="9b63b-102">AutoIncrement 열 만들기</span><span class="sxs-lookup"><span data-stu-id="9b63b-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="9b63b-103">열에 고유 값을 지정하려면 테이블에 새 행을 추가할 때 열 값이 자동으로 증가하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b63b-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="9b63b-104">자동 증분 만들려는 <xref:System.Data.DataColumn>로 설정 합니다 <xref:System.Data.DataColumn.AutoIncrement%2A> 열의 속성 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b63b-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="9b63b-105"><xref:System.Data.DataColumn> 정의 된 값을 사용 하 여 시작한를 <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 속성을 각 행의 값을 추가 하 고는 **AutoIncrement** 열에 정의 된 값으로 증가 <xref:System.Data.DataColumn.AutoIncrementStep%2A> 열의 속성.</span><span class="sxs-lookup"><span data-stu-id="9b63b-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="9b63b-106">에 대 한 **AutoIncrement** 좋습니다 열 합니다 <xref:System.Data.DataColumn.ReadOnly%2A> 의 속성을 **DataColumn** 로 설정 **true**.</span><span class="sxs-lookup"><span data-stu-id="9b63b-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="9b63b-107">다음 예제에서는 200으로 시작하여 3씩 증가하여 추가되는 열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b63b-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b63b-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b63b-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="9b63b-109">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="9b63b-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="9b63b-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="9b63b-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="9b63b-111">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9b63b-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
