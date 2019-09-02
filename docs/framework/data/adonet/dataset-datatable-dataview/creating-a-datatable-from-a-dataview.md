---
title: DataView에서 DataTable 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d45cf41-d8ae-4409-af3e-a96a7e476d85
ms.openlocfilehash: 36839574ae8a8acd1cb56fa82ebcfa6bddb0c97e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203873"
---
# <a name="creating-a-datatable-from-a-dataview"></a><span data-ttu-id="85f01-102">DataView에서 DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="85f01-102">Creating a DataTable from a DataView</span></span>
<span data-ttu-id="85f01-103">데이터 소스에서 데이터를 검색하여 이 데이터로 <xref:System.Data.DataTable>을 채웠으면 해당 데이터를 다시 검색하지 않고 반환된 데이터를 정렬하고 필터링하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-103">Once you have retrieved data from a data source, and have filled a <xref:System.Data.DataTable> with the data, you may want to sort, filter, or otherwise limit the returned data without retrieving it again.</span></span> <span data-ttu-id="85f01-104">이러한 작업은 <xref:System.Data.DataView> 클래스를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-104">The <xref:System.Data.DataView> class makes this possible.</span></span> <span data-ttu-id="85f01-105">또한 <xref:System.Data.DataTable> <xref:System.Data.DataView.ToTable%2A> 에서 새을 만들어야 하는 경우 메서드를 사용 하 여 모든 행과 열 또는 데이터의 하위 집합을 새 <xref:System.Data.DataTable>에 복사할 수 있습니다. <xref:System.Data.DataView></span><span class="sxs-lookup"><span data-stu-id="85f01-105">In addition, if you need to create a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView>, you can use the <xref:System.Data.DataView.ToTable%2A> method to copy all the rows and columns, or a subset of the data into a new <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="85f01-106"><xref:System.Data.DataView.ToTable%2A> 메서드는 다음 작업을 위한 오버로드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-106">The <xref:System.Data.DataView.ToTable%2A> method provides overloads to:</span></span>  
  
- <span data-ttu-id="85f01-107"><xref:System.Data.DataTable>에 있는 열의 하위 집합인 열이 포함된 <xref:System.Data.DataView>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-107">Create a <xref:System.Data.DataTable> containing columns that are a subset of the columns in the <xref:System.Data.DataView>.</span></span>  
  
- <span data-ttu-id="85f01-108">Transact-sql의 <xref:System.Data.DataTable> distinct 키워드 <xref:System.Data.DataView>와와 유사의 고유 행만 포함 하는을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-108">Create a <xref:System.Data.DataTable> that includes only distinct rows from the <xref:System.Data.DataView>, analogously to the DISTINCT keyword in Transact-SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85f01-109">예제</span><span class="sxs-lookup"><span data-stu-id="85f01-109">Example</span></span>  
 <span data-ttu-id="85f01-110">다음 콘솔 응용 프로그램 예제에서는 <xref:System.Data.DataTable> **AdventureWorks** 샘플 데이터베이스의 **Contact** 테이블에서 데이터를 포함 하는을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-110">The following console application example creates a <xref:System.Data.DataTable> that contains data from the **Person.Contact** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="85f01-111">그런 다음에 따라 <xref:System.Data.DataView> <xref:System.Data.DataTable>정렬 및 필터링 된를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-111">Next, the example creates a sorted and filtered <xref:System.Data.DataView> based on the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="85f01-112"><xref:System.Data.DataView>이 예제에서는 <xref:System.Data.DataTable> 및의 내용을 표시 한 후 <xref:System.Data.DataView.ToTable%2A> 메서드를 호출 하 고 <xref:System.Data.DataTable> 사용 가능한 <xref:System.Data.DataView> 열의 일부만 선택 하 여에서 새를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-112">After displaying the contents of the <xref:System.Data.DataTable> and the <xref:System.Data.DataView>, the example creates a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView> by calling the <xref:System.Data.DataView.ToTable%2A> method, selecting only a subset of the available columns.</span></span> <span data-ttu-id="85f01-113">마지막으로 이 예제에서는 새 <xref:System.Data.DataTable>의 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="85f01-113">Finally, the example displays the contents of the new <xref:System.Data.DataTable>.</span></span>  
  
```vb  
Private Sub DemonstrateDataView()  
    ' Retrieve a DataTable from the AdventureWorks sample database.  
    ' connectionString is assumed to be a valid connection string.  
    Dim adapter As New SqlDataAdapter( _  
       "SELECT FirstName, LastName, EmailAddress FROM Person.Contact WHERE FirstName LIKE 'Mich%'", connectionString)  
    Dim table As New DataTable  
  
    adapter.Fill(table)  
    Console.WriteLine("Original table name: " & table.TableName)  
    ' Print current table values.  
    PrintTableOrView(table, "Current Values in Table")  
  
    ' Now create a DataView based on the DataTable.  
    ' Sort and filter the data.  
    Dim view As DataView = table.DefaultView  
    view.Sort = "LastName, FirstName"  
    view.RowFilter = "LastName > 'M'"  
    PrintTableOrView(view, "Current Values in View")  
  
    ' Create a new DataTable based on the DataView,  
    ' requesting only two columns with distinct values  
    ' in the columns.  
    Dim newTable As DataTable = view.ToTable("UniqueLastNames", True, "FirstName", "LastName")  
    PrintTableOrView(newTable, "Table created from DataView")  
    Console.WriteLine("New table name: " & newTable.TableName)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
    End Sub  
  
Private Sub PrintTableOrView(ByVal dv As DataView, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
    Dim table As DataTable = dv.Table  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the view.  
    For Each rowView As DataRowView In dv  
        sw = New System.IO.StringWriter  
  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(rowView(col.ColumnName).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
End Sub  
  
Private Sub PrintTableOrView(ByVal table As DataTable, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the table.  
    For Each row As DataRow In table.Rows  
        sw = New System.IO.StringWriter  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(row(col).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
    End Sub  
End Module  
```  
  
```csharp  
private static void DemonstrateDataView()  
{  
// Retrieve a DataTable from the AdventureWorks sample database.  
// connectionString is assumed to be a valid connection string.  
SqlDataAdapter adapter = new SqlDataAdapter(  
    "SELECT FirstName, LastName, EmailAddress " +  
    "FROM Person.Contact WHERE FirstName LIKE 'Mich%'",   
       GetConnectionString());  
DataTable table = new DataTable();  
  
adapter.Fill(table);  
Console.WriteLine("Original table name: " + table.TableName);  
// Print current table values.  
PrintTableOrView(table, "Current Values in Table");  
  
// Now create a DataView based on the DataTable.  
// Sort and filter the data.  
DataView view = table.DefaultView;  
view.Sort = "LastName, FirstName";  
view.RowFilter = "LastName > 'M'";  
PrintTableOrView(view, "Current Values in View");  
  
// Create a new DataTable based on the DataView,  
// requesting only two columns with distinct values  
// in the columns.  
DataTable newTable = view.ToTable("UniqueLastNames",  
     true, "FirstName", "LastName");  
PrintTableOrView(newTable, "Table created from DataView");  
Console.WriteLine("New table name: " + newTable.TableName);  
  
Console.WriteLine("Press any key to continue.");  
Console.ReadKey();  
}  
  
private static void PrintTableOrView(DataView dv, string label)  
{  
System.IO.StringWriter sw;  
string output;  
DataTable table = dv.Table;  
  
Console.WriteLine(label);  
  
// Loop through each row in the view.  
foreach (DataRowView rowView in dv)  
{  
    sw = new System.IO.StringWriter();  
  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(rowView[col.ColumnName].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
}  
Console.WriteLine();  
}  
  
private static void PrintTableOrView(DataTable table, string label)  
{  
System.IO.StringWriter sw;  
string output;  
  
Console.WriteLine(label);  
  
// Loop through each row in the table.  
foreach (DataRow row in table.Rows)  
{  
    sw = new System.IO.StringWriter();  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(row[col].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
} //  
Console.WriteLine();  
}  
```  
  
 <span data-ttu-id="85f01-114">}</span><span class="sxs-lookup"><span data-stu-id="85f01-114">}</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f01-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="85f01-115">See also</span></span>

- <xref:System.Data.DataView.ToTable%2A>
- [<span data-ttu-id="85f01-116">DataView</span><span class="sxs-lookup"><span data-stu-id="85f01-116">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="85f01-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="85f01-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
