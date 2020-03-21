---
title: 기본 키 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 159b23eb4ef5ca38ebce6e488080d315ec3be081
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151184"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="e2904-102">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="e2904-102">Defining Primary Keys</span></span>
<span data-ttu-id="e2904-103">일반적으로 데이터베이스 테이블에는 테이블의 각 행을 고유하게 식별하는 열 또는 열 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="e2904-104">이 식별 열 또는 열 그룹을 기본 키라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="e2904-105">single을 <xref:System.Data.DataColumn> <xref:System.Data.DataTable.PrimaryKey%2A> 에 <xref:System.Data.DataTable>대한 것으로 식별하면 테이블은 <xref:System.Data.DataColumn.AllowDBNull%2A> 열의 속성을 **false로** 자동으로 <xref:System.Data.DataColumn.Unique%2A> 설정하고 속성을 **true로**설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="e2904-106">다중 열 기본 키의 경우 **AllowDBNull** 속성만 **false로**자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="e2904-107">다음 **PrimaryKey** 예제와 같이 <xref:System.Data.DataTable> 수신하는 기본 Key 속성은 하나 이상의 **DataColumn** 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="e2904-108">첫 번째 예제에서는 단일 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="e2904-109">다음 예제에서는 두 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2904-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2904-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2904-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="e2904-111">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="e2904-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="e2904-112">DataTable</span><span class="sxs-lookup"><span data-stu-id="e2904-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="e2904-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="e2904-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
