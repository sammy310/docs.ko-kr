---
title: 스키마 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: d0250e573dc24bfcad97a2f2606cb2e6c8e520da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782764"
---
# <a name="schema-restrictions"></a><span data-ttu-id="cebea-102">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="cebea-102">Schema Restrictions</span></span>
<span data-ttu-id="cebea-103">**Getschema** 메서드의 두 번째 선택적 매개 변수는 반환 되는 스키마 정보의 양을 제한 하는 데 사용 되는 제한 사항이 며 **getschema** 메서드에 문자열 배열로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="cebea-104">배열의 위치는 전달할 수 있는 값을 결정하며 이 위치는 제한 번호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="cebea-105">예를 들어 다음 표에는 .NET Framework Data Provider for SQL Server를 사용하는 "Table" 스키마 컬렉션에서 지원되는 제한에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="cebea-106">SQL Server 스키마 컬렉션의 추가 제한은 이 항목의 맨 마지막에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="cebea-107">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-107">Restriction Name</span></span>|<span data-ttu-id="cebea-108">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-108">Parameter Name</span></span>|<span data-ttu-id="cebea-109">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-109">Restriction Default</span></span>|<span data-ttu-id="cebea-110">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-111">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-112">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-113">1</span><span class="sxs-lookup"><span data-stu-id="cebea-113">1</span></span>|  
|<span data-ttu-id="cebea-114">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-114">Owner</span></span>|@Owner|<span data-ttu-id="cebea-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-116">2</span><span class="sxs-lookup"><span data-stu-id="cebea-116">2</span></span>|  
|<span data-ttu-id="cebea-117">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-117">Table</span></span>|@Name|<span data-ttu-id="cebea-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-118">TABLE_NAME</span></span>|<span data-ttu-id="cebea-119">3</span><span class="sxs-lookup"><span data-stu-id="cebea-119">3</span></span>|  
|<span data-ttu-id="cebea-120">TableType</span><span class="sxs-lookup"><span data-stu-id="cebea-120">TableType</span></span>|@TableType|<span data-ttu-id="cebea-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cebea-121">TABLE_TYPE</span></span>|<span data-ttu-id="cebea-122">4</span><span class="sxs-lookup"><span data-stu-id="cebea-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="cebea-123">제한 값 지정</span><span class="sxs-lookup"><span data-stu-id="cebea-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="cebea-124">"Tables" 스키마 컬렉션의 제한 중 하나를 사용하려면 네 가지 요소로 된 문자열 배열을 만든 다음 제한 번호와 일치하는 요소에 값을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="cebea-125">예를 들어 **getschema** 메서드에서 반환 되는 테이블을 "sales" 스키마의 테이블로만 제한 하려면 **getschema** 메서드로 전달 하기 전에 배열의 두 번째 요소를 "sales"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cebea-126">`SqlClient` 및 `OracleClient`의 제한 컬렉션에는 하나의 추가 `ParameterName` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="cebea-127">제한 기본 열은 이전 버전과 여전히 호환되지만 현재는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="cebea-128">문자열 대체보다는 매개 변수가 있는 쿼리를 사용하여 제한 값을 지정할 때 SQL 삽입 공격 위험을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cebea-129">배열의 요소 개수는 지정된 스키마 컬렉션에 대해 지원되는 제한 개수보다 작거나 같아야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="cebea-130">제한의 최대 개수보다 작을 수 있으며</span><span class="sxs-lookup"><span data-stu-id="cebea-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="cebea-131">제한이 없으면 null(무제한)로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="cebea-132">.NET Framework 관리 공급자를 쿼리하여 제한 스키마 컬렉션의 이름 ("제한 사항")으로 **GetSchema** 메서드를 호출 하 여 지원 되는 제한 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="cebea-133">그러면 컬렉션 이름, 제한 이름, 기본 제한 값 및 제한 번호 목록과 함께 <xref:System.Data.DataTable>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="cebea-134">예제</span><span class="sxs-lookup"><span data-stu-id="cebea-134">Example</span></span>  
 <span data-ttu-id="cebea-135">다음 예에서는 SQL Server <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> <xref:System.Data.SqlClient.SqlConnection> 클래스에 대해 .NET Framework Data Provider의 메서드를 사용 하 여 **AdventureWorks** 예제 데이터베이스에 포함 된 모든 테이블에 대 한 스키마 정보를 검색 하는 방법을 보여 줍니다. 반환 되는 정보를 "Sales" 스키마의 해당 테이블로만 제한 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="cebea-136">SQL Server 스키마 제한</span><span class="sxs-lookup"><span data-stu-id="cebea-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="cebea-137">다음 표에는 SQL Server 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="cebea-138">사용자</span><span class="sxs-lookup"><span data-stu-id="cebea-138">Users</span></span>  
  
|<span data-ttu-id="cebea-139">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-139">Restriction Name</span></span>|<span data-ttu-id="cebea-140">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-140">Parameter Name</span></span>|<span data-ttu-id="cebea-141">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-141">Restriction Default</span></span>|<span data-ttu-id="cebea-142">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="cebea-143">User_Name</span></span>|@Name|<span data-ttu-id="cebea-144">name</span><span class="sxs-lookup"><span data-stu-id="cebea-144">name</span></span>|<span data-ttu-id="cebea-145">1</span><span class="sxs-lookup"><span data-stu-id="cebea-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="cebea-146">데이터베이스</span><span class="sxs-lookup"><span data-stu-id="cebea-146">Databases</span></span>  
  
|<span data-ttu-id="cebea-147">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-147">Restriction Name</span></span>|<span data-ttu-id="cebea-148">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-148">Parameter Name</span></span>|<span data-ttu-id="cebea-149">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-149">Restriction Default</span></span>|<span data-ttu-id="cebea-150">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-151">이름</span><span class="sxs-lookup"><span data-stu-id="cebea-151">Name</span></span>|@Name|<span data-ttu-id="cebea-152">이름</span><span class="sxs-lookup"><span data-stu-id="cebea-152">Name</span></span>|<span data-ttu-id="cebea-153">1</span><span class="sxs-lookup"><span data-stu-id="cebea-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="cebea-154">테이블</span><span class="sxs-lookup"><span data-stu-id="cebea-154">Tables</span></span>  
  
|<span data-ttu-id="cebea-155">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-155">Restriction Name</span></span>|<span data-ttu-id="cebea-156">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-156">Parameter Name</span></span>|<span data-ttu-id="cebea-157">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-157">Restriction Default</span></span>|<span data-ttu-id="cebea-158">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-159">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-160">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-161">1</span><span class="sxs-lookup"><span data-stu-id="cebea-161">1</span></span>|  
|<span data-ttu-id="cebea-162">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-162">Owner</span></span>|@Owner|<span data-ttu-id="cebea-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-164">2</span><span class="sxs-lookup"><span data-stu-id="cebea-164">2</span></span>|  
|<span data-ttu-id="cebea-165">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-165">Table</span></span>|@Name|<span data-ttu-id="cebea-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-166">TABLE_NAME</span></span>|<span data-ttu-id="cebea-167">3</span><span class="sxs-lookup"><span data-stu-id="cebea-167">3</span></span>|  
|<span data-ttu-id="cebea-168">TableType</span><span class="sxs-lookup"><span data-stu-id="cebea-168">TableType</span></span>|@TableType|<span data-ttu-id="cebea-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cebea-169">TABLE_TYPE</span></span>|<span data-ttu-id="cebea-170">4</span><span class="sxs-lookup"><span data-stu-id="cebea-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cebea-171">열</span><span class="sxs-lookup"><span data-stu-id="cebea-171">Columns</span></span>  
  
|<span data-ttu-id="cebea-172">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-172">Restriction Name</span></span>|<span data-ttu-id="cebea-173">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-173">Parameter Name</span></span>|<span data-ttu-id="cebea-174">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-174">Restriction Default</span></span>|<span data-ttu-id="cebea-175">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-176">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-177">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-178">1</span><span class="sxs-lookup"><span data-stu-id="cebea-178">1</span></span>|  
|<span data-ttu-id="cebea-179">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-179">Owner</span></span>|@Owner|<span data-ttu-id="cebea-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-181">2</span><span class="sxs-lookup"><span data-stu-id="cebea-181">2</span></span>|  
|<span data-ttu-id="cebea-182">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-182">Table</span></span>|@Table|<span data-ttu-id="cebea-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-183">TABLE_NAME</span></span>|<span data-ttu-id="cebea-184">3</span><span class="sxs-lookup"><span data-stu-id="cebea-184">3</span></span>|  
|<span data-ttu-id="cebea-185">Column</span><span class="sxs-lookup"><span data-stu-id="cebea-185">Column</span></span>|@Column|<span data-ttu-id="cebea-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-186">COLUMN_NAME</span></span>|<span data-ttu-id="cebea-187">4</span><span class="sxs-lookup"><span data-stu-id="cebea-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="cebea-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="cebea-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="cebea-189">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-189">Restriction Name</span></span>|<span data-ttu-id="cebea-190">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-190">Parameter Name</span></span>|<span data-ttu-id="cebea-191">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-191">Restriction Default</span></span>|<span data-ttu-id="cebea-192">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-193">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-194">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-195">1</span><span class="sxs-lookup"><span data-stu-id="cebea-195">1</span></span>|  
|<span data-ttu-id="cebea-196">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-196">Owner</span></span>|@Owner|<span data-ttu-id="cebea-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-198">2</span><span class="sxs-lookup"><span data-stu-id="cebea-198">2</span></span>|  
|<span data-ttu-id="cebea-199">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-199">Table</span></span>|@Table|<span data-ttu-id="cebea-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-200">TABLE_NAME</span></span>|<span data-ttu-id="cebea-201">3</span><span class="sxs-lookup"><span data-stu-id="cebea-201">3</span></span>|  
|<span data-ttu-id="cebea-202">Column</span><span class="sxs-lookup"><span data-stu-id="cebea-202">Column</span></span>|@Column|<span data-ttu-id="cebea-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-203">COLUMN_NAME</span></span>|<span data-ttu-id="cebea-204">4</span><span class="sxs-lookup"><span data-stu-id="cebea-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="cebea-205">뷰</span><span class="sxs-lookup"><span data-stu-id="cebea-205">Views</span></span>  
  
|<span data-ttu-id="cebea-206">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-206">Restriction Name</span></span>|<span data-ttu-id="cebea-207">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-207">Parameter Name</span></span>|<span data-ttu-id="cebea-208">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-208">Restriction Default</span></span>|<span data-ttu-id="cebea-209">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-210">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-211">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-212">1</span><span class="sxs-lookup"><span data-stu-id="cebea-212">1</span></span>|  
|<span data-ttu-id="cebea-213">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-213">Owner</span></span>|@Owner|<span data-ttu-id="cebea-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-215">2</span><span class="sxs-lookup"><span data-stu-id="cebea-215">2</span></span>|  
|<span data-ttu-id="cebea-216">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-216">Table</span></span>|@Table|<span data-ttu-id="cebea-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-217">TABLE_NAME</span></span>|<span data-ttu-id="cebea-218">3</span><span class="sxs-lookup"><span data-stu-id="cebea-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="cebea-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="cebea-219">ViewColumns</span></span>  
  
|<span data-ttu-id="cebea-220">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-220">Restriction Name</span></span>|<span data-ttu-id="cebea-221">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-221">Parameter Name</span></span>|<span data-ttu-id="cebea-222">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-222">Restriction Default</span></span>|<span data-ttu-id="cebea-223">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-224">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-225">VIEW_CATALOG</span></span>|<span data-ttu-id="cebea-226">1</span><span class="sxs-lookup"><span data-stu-id="cebea-226">1</span></span>|  
|<span data-ttu-id="cebea-227">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-227">Owner</span></span>|@Owner|<span data-ttu-id="cebea-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="cebea-229">2</span><span class="sxs-lookup"><span data-stu-id="cebea-229">2</span></span>|  
|<span data-ttu-id="cebea-230">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-230">Table</span></span>|@Table|<span data-ttu-id="cebea-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-231">VIEW_NAME</span></span>|<span data-ttu-id="cebea-232">3</span><span class="sxs-lookup"><span data-stu-id="cebea-232">3</span></span>|  
|<span data-ttu-id="cebea-233">Column</span><span class="sxs-lookup"><span data-stu-id="cebea-233">Column</span></span>|@Column|<span data-ttu-id="cebea-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-234">COLUMN_NAME</span></span>|<span data-ttu-id="cebea-235">4</span><span class="sxs-lookup"><span data-stu-id="cebea-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="cebea-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cebea-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="cebea-237">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-237">Restriction Name</span></span>|<span data-ttu-id="cebea-238">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-238">Parameter Name</span></span>|<span data-ttu-id="cebea-239">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-239">Restriction Default</span></span>|<span data-ttu-id="cebea-240">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-241">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="cebea-243">1</span><span class="sxs-lookup"><span data-stu-id="cebea-243">1</span></span>|  
|<span data-ttu-id="cebea-244">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-244">Owner</span></span>|@Owner|<span data-ttu-id="cebea-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="cebea-246">2</span><span class="sxs-lookup"><span data-stu-id="cebea-246">2</span></span>|  
|<span data-ttu-id="cebea-247">이름</span><span class="sxs-lookup"><span data-stu-id="cebea-247">Name</span></span>|@Name|<span data-ttu-id="cebea-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="cebea-249">3</span><span class="sxs-lookup"><span data-stu-id="cebea-249">3</span></span>|  
|<span data-ttu-id="cebea-250">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cebea-250">Parameter</span></span>|@Parameter|<span data-ttu-id="cebea-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-251">PARAMETER_NAME</span></span>|<span data-ttu-id="cebea-252">4</span><span class="sxs-lookup"><span data-stu-id="cebea-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cebea-253">절차</span><span class="sxs-lookup"><span data-stu-id="cebea-253">Procedures</span></span>  
  
|<span data-ttu-id="cebea-254">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-254">Restriction Name</span></span>|<span data-ttu-id="cebea-255">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-255">Parameter Name</span></span>|<span data-ttu-id="cebea-256">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-256">Restriction Default</span></span>|<span data-ttu-id="cebea-257">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-258">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="cebea-260">1</span><span class="sxs-lookup"><span data-stu-id="cebea-260">1</span></span>|  
|<span data-ttu-id="cebea-261">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-261">Owner</span></span>|@Owner|<span data-ttu-id="cebea-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="cebea-263">2</span><span class="sxs-lookup"><span data-stu-id="cebea-263">2</span></span>|  
|<span data-ttu-id="cebea-264">이름</span><span class="sxs-lookup"><span data-stu-id="cebea-264">Name</span></span>|@Name|<span data-ttu-id="cebea-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="cebea-266">3</span><span class="sxs-lookup"><span data-stu-id="cebea-266">3</span></span>|  
|<span data-ttu-id="cebea-267">형식</span><span class="sxs-lookup"><span data-stu-id="cebea-267">Type</span></span>|@Type|<span data-ttu-id="cebea-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cebea-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="cebea-269">4</span><span class="sxs-lookup"><span data-stu-id="cebea-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="cebea-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="cebea-270">IndexColumns</span></span>  
  
|<span data-ttu-id="cebea-271">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-271">Restriction Name</span></span>|<span data-ttu-id="cebea-272">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-272">Parameter Name</span></span>|<span data-ttu-id="cebea-273">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-273">Restriction Default</span></span>|<span data-ttu-id="cebea-274">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-275">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="cebea-276">db_name()</span></span>|<span data-ttu-id="cebea-277">1</span><span class="sxs-lookup"><span data-stu-id="cebea-277">1</span></span>|  
|<span data-ttu-id="cebea-278">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-278">Owner</span></span>|@Owner|<span data-ttu-id="cebea-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="cebea-279">user_name()</span></span>|<span data-ttu-id="cebea-280">2</span><span class="sxs-lookup"><span data-stu-id="cebea-280">2</span></span>|  
|<span data-ttu-id="cebea-281">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-281">Table</span></span>|@Table|<span data-ttu-id="cebea-282">o.name</span><span class="sxs-lookup"><span data-stu-id="cebea-282">o.name</span></span>|<span data-ttu-id="cebea-283">3</span><span class="sxs-lookup"><span data-stu-id="cebea-283">3</span></span>|  
|<span data-ttu-id="cebea-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="cebea-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="cebea-285">x.name</span><span class="sxs-lookup"><span data-stu-id="cebea-285">x.name</span></span>|<span data-ttu-id="cebea-286">4</span><span class="sxs-lookup"><span data-stu-id="cebea-286">4</span></span>|  
|<span data-ttu-id="cebea-287">Column</span><span class="sxs-lookup"><span data-stu-id="cebea-287">Column</span></span>|@Column|<span data-ttu-id="cebea-288">c.name</span><span class="sxs-lookup"><span data-stu-id="cebea-288">c.name</span></span>|<span data-ttu-id="cebea-289">5</span><span class="sxs-lookup"><span data-stu-id="cebea-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="cebea-290">인덱스</span><span class="sxs-lookup"><span data-stu-id="cebea-290">Indexes</span></span>  
  
|<span data-ttu-id="cebea-291">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-291">Restriction Name</span></span>|<span data-ttu-id="cebea-292">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-292">Parameter Name</span></span>|<span data-ttu-id="cebea-293">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-293">Restriction Default</span></span>|<span data-ttu-id="cebea-294">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-295">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="cebea-296">db_name()</span></span>|<span data-ttu-id="cebea-297">1</span><span class="sxs-lookup"><span data-stu-id="cebea-297">1</span></span>|  
|<span data-ttu-id="cebea-298">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-298">Owner</span></span>|@Owner|<span data-ttu-id="cebea-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="cebea-299">user_name()</span></span>|<span data-ttu-id="cebea-300">2</span><span class="sxs-lookup"><span data-stu-id="cebea-300">2</span></span>|  
|<span data-ttu-id="cebea-301">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-301">Table</span></span>|@Table|<span data-ttu-id="cebea-302">o.name</span><span class="sxs-lookup"><span data-stu-id="cebea-302">o.name</span></span>|<span data-ttu-id="cebea-303">3</span><span class="sxs-lookup"><span data-stu-id="cebea-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="cebea-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="cebea-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="cebea-305">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-305">Restriction Name</span></span>|<span data-ttu-id="cebea-306">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-306">Parameter Name</span></span>|<span data-ttu-id="cebea-307">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-307">Restriction Default</span></span>|<span data-ttu-id="cebea-308">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="cebea-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="cebea-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="cebea-310">assemblies.name</span></span>|<span data-ttu-id="cebea-311">1</span><span class="sxs-lookup"><span data-stu-id="cebea-311">1</span></span>|  
|<span data-ttu-id="cebea-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="cebea-312">udt_name</span></span>|@UDTName|<span data-ttu-id="cebea-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="cebea-313">types.assembly_class</span></span>|<span data-ttu-id="cebea-314">2</span><span class="sxs-lookup"><span data-stu-id="cebea-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="cebea-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="cebea-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="cebea-316">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-316">Restriction Name</span></span>|<span data-ttu-id="cebea-317">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-317">Parameter Name</span></span>|<span data-ttu-id="cebea-318">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-318">Restriction Default</span></span>|<span data-ttu-id="cebea-319">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-320">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="cebea-322">1</span><span class="sxs-lookup"><span data-stu-id="cebea-322">1</span></span>|  
|<span data-ttu-id="cebea-323">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-323">Owner</span></span>|@Owner|<span data-ttu-id="cebea-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="cebea-325">2</span><span class="sxs-lookup"><span data-stu-id="cebea-325">2</span></span>|  
|<span data-ttu-id="cebea-326">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-326">Table</span></span>|@Table|<span data-ttu-id="cebea-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-327">TABLE_NAME</span></span>|<span data-ttu-id="cebea-328">3</span><span class="sxs-lookup"><span data-stu-id="cebea-328">3</span></span>|  
|<span data-ttu-id="cebea-329">이름</span><span class="sxs-lookup"><span data-stu-id="cebea-329">Name</span></span>|@Name|<span data-ttu-id="cebea-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="cebea-331">4</span><span class="sxs-lookup"><span data-stu-id="cebea-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="cebea-332">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="cebea-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="cebea-333">다음 표에는 SQL Server 2008 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="cebea-334">이러한 제한은 .NET Framework 버전 3.5 SP1 및 SQL Server 2008 이상에서 유효하며</span><span class="sxs-lookup"><span data-stu-id="cebea-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="cebea-335">이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebea-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="cebea-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="cebea-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="cebea-337">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-337">Restriction Name</span></span>|<span data-ttu-id="cebea-338">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-338">Parameter Name</span></span>|<span data-ttu-id="cebea-339">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-339">Restriction Default</span></span>|<span data-ttu-id="cebea-340">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-341">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-342">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-343">1</span><span class="sxs-lookup"><span data-stu-id="cebea-343">1</span></span>|  
|<span data-ttu-id="cebea-344">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-344">Owner</span></span>|@Owner|<span data-ttu-id="cebea-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-346">2</span><span class="sxs-lookup"><span data-stu-id="cebea-346">2</span></span>|  
|<span data-ttu-id="cebea-347">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-347">Table</span></span>|@Table|<span data-ttu-id="cebea-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-348">TABLE_NAME</span></span>|<span data-ttu-id="cebea-349">3</span><span class="sxs-lookup"><span data-stu-id="cebea-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="cebea-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="cebea-350">AllColumns</span></span>  
  
|<span data-ttu-id="cebea-351">제한 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-351">Restriction Name</span></span>|<span data-ttu-id="cebea-352">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="cebea-352">Parameter Name</span></span>|<span data-ttu-id="cebea-353">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="cebea-353">Restriction Default</span></span>|<span data-ttu-id="cebea-354">제한 번호</span><span class="sxs-lookup"><span data-stu-id="cebea-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="cebea-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="cebea-355">Catalog</span></span>|@Catalog|<span data-ttu-id="cebea-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cebea-356">TABLE_CATALOG</span></span>|<span data-ttu-id="cebea-357">1</span><span class="sxs-lookup"><span data-stu-id="cebea-357">1</span></span>|  
|<span data-ttu-id="cebea-358">소유자</span><span class="sxs-lookup"><span data-stu-id="cebea-358">Owner</span></span>|@Owner|<span data-ttu-id="cebea-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cebea-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="cebea-360">2</span><span class="sxs-lookup"><span data-stu-id="cebea-360">2</span></span>|  
|<span data-ttu-id="cebea-361">Table</span><span class="sxs-lookup"><span data-stu-id="cebea-361">Table</span></span>|@Table|<span data-ttu-id="cebea-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-362">TABLE_NAME</span></span>|<span data-ttu-id="cebea-363">3</span><span class="sxs-lookup"><span data-stu-id="cebea-363">3</span></span>|  
|<span data-ttu-id="cebea-364">Column</span><span class="sxs-lookup"><span data-stu-id="cebea-364">Column</span></span>|@Column|<span data-ttu-id="cebea-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cebea-365">COLUMN_NAME</span></span>|<span data-ttu-id="cebea-366">4</span><span class="sxs-lookup"><span data-stu-id="cebea-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cebea-367">참고자료</span><span class="sxs-lookup"><span data-stu-id="cebea-367">See also</span></span>

- [<span data-ttu-id="cebea-368">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="cebea-368">ADO.NET Overview</span></span>](ado-net-overview.md)
