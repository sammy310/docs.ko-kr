---
title: 식 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: ad14e4d3d6a1107f994d9536485257f9dc1851f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166848"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="27fac-102">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="27fac-102">Creating Expression Columns</span></span>

<span data-ttu-id="27fac-103">테이블에서 같은 행의 다른 열 값이나 여러 행의 열 값에서 계산한 값을 포함할 수 있도록 열에 대한 식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27fac-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="27fac-104">계산할 식을 정의하려면 대상 열의 <xref:System.Data.DataColumn.Expression%2A> 속성과 <xref:System.Data.DataColumn.ColumnName%2A> 속성을 사용하여 식에서 다른 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="27fac-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="27fac-105">식 열의 <xref:System.Data.DataColumn.DataType%2A>은 이 식에서 반환되는 값에 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27fac-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="27fac-106">다음 표에서는 식 열을 사용할 수 있는 몇 가지 방법의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27fac-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="27fac-107">식 형식</span><span class="sxs-lookup"><span data-stu-id="27fac-107">Expression type</span></span>|<span data-ttu-id="27fac-108">예제</span><span class="sxs-lookup"><span data-stu-id="27fac-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="27fac-109">비교</span><span class="sxs-lookup"><span data-stu-id="27fac-109">Comparison</span></span>|<span data-ttu-id="27fac-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="27fac-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="27fac-111">계산</span><span class="sxs-lookup"><span data-stu-id="27fac-111">Computation</span></span>|<span data-ttu-id="27fac-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="27fac-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="27fac-113">집계</span><span class="sxs-lookup"><span data-stu-id="27fac-113">Aggregation</span></span>|<span data-ttu-id="27fac-114">합계 (가격)</span><span class="sxs-lookup"><span data-stu-id="27fac-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="27fac-115">기존 **DataColumn** 개체에서 **Expression** 속성을 설정 하거나, 다음 예제와 같이 생성자에 전달 되는 세 번째 인수로 속성을 포함할 수 있습니다 <xref:System.Data.DataColumn> .</span><span class="sxs-lookup"><span data-stu-id="27fac-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="27fac-116">식은 다른 식 열을 참조할 수 있습니다. 그러나 두 식이 서로를 참조하는 순환 참조에서는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="27fac-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="27fac-117">식 작성에 대 한 규칙은 <xref:System.Data.DataColumn.Expression%2A> **DataColumn** 클래스의 속성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27fac-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27fac-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27fac-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="27fac-119">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="27fac-119">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="27fac-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="27fac-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="27fac-121">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="27fac-121">ADO.NET Overview</span></span>](../ado-net-overview.md)
