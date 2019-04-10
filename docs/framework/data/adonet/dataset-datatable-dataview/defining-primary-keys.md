---
title: 기본 키 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 84c84cb8fc0ee484b09c69c72571a19c335b58f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230631"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="74a22-102">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="74a22-102">Defining Primary Keys</span></span>
<span data-ttu-id="74a22-103">일반적으로 데이터베이스 테이블에는 테이블의 각 행을 고유하게 식별하는 열 또는 열 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="74a22-104">이 식별 열 또는 열 그룹을 기본 키라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="74a22-105">단일 식별 되는 경우 <xref:System.Data.DataColumn> 으로 <xref:System.Data.DataTable.PrimaryKey%2A> 에 대 한를 <xref:System.Data.DataTable>, 테이블을 자동으로 설정 합니다 <xref:System.Data.DataColumn.AllowDBNull%2A> 열의 속성 **false** 및 <xref:System.Data.DataColumn.Unique%2A> 속성을  **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="74a22-106">여러 개의 열 기본 키의 경우에 **AllowDBNull** 속성으로 자동 설정 됩니다 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="74a22-107">**PrimaryKey** 의 속성을 <xref:System.Data.DataTable> 하나 이상의 배열 값으로 받습니다 **DataColumn** 다음 예와에서 같이 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="74a22-108">첫 번째 예제에서는 단일 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="74a22-109">다음 예제에서는 두 열이 기본 키로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a22-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74a22-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="74a22-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="74a22-111">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="74a22-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="74a22-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="74a22-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="74a22-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="74a22-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
