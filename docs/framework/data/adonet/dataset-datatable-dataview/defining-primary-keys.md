---
title: 기본 키 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 94b033d58061e3d2e48a352d782eec7c4202fa43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166835"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="cf5a3-102">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="cf5a3-102">Defining Primary Keys</span></span>

<span data-ttu-id="cf5a3-103">일반적으로 데이터베이스 테이블에는 테이블의 각 행을 고유하게 식별하는 열 또는 열 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="cf5a3-104">이 식별 열 또는 열 그룹을 기본 키라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="cf5a3-105">단일를의로 식별 하면 <xref:System.Data.DataColumn> <xref:System.Data.DataTable.PrimaryKey%2A> <xref:System.Data.DataTable> 테이블에서 자동으로 <xref:System.Data.DataColumn.AllowDBNull%2A> 열의 속성을 **false** 로 설정 하 고 <xref:System.Data.DataColumn.Unique%2A> 속성을 **true**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="cf5a3-106">여러 열로 된 기본 키의 경우 **Allowdbnull** 속성만 자동으로 **false**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="cf5a3-107">의 **PrimaryKey** 속성은 <xref:System.Data.DataTable> 다음 예제와 같이 하나 이상의 **DataColumn** 개체 배열을 값으로 받습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="cf5a3-108">첫 번째 예제에서는 단일 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="cf5a3-109">다음 예제에서는 두 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5a3-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf5a3-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf5a3-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="cf5a3-111">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="cf5a3-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="cf5a3-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="cf5a3-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="cf5a3-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="cf5a3-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
