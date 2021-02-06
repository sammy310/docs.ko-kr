---
description: '자세한 정보: 행 찾기'
title: 행 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: bf4752255945d5bbc0dd5551cd6e84c98fd78c3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652473"
---
# <a name="finding-rows"></a><span data-ttu-id="c5b3c-103">행 찾기</span><span class="sxs-lookup"><span data-stu-id="c5b3c-103">Finding Rows</span></span>

<span data-ttu-id="c5b3c-104"><xref:System.Data.DataView.Find%2A>의 <xref:System.Data.DataView.FindRows%2A> 및 <xref:System.Data.DataView> 메서드를 사용하여 행의 정렬 키 값에 따라 행을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-104">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="c5b3c-105">**Find** 및 **findrows** 메서드에서 검색 값의 대/소문자 구분은 기본의 **CaseSensitive** 속성에 의해 결정 됩니다 <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="c5b3c-105">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c5b3c-106">검색 값이 기존 정렬 키 값 전체와 일치해야 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-106">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="c5b3c-107">**Find** 메서드는 <xref:System.Data.DataRowView> 검색 조건과 일치 하는의 인덱스와 함께 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-107">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="c5b3c-108">검색 조건과 일치 하는 행이 두 개 이상 있으면 첫 번째 일치 하는 **DataRowView** 의 인덱스만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-108">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="c5b3c-109">일치 하는 항목이 없으면 **Find** 는-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-109">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="c5b3c-110">여러 행과 일치 하는 검색 결과를 반환 하려면 **Findrows** 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-110">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="c5b3c-111">**Findrows** 는 **DataView** 에서 일치 하는 모든 행을 참조 하는 **DataRowView** 배열을 반환 한다는 점을 제외 하 고 **Find** 메서드와 똑같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-111">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="c5b3c-112">일치 하는 항목이 없으면 **DataRowView** 배열이 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-112">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="c5b3c-113">**Find** 또는 **findrows** 메서드를 사용 하려면 **ApplyDefaultSort** 를 **true** 로 설정 하거나 **sort** 속성을 사용 하 여 정렬 순서를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-113">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="c5b3c-114">정렬 순서를 지정하지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-114">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="c5b3c-115">**Find** 및 **findrows** 메서드는 값 배열을 입력으로 사용 합니다 .이 값의 길이는 정렬 순서의 열 수와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-115">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="c5b3c-116">하나의 열에 대해 정렬하는 경우에는 하나의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-116">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="c5b3c-117">정렬 순서에 여러 열이 포함된 경우에는 개체 배열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-117">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="c5b3c-118">여러 열에 대해 정렬 하는 경우 개체 배열의 값은 **DataView** 의 **sort** 속성에 지정 된 열의 순서와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-118">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="c5b3c-119">다음 코드 예제에서는 단일 열 정렬 순서를 사용 하 여 **DataView** 에 대해 호출 되는 **Find** 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-119">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 <span data-ttu-id="c5b3c-120">**Sort** 속성이 여러 열을 지정 하는 경우 다음 코드 예제와 같이 **sort** 속성에 지정 된 순서에 따라 각 열에 대 한 검색 값을 사용 하 여 개체 배열을 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b3c-120">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5b3c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5b3c-121">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="c5b3c-122">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="c5b3c-122">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="c5b3c-123">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c5b3c-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
