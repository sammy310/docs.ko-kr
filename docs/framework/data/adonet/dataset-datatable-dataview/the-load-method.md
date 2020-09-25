---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: ea437d1f8ed567934acafbd8db1f8dba8eb22bcc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177542"
---
# <a name="the-load-method"></a><span data-ttu-id="bdaf4-102">로드 메서드</span><span class="sxs-lookup"><span data-stu-id="bdaf4-102">The Load Method</span></span>

<span data-ttu-id="bdaf4-103"><xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="bdaf4-104">가장 간단한 형식으로 **DataReader**인 단일 매개 변수를 허용 하는 오버 로드 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="bdaf4-105">이 폼에서는 행이 있는 **DataTable** 을 로드 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="bdaf4-106">필요에 따라 **LoadOption** 매개 변수를 지정 하 여 **DataTable**에 데이터를 추가 하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="bdaf4-107">**LoadOption** 매개 변수는 데이터 원본에서 들어오는 데이터를 테이블에 이미 있는 데이터와 결합 하는 방법을 설명 하기 때문에 **DataTable** 에 이미 데이터 행이 포함 되어 있는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="bdaf4-108">예를 들어 **PreserveCurrentValues** (기본값)는 **DataTable**에 행이 **추가** 된 것으로 표시 된 경우 **원래** 값 또는 각 열이 데이터 소스에서 일치 하는 행의 내용으로 설정 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="bdaf4-109">**현재** 값에는 행이 추가 될 때 할당 된 값이 유지 되 고 행의 **RowState** 가 **변경**된 것으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="bdaf4-110">다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="bdaf4-111">LoadOption 값</span><span class="sxs-lookup"><span data-stu-id="bdaf4-111">LoadOption value</span></span>|<span data-ttu-id="bdaf4-112">설명</span><span class="sxs-lookup"><span data-stu-id="bdaf4-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="bdaf4-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="bdaf4-113">**OverwriteRow**</span></span>|<span data-ttu-id="bdaf4-114">들어오는 행에 이미 **DataTable**에 있는 행과 같은 **PrimaryKey** 값이 있는 경우 각 열의 **원래** 값과 **현재** 값은 들어오는 행의 값으로 바뀌고 **RowState** 속성은 **변경 되지 않은 상태로**설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="bdaf4-115">**DataTable** 에 없는 데이터 원본의 행은 **RowState** 값이 **변경 되지**않은 상태로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="bdaf4-116">이 옵션을 적용 하면 데이터 원본의 내용과 일치 하도록 **DataTable** 의 내용이 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="bdaf4-117">**PreserveCurrentValues(기본값)**</span><span class="sxs-lookup"><span data-stu-id="bdaf4-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="bdaf4-118">들어오는 행에 이미 **DataTable**에 있는 행과 같은 **PrimaryKey** 값이 있으면 **원래** 값은 들어오는 행의 내용으로 설정 되 고 **현재** 값은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="bdaf4-119">**RowState** 를 **추가** 하거나 **수정**하는 경우 **수정**됨으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="bdaf4-120">**RowState** **삭제**된 경우 **삭제**된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="bdaf4-121">**DataTable** 에 없는 데이터 소스의 행이 추가 되 고 **RowState** 이 변경 되지 않은 **상태로**설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="bdaf4-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="bdaf4-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="bdaf4-123">들어오는 행에 이미 **DataTable**에 있는 행과 같은 **PrimaryKey** 값이 있는 경우 **현재** 값이 **원래** 값으로 복사 되 고 **현재** 값이 들어오는 행의 콘텐츠로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="bdaf4-124">**DataTable** 의 **RowState** 이 **추가**된 경우 **RowState** 는 **추가**된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="bdaf4-125">**Modified** 또는 **Deleted**로 표시 된 행의 경우에는 **RowState** 가 **수정**됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="bdaf4-126">**DataTable** 에 없는 데이터 소스의 행이 추가 되 고 **RowState** 이 **추가**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="bdaf4-127">다음 예제에서는 **Load** 메서드를 사용 하 여 **Northwind** 데이터베이스에 있는 직원의 생일 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdaf4-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdaf4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdaf4-128">See also</span></span>

- [<span data-ttu-id="bdaf4-129">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="bdaf4-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="bdaf4-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="bdaf4-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
