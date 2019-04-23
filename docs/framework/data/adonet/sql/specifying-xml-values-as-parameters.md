---
title: XML 값을 매개 변수로 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2c4d08b8-fc29-4614-97fa-29c8ff7ca5b3
ms.openlocfilehash: 4551e8f193ffc9799b57a660f05add888b330484
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159252"
---
# <a name="specifying-xml-values-as-parameters"></a><span data-ttu-id="20a60-102">XML 값을 매개 변수로 지정</span><span class="sxs-lookup"><span data-stu-id="20a60-102">Specifying XML Values as Parameters</span></span>
<span data-ttu-id="20a60-103">쿼리 매개 변수 값으로 가지는 XML 문자열에 필요한 경우 개발자의 인스턴스를 사용 하 여 해당 값을 제공할 수는 **SqlXml** 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-103">If a query requires a parameter whose value is an XML string, developers can supply that value using an instance of the **SqlXml** data type.</span></span> <span data-ttu-id="20a60-104">실제로 가지 기법이; 다른 데이터 형식으로 동일한 방식으로 매개 변수 값을 허용 하는 SQL Server의 XML 열입니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-104">There really are no tricks; XML columns in SQL Server accept parameter values in exactly the same way as other data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20a60-105">예제</span><span class="sxs-lookup"><span data-stu-id="20a60-105">Example</span></span>  
 <span data-ttu-id="20a60-106">다음 콘솔 응용 프로그램에서 새 테이블을 만듭니다는 **AdventureWorks** 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-106">The following console application creates a new table in the **AdventureWorks** database.</span></span> <span data-ttu-id="20a60-107">새 테이블 열이 포함 **SalesID** 및 명명 된 XML 열 **SalesInfo**합니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-107">The new table includes a column named **SalesID** and an XML column named **SalesInfo**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20a60-108">합니다 **AdventureWorks** SQL Server를 설치할 때 기본적으로 예제 데이터베이스 설치 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-108">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="20a60-109">SQL Server 설치 프로그램을 실행하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-109">You can install it by running SQL Server Setup.</span></span>  
  
 <span data-ttu-id="20a60-110">이 예제에서는 <xref:System.Data.SqlClient.SqlCommand> 개체를 통해 새 테이블에 행을 삽입하도록 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-110">The example prepares a <xref:System.Data.SqlClient.SqlCommand> object to insert a row in the new table.</span></span> <span data-ttu-id="20a60-111">저장된 된 파일에 대 한 필요한 XML 데이터를 제공 합니다 **SalesInfo** 열입니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-111">A saved file provides the XML data needed for the **SalesInfo** column.</span></span>  
  
 <span data-ttu-id="20a60-112">예제를 실행시키는 데 필요한 파일을 만들려면 프로젝트와 동일한 폴더에 새 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-112">To create the file needed for the example to run, create a new text file in the same folder as your project.</span></span> <span data-ttu-id="20a60-113">파일의 이름을 MyTestStoreData.xml로 지정하고</span><span class="sxs-lookup"><span data-stu-id="20a60-113">Name the file MyTestStoreData.xml.</span></span> <span data-ttu-id="20a60-114">파일을 메모장에서 연 후 다음 텍스트를 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="20a60-114">Open the file in Notepad and copy and paste the following text:</span></span>  
  
```xml  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>International Bank</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1970</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>7000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>T1</Internet>  
  <NumberEmployees>2</NumberEmployees>  
</StoreSurvey>  
```  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Xml  
  
Module Module1  
    Sub Main()  
  
        Using connection As SqlConnection = New SqlConnection(GetConnectionString())  
        connection.Open()  
  
        ' Create a sample table (dropping first if it already  
        ' exists.)  
        Dim commandNewTable As String = _  
         "IF EXISTS (SELECT * FROM dbo.sysobjects " & _  
         "WHERE id = object_id(N'[dbo].[XmlDataTypeSample]') " & _  
         "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " & _  
         "DROP TABLE [dbo].[XmlDataTypeSample];" & _  
         "CREATE TABLE [dbo].[XmlDataTypeSample](" & _  
         "[SalesID] [int] IDENTITY(1,1) NOT NULL, " & _  
         "[SalesInfo] [xml])"  
  
        Dim commandAdd As New _  
         SqlCommand(commandNewTable, connection)  
        commandAdd.ExecuteNonQuery()  
  
        Dim commandText As String = _  
         "INSERT INTO [dbo].[XmlDataTypeSample] " & _  
           "([SalesInfo] ) " & _  
           "VALUES(@xmlParameter )"  
  
        Dim command As New SqlCommand(commandText, connection)  
  
        ' Read the saved XML document as a   
        ' SqlXml-data typed variable.  
        Dim newXml As SqlXml = _  
         New SqlXml(New XmlTextReader("MyTestStoreData.xml"))  
  
        ' Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml)  
  
        Dim result As Integer = command.ExecuteNonQuery()  
        Console.WriteLine(result & " row was added.")  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Using  
End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Xml;  
using System.Data.SqlTypes;  
  
class Class1  
{  
    static void Main()  
    {  
        using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
       {  
        connection.Open();  
        //  Create a sample table (dropping first if it already  
        //  exists.)  
  
        string commandNewTable =   
            "IF EXISTS (SELECT * FROM dbo.sysobjects " +   
            "WHERE id = " +  
                  "object_id(N'[dbo].[XmlDataTypeSample]') " +   
            "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " +   
            "DROP TABLE [dbo].[XmlDataTypeSample];" +   
            "CREATE TABLE [dbo].[XmlDataTypeSample](" +   
            "[SalesID] [int] IDENTITY(1,1) NOT NULL, " +   
            "[SalesInfo] [xml])";  
        SqlCommand commandAdd =   
                   new SqlCommand(commandNewTable, connection);  
        commandAdd.ExecuteNonQuery();  
        string commandText =   
            "INSERT INTO [dbo].[XmlDataTypeSample] " +   
            "([SalesInfo] ) " +   
            "VALUES(@xmlParameter )";  
        SqlCommand command =   
                  new SqlCommand(commandText, connection);  
  
        //  Read the saved XML document as a   
        //  SqlXml-data typed variable.  
        SqlXml newXml =   
            new SqlXml(new XmlTextReader("MyTestStoreData.xml"));  
  
        //  Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml);  
  
        int result = command.ExecuteNonQuery();  
        Console.WriteLine(result + " row was added.");  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,              
        // you can retrieve it from a configuration file.   
        return "Data Source=(local);Integrated Security=true;" +  
        "Initial Catalog=AdventureWorks; ";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="20a60-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="20a60-115">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="20a60-116">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="20a60-116">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [<span data-ttu-id="20a60-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="20a60-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
