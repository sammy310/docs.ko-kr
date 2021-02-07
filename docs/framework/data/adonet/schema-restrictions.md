---
description: '자세한 정보: 스키마 제한 사항'
title: 스키마 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 74ddfe5b8aaf9b8193e0c0b2a929ccde333eac26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719047"
---
# <a name="schema-restrictions"></a><span data-ttu-id="d13c1-103">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="d13c1-103">Schema Restrictions</span></span>

<span data-ttu-id="d13c1-104">**GetSchema** 메서드의 두 번째 선택적 매개 변수는 반환되는 스키마 정보의 양을 제한하는 데 사용되는 제한이며, **GetSchema** 메서드에 문자열 배열로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-104">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d13c1-105">배열의 위치는 전달할 수 있는 값을 결정하며 이 위치는 제한 번호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-105">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d13c1-106">예를 들어 다음 표에는 .NET Framework Data Provider for SQL Server를 사용하는 "Table" 스키마 컬렉션에서 지원되는 제한에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-106">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d13c1-107">SQL Server 스키마 컬렉션의 추가 제한은 이 항목의 맨 마지막에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-107">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d13c1-108">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-108">Restriction Name</span></span>|<span data-ttu-id="d13c1-109">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-109">Parameter Name</span></span>|<span data-ttu-id="d13c1-110">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-110">Restriction Default</span></span>|<span data-ttu-id="d13c1-111">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-111">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-112">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-112">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-113">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-113">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-114">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-114">1</span></span>|  
|<span data-ttu-id="d13c1-115">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-115">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-116">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-116">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-117">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-117">2</span></span>|  
|<span data-ttu-id="d13c1-118">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-118">Table</span></span>|@Name|<span data-ttu-id="d13c1-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-119">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-120">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-120">3</span></span>|  
|<span data-ttu-id="d13c1-121">TableType</span><span class="sxs-lookup"><span data-stu-id="d13c1-121">TableType</span></span>|@TableType|<span data-ttu-id="d13c1-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d13c1-122">TABLE_TYPE</span></span>|<span data-ttu-id="d13c1-123">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-123">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d13c1-124">제한 값 지정</span><span class="sxs-lookup"><span data-stu-id="d13c1-124">Specifying Restriction Values</span></span>  

 <span data-ttu-id="d13c1-125">"Tables" 스키마 컬렉션의 제한 중 하나를 사용하려면 네 가지 요소로 된 문자열 배열을 만든 다음 제한 번호와 일치하는 요소에 값을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-125">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d13c1-126">예를 들어, **GetSchema** 메서드에서 “Sales” 스키마의 테이블만 반환하도록 제한하려면 **GetSchema** 메서드로 전달하기 전에 배열의 두 번째 요소를 “Sales”로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-126">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d13c1-127">`SqlClient` 및 `OracleClient`의 제한 컬렉션에는 하나의 추가 `ParameterName` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-127">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d13c1-128">제한 기본 열은 이전 버전과 여전히 호환되지만 현재는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-128">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d13c1-129">문자열 대체보다는 매개 변수가 있는 쿼리를 사용하여 제한 값을 지정할 때 SQL 삽입 공격 위험을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-129">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d13c1-130">배열의 요소 개수는 지정된 스키마 컬렉션에 대해 지원되는 제한 개수보다 작거나 같아야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-130">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d13c1-131">제한의 최대 개수보다 작을 수 있으며</span><span class="sxs-lookup"><span data-stu-id="d13c1-131">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d13c1-132">제한이 없으면 null(무제한)로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-132">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d13c1-133">.NET Framework 관리 공급자를 쿼리하여 제한 스키마 컬렉션의 이름 ("제한 사항")으로 **GetSchema** 메서드를 호출 하 여 지원 되는 제한 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-133">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d13c1-134">그러면 컬렉션 이름, 제한 이름, 기본 제한 값 및 제한 번호 목록과 함께 <xref:System.Data.DataTable>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-134">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d13c1-135">예제</span><span class="sxs-lookup"><span data-stu-id="d13c1-135">Example</span></span>  

 <span data-ttu-id="d13c1-136">다음 예에서는 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> SQL Server 클래스에 대해 .NET Framework Data Provider의 메서드를 사용 하 여 <xref:System.Data.SqlClient.SqlConnection> **AdventureWorks** 예제 데이터베이스에 포함 된 모든 테이블에 대 한 스키마 정보를 검색 하 고 "Sales" 스키마의 테이블만 반환 하는 정보를 제한 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-136">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d13c1-137">SQL Server 스키마 제한</span><span class="sxs-lookup"><span data-stu-id="d13c1-137">SQL Server Schema Restrictions</span></span>  

 <span data-ttu-id="d13c1-138">다음 표에는 SQL Server 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-138">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d13c1-139">사용자</span><span class="sxs-lookup"><span data-stu-id="d13c1-139">Users</span></span>  
  
|<span data-ttu-id="d13c1-140">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-140">Restriction Name</span></span>|<span data-ttu-id="d13c1-141">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-141">Parameter Name</span></span>|<span data-ttu-id="d13c1-142">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-142">Restriction Default</span></span>|<span data-ttu-id="d13c1-143">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-143">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-144">User_Name</span><span class="sxs-lookup"><span data-stu-id="d13c1-144">User_Name</span></span>|@Name|<span data-ttu-id="d13c1-145">name</span><span class="sxs-lookup"><span data-stu-id="d13c1-145">name</span></span>|<span data-ttu-id="d13c1-146">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-146">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d13c1-147">데이터베이스</span><span class="sxs-lookup"><span data-stu-id="d13c1-147">Databases</span></span>  
  
|<span data-ttu-id="d13c1-148">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-148">Restriction Name</span></span>|<span data-ttu-id="d13c1-149">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-149">Parameter Name</span></span>|<span data-ttu-id="d13c1-150">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-150">Restriction Default</span></span>|<span data-ttu-id="d13c1-151">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-151">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-152">속성</span><span class="sxs-lookup"><span data-stu-id="d13c1-152">Name</span></span>|@Name|<span data-ttu-id="d13c1-153">속성</span><span class="sxs-lookup"><span data-stu-id="d13c1-153">Name</span></span>|<span data-ttu-id="d13c1-154">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-154">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d13c1-155">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-155">Tables</span></span>  
  
|<span data-ttu-id="d13c1-156">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-156">Restriction Name</span></span>|<span data-ttu-id="d13c1-157">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-157">Parameter Name</span></span>|<span data-ttu-id="d13c1-158">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-158">Restriction Default</span></span>|<span data-ttu-id="d13c1-159">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-159">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-160">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-160">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-161">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-161">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-162">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-162">1</span></span>|  
|<span data-ttu-id="d13c1-163">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-163">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-164">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-164">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-165">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-165">2</span></span>|  
|<span data-ttu-id="d13c1-166">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-166">Table</span></span>|@Name|<span data-ttu-id="d13c1-167">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-167">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-168">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-168">3</span></span>|  
|<span data-ttu-id="d13c1-169">TableType</span><span class="sxs-lookup"><span data-stu-id="d13c1-169">TableType</span></span>|@TableType|<span data-ttu-id="d13c1-170">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d13c1-170">TABLE_TYPE</span></span>|<span data-ttu-id="d13c1-171">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-171">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d13c1-172">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-172">Columns</span></span>  
  
|<span data-ttu-id="d13c1-173">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-173">Restriction Name</span></span>|<span data-ttu-id="d13c1-174">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-174">Parameter Name</span></span>|<span data-ttu-id="d13c1-175">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-175">Restriction Default</span></span>|<span data-ttu-id="d13c1-176">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-176">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-177">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-177">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-178">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-178">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-179">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-179">1</span></span>|  
|<span data-ttu-id="d13c1-180">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-180">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-181">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-181">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-182">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-182">2</span></span>|  
|<span data-ttu-id="d13c1-183">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-183">Table</span></span>|@Table|<span data-ttu-id="d13c1-184">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-184">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-185">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-185">3</span></span>|  
|<span data-ttu-id="d13c1-186">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-186">Column</span></span>|@Column|<span data-ttu-id="d13c1-187">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-187">COLUMN_NAME</span></span>|<span data-ttu-id="d13c1-188">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-188">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d13c1-189">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d13c1-189">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d13c1-190">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-190">Restriction Name</span></span>|<span data-ttu-id="d13c1-191">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-191">Parameter Name</span></span>|<span data-ttu-id="d13c1-192">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-192">Restriction Default</span></span>|<span data-ttu-id="d13c1-193">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-193">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-194">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-194">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-195">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-195">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-196">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-196">1</span></span>|  
|<span data-ttu-id="d13c1-197">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-197">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-198">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-198">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-199">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-199">2</span></span>|  
|<span data-ttu-id="d13c1-200">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-200">Table</span></span>|@Table|<span data-ttu-id="d13c1-201">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-201">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-202">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-202">3</span></span>|  
|<span data-ttu-id="d13c1-203">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-203">Column</span></span>|@Column|<span data-ttu-id="d13c1-204">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-204">COLUMN_NAME</span></span>|<span data-ttu-id="d13c1-205">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-205">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d13c1-206">보기</span><span class="sxs-lookup"><span data-stu-id="d13c1-206">Views</span></span>  
  
|<span data-ttu-id="d13c1-207">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-207">Restriction Name</span></span>|<span data-ttu-id="d13c1-208">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-208">Parameter Name</span></span>|<span data-ttu-id="d13c1-209">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-209">Restriction Default</span></span>|<span data-ttu-id="d13c1-210">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-210">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-211">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-211">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-212">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-212">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-213">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-213">1</span></span>|  
|<span data-ttu-id="d13c1-214">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-214">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-215">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-215">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-216">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-216">2</span></span>|  
|<span data-ttu-id="d13c1-217">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-217">Table</span></span>|@Table|<span data-ttu-id="d13c1-218">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-218">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-219">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-219">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d13c1-220">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d13c1-220">ViewColumns</span></span>  
  
|<span data-ttu-id="d13c1-221">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-221">Restriction Name</span></span>|<span data-ttu-id="d13c1-222">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-222">Parameter Name</span></span>|<span data-ttu-id="d13c1-223">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-223">Restriction Default</span></span>|<span data-ttu-id="d13c1-224">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-224">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-225">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-225">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-226">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-226">VIEW_CATALOG</span></span>|<span data-ttu-id="d13c1-227">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-227">1</span></span>|  
|<span data-ttu-id="d13c1-228">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-228">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-229">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-229">VIEW_SCHEMA</span></span>|<span data-ttu-id="d13c1-230">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-230">2</span></span>|  
|<span data-ttu-id="d13c1-231">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-231">Table</span></span>|@Table|<span data-ttu-id="d13c1-232">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-232">VIEW_NAME</span></span>|<span data-ttu-id="d13c1-233">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-233">3</span></span>|  
|<span data-ttu-id="d13c1-234">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-234">Column</span></span>|@Column|<span data-ttu-id="d13c1-235">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-235">COLUMN_NAME</span></span>|<span data-ttu-id="d13c1-236">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-236">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d13c1-237">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d13c1-237">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d13c1-238">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-238">Restriction Name</span></span>|<span data-ttu-id="d13c1-239">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-239">Parameter Name</span></span>|<span data-ttu-id="d13c1-240">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-240">Restriction Default</span></span>|<span data-ttu-id="d13c1-241">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-241">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-242">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-242">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-243">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-243">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d13c1-244">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-244">1</span></span>|  
|<span data-ttu-id="d13c1-245">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-245">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-246">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-246">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d13c1-247">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-247">2</span></span>|  
|<span data-ttu-id="d13c1-248">속성</span><span class="sxs-lookup"><span data-stu-id="d13c1-248">Name</span></span>|@Name|<span data-ttu-id="d13c1-249">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-249">SPECIFIC_NAME</span></span>|<span data-ttu-id="d13c1-250">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-250">3</span></span>|  
|<span data-ttu-id="d13c1-251">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d13c1-251">Parameter</span></span>|@Parameter|<span data-ttu-id="d13c1-252">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-252">PARAMETER_NAME</span></span>|<span data-ttu-id="d13c1-253">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-253">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d13c1-254">프로시저</span><span class="sxs-lookup"><span data-stu-id="d13c1-254">Procedures</span></span>  
  
|<span data-ttu-id="d13c1-255">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-255">Restriction Name</span></span>|<span data-ttu-id="d13c1-256">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-256">Parameter Name</span></span>|<span data-ttu-id="d13c1-257">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-257">Restriction Default</span></span>|<span data-ttu-id="d13c1-258">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-258">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-259">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-259">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-260">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-260">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d13c1-261">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-261">1</span></span>|  
|<span data-ttu-id="d13c1-262">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-262">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-263">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-263">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d13c1-264">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-264">2</span></span>|  
|<span data-ttu-id="d13c1-265">속성</span><span class="sxs-lookup"><span data-stu-id="d13c1-265">Name</span></span>|@Name|<span data-ttu-id="d13c1-266">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-266">SPECIFIC_NAME</span></span>|<span data-ttu-id="d13c1-267">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-267">3</span></span>|  
|<span data-ttu-id="d13c1-268">형식</span><span class="sxs-lookup"><span data-stu-id="d13c1-268">Type</span></span>|@Type|<span data-ttu-id="d13c1-269">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d13c1-269">ROUTINE_TYPE</span></span>|<span data-ttu-id="d13c1-270">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-270">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d13c1-271">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d13c1-271">IndexColumns</span></span>  
  
|<span data-ttu-id="d13c1-272">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-272">Restriction Name</span></span>|<span data-ttu-id="d13c1-273">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-273">Parameter Name</span></span>|<span data-ttu-id="d13c1-274">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-274">Restriction Default</span></span>|<span data-ttu-id="d13c1-275">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-275">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-276">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-276">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-277">db_name()</span><span class="sxs-lookup"><span data-stu-id="d13c1-277">db_name()</span></span>|<span data-ttu-id="d13c1-278">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-278">1</span></span>|  
|<span data-ttu-id="d13c1-279">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-279">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-280">user_name()</span><span class="sxs-lookup"><span data-stu-id="d13c1-280">user_name()</span></span>|<span data-ttu-id="d13c1-281">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-281">2</span></span>|  
|<span data-ttu-id="d13c1-282">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-282">Table</span></span>|@Table|<span data-ttu-id="d13c1-283">o.name</span><span class="sxs-lookup"><span data-stu-id="d13c1-283">o.name</span></span>|<span data-ttu-id="d13c1-284">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-284">3</span></span>|  
|<span data-ttu-id="d13c1-285">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d13c1-285">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d13c1-286">x.name</span><span class="sxs-lookup"><span data-stu-id="d13c1-286">x.name</span></span>|<span data-ttu-id="d13c1-287">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-287">4</span></span>|  
|<span data-ttu-id="d13c1-288">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-288">Column</span></span>|@Column|<span data-ttu-id="d13c1-289">c.name</span><span class="sxs-lookup"><span data-stu-id="d13c1-289">c.name</span></span>|<span data-ttu-id="d13c1-290">5</span><span class="sxs-lookup"><span data-stu-id="d13c1-290">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d13c1-291">인덱스</span><span class="sxs-lookup"><span data-stu-id="d13c1-291">Indexes</span></span>  
  
|<span data-ttu-id="d13c1-292">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-292">Restriction Name</span></span>|<span data-ttu-id="d13c1-293">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-293">Parameter Name</span></span>|<span data-ttu-id="d13c1-294">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-294">Restriction Default</span></span>|<span data-ttu-id="d13c1-295">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-295">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-296">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-296">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-297">db_name()</span><span class="sxs-lookup"><span data-stu-id="d13c1-297">db_name()</span></span>|<span data-ttu-id="d13c1-298">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-298">1</span></span>|  
|<span data-ttu-id="d13c1-299">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-299">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-300">user_name()</span><span class="sxs-lookup"><span data-stu-id="d13c1-300">user_name()</span></span>|<span data-ttu-id="d13c1-301">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-301">2</span></span>|  
|<span data-ttu-id="d13c1-302">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-302">Table</span></span>|@Table|<span data-ttu-id="d13c1-303">o.name</span><span class="sxs-lookup"><span data-stu-id="d13c1-303">o.name</span></span>|<span data-ttu-id="d13c1-304">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-304">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d13c1-305">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d13c1-305">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d13c1-306">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-306">Restriction Name</span></span>|<span data-ttu-id="d13c1-307">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-307">Parameter Name</span></span>|<span data-ttu-id="d13c1-308">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-308">Restriction Default</span></span>|<span data-ttu-id="d13c1-309">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-309">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-310">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d13c1-310">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d13c1-311">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d13c1-311">assemblies.name</span></span>|<span data-ttu-id="d13c1-312">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-312">1</span></span>|  
|<span data-ttu-id="d13c1-313">udt_name</span><span class="sxs-lookup"><span data-stu-id="d13c1-313">udt_name</span></span>|@UDTName|<span data-ttu-id="d13c1-314">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d13c1-314">types.assembly_class</span></span>|<span data-ttu-id="d13c1-315">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-315">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d13c1-316">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d13c1-316">ForeignKeys</span></span>  
  
|<span data-ttu-id="d13c1-317">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-317">Restriction Name</span></span>|<span data-ttu-id="d13c1-318">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-318">Parameter Name</span></span>|<span data-ttu-id="d13c1-319">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-319">Restriction Default</span></span>|<span data-ttu-id="d13c1-320">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-320">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-321">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-321">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-322">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-322">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d13c1-323">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-323">1</span></span>|  
|<span data-ttu-id="d13c1-324">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-324">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-325">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-325">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d13c1-326">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-326">2</span></span>|  
|<span data-ttu-id="d13c1-327">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-327">Table</span></span>|@Table|<span data-ttu-id="d13c1-328">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-328">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-329">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-329">3</span></span>|  
|<span data-ttu-id="d13c1-330">속성</span><span class="sxs-lookup"><span data-stu-id="d13c1-330">Name</span></span>|@Name|<span data-ttu-id="d13c1-331">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-331">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d13c1-332">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-332">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d13c1-333">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d13c1-333">SQL Server 2008 Schema Restrictions</span></span>  

 <span data-ttu-id="d13c1-334">다음 표에는 SQL Server 2008 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-334">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d13c1-335">이러한 제한은 .NET Framework 버전 3.5 SP1 및 SQL Server 2008 이상에서 유효하며</span><span class="sxs-lookup"><span data-stu-id="d13c1-335">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d13c1-336">이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d13c1-336">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d13c1-337">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d13c1-337">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d13c1-338">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-338">Restriction Name</span></span>|<span data-ttu-id="d13c1-339">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-339">Parameter Name</span></span>|<span data-ttu-id="d13c1-340">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-340">Restriction Default</span></span>|<span data-ttu-id="d13c1-341">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-341">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-342">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-342">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-343">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-343">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-344">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-344">1</span></span>|  
|<span data-ttu-id="d13c1-345">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-345">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-346">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-346">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-347">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-347">2</span></span>|  
|<span data-ttu-id="d13c1-348">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-348">Table</span></span>|@Table|<span data-ttu-id="d13c1-349">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-349">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-350">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-350">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d13c1-351">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d13c1-351">AllColumns</span></span>  
  
|<span data-ttu-id="d13c1-352">제한 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-352">Restriction Name</span></span>|<span data-ttu-id="d13c1-353">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="d13c1-353">Parameter Name</span></span>|<span data-ttu-id="d13c1-354">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="d13c1-354">Restriction Default</span></span>|<span data-ttu-id="d13c1-355">제한 번호</span><span class="sxs-lookup"><span data-stu-id="d13c1-355">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d13c1-356">카탈로그</span><span class="sxs-lookup"><span data-stu-id="d13c1-356">Catalog</span></span>|@Catalog|<span data-ttu-id="d13c1-357">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d13c1-357">TABLE_CATALOG</span></span>|<span data-ttu-id="d13c1-358">1</span><span class="sxs-lookup"><span data-stu-id="d13c1-358">1</span></span>|  
|<span data-ttu-id="d13c1-359">소유자</span><span class="sxs-lookup"><span data-stu-id="d13c1-359">Owner</span></span>|@Owner|<span data-ttu-id="d13c1-360">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d13c1-360">TABLE_SCHEMA</span></span>|<span data-ttu-id="d13c1-361">2</span><span class="sxs-lookup"><span data-stu-id="d13c1-361">2</span></span>|  
|<span data-ttu-id="d13c1-362">테이블</span><span class="sxs-lookup"><span data-stu-id="d13c1-362">Table</span></span>|@Table|<span data-ttu-id="d13c1-363">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-363">TABLE_NAME</span></span>|<span data-ttu-id="d13c1-364">3</span><span class="sxs-lookup"><span data-stu-id="d13c1-364">3</span></span>|  
|<span data-ttu-id="d13c1-365">열</span><span class="sxs-lookup"><span data-stu-id="d13c1-365">Column</span></span>|@Column|<span data-ttu-id="d13c1-366">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d13c1-366">COLUMN_NAME</span></span>|<span data-ttu-id="d13c1-367">4</span><span class="sxs-lookup"><span data-stu-id="d13c1-367">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d13c1-368">참조</span><span class="sxs-lookup"><span data-stu-id="d13c1-368">See also</span></span>

- [<span data-ttu-id="d13c1-369">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d13c1-369">ADO.NET Overview</span></span>](ado-net-overview.md)
