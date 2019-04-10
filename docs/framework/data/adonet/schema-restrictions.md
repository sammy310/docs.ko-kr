---
title: 스키마 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: b5044d39d1dc5d2fa7d2ce691cdda7075fa0e32a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151205"
---
# <a name="schema-restrictions"></a><span data-ttu-id="39805-102">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="39805-102">Schema Restrictions</span></span>
<span data-ttu-id="39805-103">두 번째 선택적 매개 변수를 **GetSchema** 메서드는 스키마 정보의 양을 제한 하는 데 사용 되는 제한을 반환 되 고 전달 되는 **GetSchema** 문자열의 배열로 메서드 .</span><span class="sxs-lookup"><span data-stu-id="39805-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="39805-104">배열의 위치는 전달할 수 있는 값을 결정하며 이 위치는 제한 번호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="39805-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="39805-105">예를 들어 다음 표에는 .NET Framework Data Provider for SQL Server를 사용하는 "Table" 스키마 컬렉션에서 지원되는 제한에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="39805-106">SQL Server 스키마 컬렉션의 추가 제한은 이 항목의 맨 마지막에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="39805-107">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-107">Restriction Name</span></span>|<span data-ttu-id="39805-108">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-108">Parameter Name</span></span>|<span data-ttu-id="39805-109">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-109">Restriction Default</span></span>|<span data-ttu-id="39805-110">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-111">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-112">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-113">1</span><span class="sxs-lookup"><span data-stu-id="39805-113">1</span></span>|  
|<span data-ttu-id="39805-114">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-114">Owner</span></span>|@Owner|<span data-ttu-id="39805-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-116">2</span><span class="sxs-lookup"><span data-stu-id="39805-116">2</span></span>|  
|<span data-ttu-id="39805-117">표</span><span class="sxs-lookup"><span data-stu-id="39805-117">Table</span></span>|@Name|<span data-ttu-id="39805-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-118">TABLE_NAME</span></span>|<span data-ttu-id="39805-119">3</span><span class="sxs-lookup"><span data-stu-id="39805-119">3</span></span>|  
|<span data-ttu-id="39805-120">TableType</span><span class="sxs-lookup"><span data-stu-id="39805-120">TableType</span></span>|@TableType|<span data-ttu-id="39805-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39805-121">TABLE_TYPE</span></span>|<span data-ttu-id="39805-122">4</span><span class="sxs-lookup"><span data-stu-id="39805-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="39805-123">제한 값 지정</span><span class="sxs-lookup"><span data-stu-id="39805-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="39805-124">"Tables" 스키마 컬렉션의 제한 중 하나를 사용하려면 네 가지 요소로 된 문자열 배열을 만든 다음 제한 번호와 일치하는 요소에 값을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39805-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="39805-125">예를 들어, 테이블을 제한 하 여 반환 합니다 **GetSchema** 전달 하기 전에 "Sales" 배열의 두 번째 요소를 설정 하는 방법 "Sales" 스키마의 테이블만 합니다 **GetSchema** 메서드.</span><span class="sxs-lookup"><span data-stu-id="39805-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39805-126">`SqlClient` 및 `OracleClient`의 제한 컬렉션에는 하나의 추가 `ParameterName` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="39805-127">제한 기본 열은 이전 버전과 여전히 호환되지만 현재는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39805-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="39805-128">문자열 대체보다는 매개 변수가 있는 쿼리를 사용하여 제한 값을 지정할 때 SQL 삽입 공격 위험을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39805-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39805-129">배열의 요소 개수는 지정된 스키마 컬렉션에 대해 지원되는 제한 개수보다 작거나 같아야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="39805-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="39805-130">제한의 최대 개수보다 작을 수 있으며</span><span class="sxs-lookup"><span data-stu-id="39805-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="39805-131">제한이 없으면 null(무제한)로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="39805-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="39805-132">호출 하 여 지원 되는 제한 사항 목록을 확인 하려면.NET Framework 관리 공급자를 쿼리할 수 있습니다 합니다 **GetSchema** 메서드는 "제한" 하는 제한 스키마 컬렉션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39805-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="39805-133">그러면 컬렉션 이름, 제한 이름, 기본 제한 값 및 제한 번호 목록과 함께 <xref:System.Data.DataTable>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="39805-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="39805-134">예제</span><span class="sxs-lookup"><span data-stu-id="39805-134">Example</span></span>  
 <span data-ttu-id="39805-135">다음 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> .NET Framework Data Provider for SQL Server 메서드의 <xref:System.Data.SqlClient.SqlConnection> 모든 포함 된 테이블에 대 한 스키마 정보를 검색 하는 클래스는 **AdventureWorks**예제 데이터베이스 및 정보를 제한 하는 "Sales" 스키마의 테이블만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39805-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="39805-136">SQL Server 스키마 제한</span><span class="sxs-lookup"><span data-stu-id="39805-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="39805-137">다음 표에는 SQL Server 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="39805-138">Users</span><span class="sxs-lookup"><span data-stu-id="39805-138">Users</span></span>  
  
|<span data-ttu-id="39805-139">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-139">Restriction Name</span></span>|<span data-ttu-id="39805-140">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-140">Parameter Name</span></span>|<span data-ttu-id="39805-141">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-141">Restriction Default</span></span>|<span data-ttu-id="39805-142">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="39805-143">User_Name</span></span>|@Name|<span data-ttu-id="39805-144">name</span><span class="sxs-lookup"><span data-stu-id="39805-144">name</span></span>|<span data-ttu-id="39805-145">1</span><span class="sxs-lookup"><span data-stu-id="39805-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="39805-146">Databases</span><span class="sxs-lookup"><span data-stu-id="39805-146">Databases</span></span>  
  
|<span data-ttu-id="39805-147">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-147">Restriction Name</span></span>|<span data-ttu-id="39805-148">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-148">Parameter Name</span></span>|<span data-ttu-id="39805-149">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-149">Restriction Default</span></span>|<span data-ttu-id="39805-150">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-151">이름</span><span class="sxs-lookup"><span data-stu-id="39805-151">Name</span></span>|@Name|<span data-ttu-id="39805-152">이름</span><span class="sxs-lookup"><span data-stu-id="39805-152">Name</span></span>|<span data-ttu-id="39805-153">1</span><span class="sxs-lookup"><span data-stu-id="39805-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="39805-154">Tables</span><span class="sxs-lookup"><span data-stu-id="39805-154">Tables</span></span>  
  
|<span data-ttu-id="39805-155">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-155">Restriction Name</span></span>|<span data-ttu-id="39805-156">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-156">Parameter Name</span></span>|<span data-ttu-id="39805-157">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-157">Restriction Default</span></span>|<span data-ttu-id="39805-158">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-159">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-160">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-161">1</span><span class="sxs-lookup"><span data-stu-id="39805-161">1</span></span>|  
|<span data-ttu-id="39805-162">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-162">Owner</span></span>|@Owner|<span data-ttu-id="39805-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-164">2</span><span class="sxs-lookup"><span data-stu-id="39805-164">2</span></span>|  
|<span data-ttu-id="39805-165">표</span><span class="sxs-lookup"><span data-stu-id="39805-165">Table</span></span>|@Name|<span data-ttu-id="39805-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-166">TABLE_NAME</span></span>|<span data-ttu-id="39805-167">3</span><span class="sxs-lookup"><span data-stu-id="39805-167">3</span></span>|  
|<span data-ttu-id="39805-168">TableType</span><span class="sxs-lookup"><span data-stu-id="39805-168">TableType</span></span>|@TableType|<span data-ttu-id="39805-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39805-169">TABLE_TYPE</span></span>|<span data-ttu-id="39805-170">4</span><span class="sxs-lookup"><span data-stu-id="39805-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="39805-171">Columns</span><span class="sxs-lookup"><span data-stu-id="39805-171">Columns</span></span>  
  
|<span data-ttu-id="39805-172">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-172">Restriction Name</span></span>|<span data-ttu-id="39805-173">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-173">Parameter Name</span></span>|<span data-ttu-id="39805-174">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-174">Restriction Default</span></span>|<span data-ttu-id="39805-175">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-176">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-177">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-178">1</span><span class="sxs-lookup"><span data-stu-id="39805-178">1</span></span>|  
|<span data-ttu-id="39805-179">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-179">Owner</span></span>|@Owner|<span data-ttu-id="39805-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-181">2</span><span class="sxs-lookup"><span data-stu-id="39805-181">2</span></span>|  
|<span data-ttu-id="39805-182">표</span><span class="sxs-lookup"><span data-stu-id="39805-182">Table</span></span>|@Table|<span data-ttu-id="39805-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-183">TABLE_NAME</span></span>|<span data-ttu-id="39805-184">3</span><span class="sxs-lookup"><span data-stu-id="39805-184">3</span></span>|  
|<span data-ttu-id="39805-185">Column</span><span class="sxs-lookup"><span data-stu-id="39805-185">Column</span></span>|@Column|<span data-ttu-id="39805-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-186">COLUMN_NAME</span></span>|<span data-ttu-id="39805-187">4</span><span class="sxs-lookup"><span data-stu-id="39805-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="39805-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="39805-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="39805-189">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-189">Restriction Name</span></span>|<span data-ttu-id="39805-190">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-190">Parameter Name</span></span>|<span data-ttu-id="39805-191">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-191">Restriction Default</span></span>|<span data-ttu-id="39805-192">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-193">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-194">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-195">1</span><span class="sxs-lookup"><span data-stu-id="39805-195">1</span></span>|  
|<span data-ttu-id="39805-196">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-196">Owner</span></span>|@Owner|<span data-ttu-id="39805-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-198">2</span><span class="sxs-lookup"><span data-stu-id="39805-198">2</span></span>|  
|<span data-ttu-id="39805-199">표</span><span class="sxs-lookup"><span data-stu-id="39805-199">Table</span></span>|@Table|<span data-ttu-id="39805-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-200">TABLE_NAME</span></span>|<span data-ttu-id="39805-201">3</span><span class="sxs-lookup"><span data-stu-id="39805-201">3</span></span>|  
|<span data-ttu-id="39805-202">Column</span><span class="sxs-lookup"><span data-stu-id="39805-202">Column</span></span>|@Column|<span data-ttu-id="39805-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-203">COLUMN_NAME</span></span>|<span data-ttu-id="39805-204">4</span><span class="sxs-lookup"><span data-stu-id="39805-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="39805-205">보기</span><span class="sxs-lookup"><span data-stu-id="39805-205">Views</span></span>  
  
|<span data-ttu-id="39805-206">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-206">Restriction Name</span></span>|<span data-ttu-id="39805-207">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-207">Parameter Name</span></span>|<span data-ttu-id="39805-208">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-208">Restriction Default</span></span>|<span data-ttu-id="39805-209">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-210">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-211">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-212">1</span><span class="sxs-lookup"><span data-stu-id="39805-212">1</span></span>|  
|<span data-ttu-id="39805-213">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-213">Owner</span></span>|@Owner|<span data-ttu-id="39805-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-215">2</span><span class="sxs-lookup"><span data-stu-id="39805-215">2</span></span>|  
|<span data-ttu-id="39805-216">표</span><span class="sxs-lookup"><span data-stu-id="39805-216">Table</span></span>|@Table|<span data-ttu-id="39805-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-217">TABLE_NAME</span></span>|<span data-ttu-id="39805-218">3</span><span class="sxs-lookup"><span data-stu-id="39805-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="39805-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="39805-219">ViewColumns</span></span>  
  
|<span data-ttu-id="39805-220">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-220">Restriction Name</span></span>|<span data-ttu-id="39805-221">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-221">Parameter Name</span></span>|<span data-ttu-id="39805-222">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-222">Restriction Default</span></span>|<span data-ttu-id="39805-223">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-224">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-225">VIEW_CATALOG</span></span>|<span data-ttu-id="39805-226">1</span><span class="sxs-lookup"><span data-stu-id="39805-226">1</span></span>|  
|<span data-ttu-id="39805-227">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-227">Owner</span></span>|@Owner|<span data-ttu-id="39805-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="39805-229">2</span><span class="sxs-lookup"><span data-stu-id="39805-229">2</span></span>|  
|<span data-ttu-id="39805-230">표</span><span class="sxs-lookup"><span data-stu-id="39805-230">Table</span></span>|@Table|<span data-ttu-id="39805-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-231">VIEW_NAME</span></span>|<span data-ttu-id="39805-232">3</span><span class="sxs-lookup"><span data-stu-id="39805-232">3</span></span>|  
|<span data-ttu-id="39805-233">Column</span><span class="sxs-lookup"><span data-stu-id="39805-233">Column</span></span>|@Column|<span data-ttu-id="39805-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-234">COLUMN_NAME</span></span>|<span data-ttu-id="39805-235">4</span><span class="sxs-lookup"><span data-stu-id="39805-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="39805-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39805-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="39805-237">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-237">Restriction Name</span></span>|<span data-ttu-id="39805-238">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-238">Parameter Name</span></span>|<span data-ttu-id="39805-239">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-239">Restriction Default</span></span>|<span data-ttu-id="39805-240">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-241">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="39805-243">1</span><span class="sxs-lookup"><span data-stu-id="39805-243">1</span></span>|  
|<span data-ttu-id="39805-244">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-244">Owner</span></span>|@Owner|<span data-ttu-id="39805-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="39805-246">2</span><span class="sxs-lookup"><span data-stu-id="39805-246">2</span></span>|  
|<span data-ttu-id="39805-247">이름</span><span class="sxs-lookup"><span data-stu-id="39805-247">Name</span></span>|@Name|<span data-ttu-id="39805-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="39805-249">3</span><span class="sxs-lookup"><span data-stu-id="39805-249">3</span></span>|  
|<span data-ttu-id="39805-250">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39805-250">Parameter</span></span>|@Parameter|<span data-ttu-id="39805-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-251">PARAMETER_NAME</span></span>|<span data-ttu-id="39805-252">4</span><span class="sxs-lookup"><span data-stu-id="39805-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="39805-253">절차</span><span class="sxs-lookup"><span data-stu-id="39805-253">Procedures</span></span>  
  
|<span data-ttu-id="39805-254">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-254">Restriction Name</span></span>|<span data-ttu-id="39805-255">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-255">Parameter Name</span></span>|<span data-ttu-id="39805-256">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-256">Restriction Default</span></span>|<span data-ttu-id="39805-257">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-258">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="39805-260">1</span><span class="sxs-lookup"><span data-stu-id="39805-260">1</span></span>|  
|<span data-ttu-id="39805-261">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-261">Owner</span></span>|@Owner|<span data-ttu-id="39805-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="39805-263">2</span><span class="sxs-lookup"><span data-stu-id="39805-263">2</span></span>|  
|<span data-ttu-id="39805-264">이름</span><span class="sxs-lookup"><span data-stu-id="39805-264">Name</span></span>|@Name|<span data-ttu-id="39805-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="39805-266">3</span><span class="sxs-lookup"><span data-stu-id="39805-266">3</span></span>|  
|<span data-ttu-id="39805-267">형식</span><span class="sxs-lookup"><span data-stu-id="39805-267">Type</span></span>|@Type|<span data-ttu-id="39805-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39805-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="39805-269">4</span><span class="sxs-lookup"><span data-stu-id="39805-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="39805-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="39805-270">IndexColumns</span></span>  
  
|<span data-ttu-id="39805-271">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-271">Restriction Name</span></span>|<span data-ttu-id="39805-272">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-272">Parameter Name</span></span>|<span data-ttu-id="39805-273">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-273">Restriction Default</span></span>|<span data-ttu-id="39805-274">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-275">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="39805-276">db_name()</span></span>|<span data-ttu-id="39805-277">1</span><span class="sxs-lookup"><span data-stu-id="39805-277">1</span></span>|  
|<span data-ttu-id="39805-278">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-278">Owner</span></span>|@Owner|<span data-ttu-id="39805-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="39805-279">user_name()</span></span>|<span data-ttu-id="39805-280">2</span><span class="sxs-lookup"><span data-stu-id="39805-280">2</span></span>|  
|<span data-ttu-id="39805-281">표</span><span class="sxs-lookup"><span data-stu-id="39805-281">Table</span></span>|@Table|<span data-ttu-id="39805-282">o.name</span><span class="sxs-lookup"><span data-stu-id="39805-282">o.name</span></span>|<span data-ttu-id="39805-283">3</span><span class="sxs-lookup"><span data-stu-id="39805-283">3</span></span>|  
|<span data-ttu-id="39805-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="39805-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="39805-285">x.name</span><span class="sxs-lookup"><span data-stu-id="39805-285">x.name</span></span>|<span data-ttu-id="39805-286">4</span><span class="sxs-lookup"><span data-stu-id="39805-286">4</span></span>|  
|<span data-ttu-id="39805-287">Column</span><span class="sxs-lookup"><span data-stu-id="39805-287">Column</span></span>|@Column|<span data-ttu-id="39805-288">c.name</span><span class="sxs-lookup"><span data-stu-id="39805-288">c.name</span></span>|<span data-ttu-id="39805-289">5</span><span class="sxs-lookup"><span data-stu-id="39805-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="39805-290">인덱스</span><span class="sxs-lookup"><span data-stu-id="39805-290">Indexes</span></span>  
  
|<span data-ttu-id="39805-291">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-291">Restriction Name</span></span>|<span data-ttu-id="39805-292">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-292">Parameter Name</span></span>|<span data-ttu-id="39805-293">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-293">Restriction Default</span></span>|<span data-ttu-id="39805-294">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-295">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="39805-296">db_name()</span></span>|<span data-ttu-id="39805-297">1</span><span class="sxs-lookup"><span data-stu-id="39805-297">1</span></span>|  
|<span data-ttu-id="39805-298">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-298">Owner</span></span>|@Owner|<span data-ttu-id="39805-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="39805-299">user_name()</span></span>|<span data-ttu-id="39805-300">2</span><span class="sxs-lookup"><span data-stu-id="39805-300">2</span></span>|  
|<span data-ttu-id="39805-301">표</span><span class="sxs-lookup"><span data-stu-id="39805-301">Table</span></span>|@Table|<span data-ttu-id="39805-302">o.name</span><span class="sxs-lookup"><span data-stu-id="39805-302">o.name</span></span>|<span data-ttu-id="39805-303">3</span><span class="sxs-lookup"><span data-stu-id="39805-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="39805-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="39805-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="39805-305">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-305">Restriction Name</span></span>|<span data-ttu-id="39805-306">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-306">Parameter Name</span></span>|<span data-ttu-id="39805-307">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-307">Restriction Default</span></span>|<span data-ttu-id="39805-308">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="39805-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="39805-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="39805-310">assemblies.name</span></span>|<span data-ttu-id="39805-311">1</span><span class="sxs-lookup"><span data-stu-id="39805-311">1</span></span>|  
|<span data-ttu-id="39805-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="39805-312">udt_name</span></span>|@UDTName|<span data-ttu-id="39805-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="39805-313">types.assembly_class</span></span>|<span data-ttu-id="39805-314">2</span><span class="sxs-lookup"><span data-stu-id="39805-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="39805-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="39805-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="39805-316">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-316">Restriction Name</span></span>|<span data-ttu-id="39805-317">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-317">Parameter Name</span></span>|<span data-ttu-id="39805-318">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-318">Restriction Default</span></span>|<span data-ttu-id="39805-319">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-320">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="39805-322">1</span><span class="sxs-lookup"><span data-stu-id="39805-322">1</span></span>|  
|<span data-ttu-id="39805-323">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-323">Owner</span></span>|@Owner|<span data-ttu-id="39805-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="39805-325">2</span><span class="sxs-lookup"><span data-stu-id="39805-325">2</span></span>|  
|<span data-ttu-id="39805-326">표</span><span class="sxs-lookup"><span data-stu-id="39805-326">Table</span></span>|@Table|<span data-ttu-id="39805-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-327">TABLE_NAME</span></span>|<span data-ttu-id="39805-328">3</span><span class="sxs-lookup"><span data-stu-id="39805-328">3</span></span>|  
|<span data-ttu-id="39805-329">이름</span><span class="sxs-lookup"><span data-stu-id="39805-329">Name</span></span>|@Name|<span data-ttu-id="39805-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="39805-331">4</span><span class="sxs-lookup"><span data-stu-id="39805-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="39805-332">SQL Server 2008       </span><span class="sxs-lookup"><span data-stu-id="39805-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="39805-333">다음 표에는 SQL Server 2008 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="39805-334">이러한 제한은 .NET Framework 버전 3.5 SP1 및 SQL Server 2008 이상에서 유효하며</span><span class="sxs-lookup"><span data-stu-id="39805-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="39805-335">이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39805-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="39805-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="39805-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="39805-337">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-337">Restriction Name</span></span>|<span data-ttu-id="39805-338">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-338">Parameter Name</span></span>|<span data-ttu-id="39805-339">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-339">Restriction Default</span></span>|<span data-ttu-id="39805-340">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-341">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-342">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-343">1</span><span class="sxs-lookup"><span data-stu-id="39805-343">1</span></span>|  
|<span data-ttu-id="39805-344">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-344">Owner</span></span>|@Owner|<span data-ttu-id="39805-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-346">2</span><span class="sxs-lookup"><span data-stu-id="39805-346">2</span></span>|  
|<span data-ttu-id="39805-347">표</span><span class="sxs-lookup"><span data-stu-id="39805-347">Table</span></span>|@Table|<span data-ttu-id="39805-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-348">TABLE_NAME</span></span>|<span data-ttu-id="39805-349">3</span><span class="sxs-lookup"><span data-stu-id="39805-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="39805-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="39805-350">AllColumns</span></span>  
  
|<span data-ttu-id="39805-351">제한 이름</span><span class="sxs-lookup"><span data-stu-id="39805-351">Restriction Name</span></span>|<span data-ttu-id="39805-352">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="39805-352">Parameter Name</span></span>|<span data-ttu-id="39805-353">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="39805-353">Restriction Default</span></span>|<span data-ttu-id="39805-354">제한 번호</span><span class="sxs-lookup"><span data-stu-id="39805-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="39805-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="39805-355">Catalog</span></span>|@Catalog|<span data-ttu-id="39805-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39805-356">TABLE_CATALOG</span></span>|<span data-ttu-id="39805-357">1</span><span class="sxs-lookup"><span data-stu-id="39805-357">1</span></span>|  
|<span data-ttu-id="39805-358">Owner</span><span class="sxs-lookup"><span data-stu-id="39805-358">Owner</span></span>|@Owner|<span data-ttu-id="39805-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39805-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="39805-360">2</span><span class="sxs-lookup"><span data-stu-id="39805-360">2</span></span>|  
|<span data-ttu-id="39805-361">표</span><span class="sxs-lookup"><span data-stu-id="39805-361">Table</span></span>|@Table|<span data-ttu-id="39805-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-362">TABLE_NAME</span></span>|<span data-ttu-id="39805-363">3</span><span class="sxs-lookup"><span data-stu-id="39805-363">3</span></span>|  
|<span data-ttu-id="39805-364">Column</span><span class="sxs-lookup"><span data-stu-id="39805-364">Column</span></span>|@Column|<span data-ttu-id="39805-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39805-365">COLUMN_NAME</span></span>|<span data-ttu-id="39805-366">4</span><span class="sxs-lookup"><span data-stu-id="39805-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39805-367">참고자료</span><span class="sxs-lookup"><span data-stu-id="39805-367">See also</span></span>

- [<span data-ttu-id="39805-368">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="39805-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
