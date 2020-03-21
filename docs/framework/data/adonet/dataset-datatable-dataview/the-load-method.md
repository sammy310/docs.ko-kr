---
title: 로드 메서드
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150729"
---
# <a name="the-load-method"></a><span data-ttu-id="7d531-102">로드 메서드</span><span class="sxs-lookup"><span data-stu-id="7d531-102">The Load Method</span></span>
<span data-ttu-id="7d531-103"><xref:System.Data.DataTable.Load%2A> 메서드를 사용하여 데이터 소스의 행과 함께 <xref:System.Data.DataTable>을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="7d531-104">이것은 가장 간단한 형태로 단일 매개 변수인 **DataReader를**허용하는 오버로드된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="7d531-105">이 양식에서는 단순히 행으로 **DataTable을** 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="7d531-106">선택적으로 **LoadOption** 매개 변수를 지정하여 **DataTable**에 데이터가 추가되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="7d531-107">**LoadOption** 매개 변수는 **DataTable에** 데이터 원본의 들어오는 데이터가 테이블에 있는 데이터와 결합되는 방법을 설명하기 때문에 데이터 테이블이 이미 포함된 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="7d531-108">예를 **들어, PreserveCurrentValues(기본값)는** 행이 **DataTable에** **추가된** 것으로 표시된 **경우, 원본** 값 또는 각 열이 데이터 원본에서 일치하는 행의 내용으로 설정되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="7d531-109">**현재** 값은 행이 추가될 때 할당된 값을 유지하고 행의 **RowState가** **변경된**로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="7d531-110">다음 표에서는 <xref:System.Data.LoadOption> 열거형 값에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="7d531-111">LoadOption 값</span><span class="sxs-lookup"><span data-stu-id="7d531-111">LoadOption value</span></span>|<span data-ttu-id="7d531-112">Description</span><span class="sxs-lookup"><span data-stu-id="7d531-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="7d531-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="7d531-113">**OverwriteRow**</span></span>|<span data-ttu-id="7d531-114">들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지면 각 열의 **원본** 및 **현재** 값이 들어오는 행의 값으로 대체되고 **RowState** 속성이 **변경되지 않음으로**설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="7d531-115">**DataTable에** 아직 존재하지 않는 데이터 원본의 행은 **변경되지 않음의** **RowState** 값으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="7d531-116">이 옵션은 데이터 원본의 내용과 일치되도록 **DataTable의** 내용을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="7d531-117">**PreserveCurrentValues(기본값)**</span><span class="sxs-lookup"><span data-stu-id="7d531-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="7d531-118">들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지는 경우 **원래** 값은 들어오는 행의 내용으로 설정되고 **현재** 값은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="7d531-119">**RowState가** **추가또는** **수정된**경우 **은 수정된**로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="7d531-120">**RowState가** **삭제된**경우 은 **삭제된**상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="7d531-121">**DataTable에** 아직 존재하지 않는 데이터 원본의 행이 추가되고 **RowState가** **변경되지 않음으로**설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="7d531-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="7d531-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="7d531-123">들어오는 행이 **DataTable에**이미 있는 행과 동일한 **PrimaryKey** 값을 가지면 **현재** 값이 **원래** 값으로 복사되고 **현재** 값이 들어오는 행의 내용으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="7d531-124">**데이터 테이블의** **RowState가** **추가된**경우 **행 상태가** **추가된**상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="7d531-125">**수정됨** 또는 **삭제됨으로**표시된 행의 경우 **RowState가** **수정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7d531-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="7d531-126">**DataTable에** 아직 존재하지 않는 데이터 원본의 행이 추가되고 **RowState가** **추가된**로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="7d531-127">다음 샘플에서는 **Load** 메서드를 사용하여 **Northwind** 데이터베이스의 직원의 생일 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d531-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d531-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d531-128">See also</span></span>

- [<span data-ttu-id="7d531-129">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="7d531-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="7d531-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="7d531-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
