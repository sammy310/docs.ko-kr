---
description: '자세한 정보: 식 열 만들기'
title: 식 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 96b445734d645a957951a1d4cbd9d72ed254068f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724988"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="3c0d3-103">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="3c0d3-103">Creating Expression Columns</span></span>

<span data-ttu-id="3c0d3-104">테이블에서 같은 행의 다른 열 값이나 여러 행의 열 값에서 계산한 값을 포함할 수 있도록 열에 대한 식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-104">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="3c0d3-105">계산할 식을 정의하려면 대상 열의 <xref:System.Data.DataColumn.Expression%2A> 속성과 <xref:System.Data.DataColumn.ColumnName%2A> 속성을 사용하여 식에서 다른 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-105">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="3c0d3-106">식 열의 <xref:System.Data.DataColumn.DataType%2A>은 이 식에서 반환되는 값에 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-106">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="3c0d3-107">다음 표에서는 식 열을 사용할 수 있는 몇 가지 방법의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-107">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="3c0d3-108">식 형식</span><span class="sxs-lookup"><span data-stu-id="3c0d3-108">Expression type</span></span>|<span data-ttu-id="3c0d3-109">예제</span><span class="sxs-lookup"><span data-stu-id="3c0d3-109">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="3c0d3-110">비교</span><span class="sxs-lookup"><span data-stu-id="3c0d3-110">Comparison</span></span>|<span data-ttu-id="3c0d3-111">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="3c0d3-111">"Total >= 500"</span></span>|  
|<span data-ttu-id="3c0d3-112">계산</span><span class="sxs-lookup"><span data-stu-id="3c0d3-112">Computation</span></span>|<span data-ttu-id="3c0d3-113">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="3c0d3-113">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="3c0d3-114">집계</span><span class="sxs-lookup"><span data-stu-id="3c0d3-114">Aggregation</span></span>|<span data-ttu-id="3c0d3-115">합계 (가격)</span><span class="sxs-lookup"><span data-stu-id="3c0d3-115">Sum(Price)</span></span>|  
  
 <span data-ttu-id="3c0d3-116">기존 **DataColumn** 개체에서 **Expression** 속성을 설정 하거나, 다음 예제와 같이 생성자에 전달 되는 세 번째 인수로 속성을 포함할 수 있습니다 <xref:System.Data.DataColumn> .</span><span class="sxs-lookup"><span data-stu-id="3c0d3-116">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="3c0d3-117">식은 다른 식 열을 참조할 수 있습니다. 그러나 두 식이 서로를 참조하는 순환 참조에서는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-117">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="3c0d3-118">식 작성에 대 한 규칙은 <xref:System.Data.DataColumn.Expression%2A> **DataColumn** 클래스의 속성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c0d3-118">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0d3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c0d3-119">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="3c0d3-120">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="3c0d3-120">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="3c0d3-121">DataTables</span><span class="sxs-lookup"><span data-stu-id="3c0d3-121">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="3c0d3-122">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="3c0d3-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
