---
title: GetSchema 및 Schema 컬렉션
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 11cfad81e40e76691db9f99efd1d60f5528600d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230176"
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="99fb2-102">GetSchema 및 Schema 컬렉션</span><span class="sxs-lookup"><span data-stu-id="99fb2-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="99fb2-103">합니다 **연결** .NET Framework 관리 공급자 구현 하는 각 클래스는 **GetSchema** 현재 연결 되어 있는 데이터베이스에 대 한 스키마 정보를 검색 하는 데 사용 되는 메서드 및 반환 된 스키마 정보를 **GetSchema** 형태로 제공 되는 메서드를 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="99fb2-104">합니다 **GetSchema** 메서드는 스키마 컬렉션이 반환 되도록 지정 하 고 반환 되는 정보의 양을 제한에 대 한 선택적 매개 변수를 제공 하는 오버 로드 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="99fb2-105">스키마 컬렉션 지정</span><span class="sxs-lookup"><span data-stu-id="99fb2-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="99fb2-106">첫 번째 선택적 매개 변수를 **GetSchema** 메서드를 문자열로 지정 된 컬렉션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="99fb2-107">스키마 컬렉션에는 모든 공급자에 공통되는 공통 스키마 컬렉션과 공급자마다 다른 특정 스키마 컬렉션의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="99fb2-108">호출 하 여 지원 되는 스키마 컬렉션 목록을 확인 하려면.NET Framework 관리 공급자를 쿼리할 수 있습니다 합니다 **GetSchema** 메서드 인수 없이 또는 "metadatacollections 라는" 스키마 컬렉션 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="99fb2-109">그러면 지원되는 스키마 컬렉션의 목록, 각자 지원하는 제약 조건 수 및 사용하는 식별자 부분 수가 포함된 <xref:System.Data.DataTable>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fb2-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="99fb2-110">스키마 컬렉션 검색 예제</span><span class="sxs-lookup"><span data-stu-id="99fb2-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="99fb2-111">다음 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> .NET Framework Data Provider for SQL Server 메서드의 <xref:System.Data.SqlClient.SqlConnection> 모든 포함 된 테이블에 대 한 스키마 정보를 검색 하는 클래스는 **AdventureWorks**예제 데이터베이스:</span><span class="sxs-lookup"><span data-stu-id="99fb2-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
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
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
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
  
## <a name="see-also"></a><span data-ttu-id="99fb2-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="99fb2-112">See also</span></span>

- [<span data-ttu-id="99fb2-113">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="99fb2-113">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="99fb2-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="99fb2-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
