---
title: 행 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 72af4b049153ce647cc1ceb2d40c3b17cc7ed988
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880063"
---
# <a name="finding-rows"></a><span data-ttu-id="62601-102">행 찾기</span><span class="sxs-lookup"><span data-stu-id="62601-102">Finding Rows</span></span>
<span data-ttu-id="62601-103"><xref:System.Data.DataView.Find%2A>의 <xref:System.Data.DataView.FindRows%2A> 및 <xref:System.Data.DataView> 메서드를 사용하여 행의 정렬 키 값에 따라 행을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62601-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="62601-104">검색의 대/소문자 구분 값을 **찾을** 및 **FindRows** 메서드에 의해 결정 됩니다는 **CaseSensitive** 속성에 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="62601-105">검색 값이 기존 정렬 키 값 전체와 일치해야 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62601-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="62601-106">합니다 **찾을** 의 인덱스를 사용 하 여 정수를 반환 하는 메서드는 <xref:System.Data.DataRowView> 검색 조건과 일치 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="62601-107">둘 이상의 행 일치 조건과 일치 하는 첫 번째 인덱스만 **DataRowView** 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62601-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="62601-108">일치 하는 경우 **찾을** -1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="62601-109">여러 행과 일치 하는 검색 결과 반환 하려면 사용 합니다 **FindRows** 메서드.</span><span class="sxs-lookup"><span data-stu-id="62601-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="62601-110">**FindRows** 처럼 작동 합니다 **찾을** 메서드를 반환 한다는 점을 제외 하 고를 **DataRowView** 에서 일치 하는 모든 행을 참조 하는 배열을 **DataView**.</span><span class="sxs-lookup"><span data-stu-id="62601-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="62601-111">일치 하는 경우는 **DataRowView** 배열은 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62601-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="62601-112">사용 하는 **찾을** 또는 **FindRows** 정렬을 지정 해야 하는 방법을 설정 하거나 주문 **ApplyDefaultSort** 에 **true** 또는 사용 하 여는 **정렬** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="62601-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="62601-113">정렬 순서를 지정하지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="62601-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="62601-114">**찾을** 하 고 **FindRows** 메서드는 값의 배열 길이가 정렬 순서에서 열 수와 일치 하는 입력으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="62601-115">하나의 열에 대해 정렬하는 경우에는 하나의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62601-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="62601-116">정렬 순서에 여러 열이 포함된 경우에는 개체 배열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="62601-117">여러 열 정렬에 대 한 개체 배열의 값 일치 해야 합니다에 지정 된 열의 순서를 **정렬** 의 속성을 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="62601-118">다음 코드 예제는 **찾을** 메서드를 호출 하는 **DataView** 단일 열 정렬 순서를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="62601-119">경우에 **정렬** 여러 열을 지정 하는 속성, 지정 된 순서에서 각 열에 대 한 검색 값을 사용 하 여 개체 배열을 전달 해야 합니다는 **정렬** 속성을 다음 코드 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="62601-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62601-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="62601-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="62601-121">DataView</span><span class="sxs-lookup"><span data-stu-id="62601-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="62601-122">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="62601-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
