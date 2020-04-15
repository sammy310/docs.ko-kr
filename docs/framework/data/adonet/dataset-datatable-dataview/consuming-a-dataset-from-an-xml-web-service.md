---
title: XML Web Service에서 데이터 세트 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: d7328949e3eb4822b1a645bb5f0c1866f01ecb0a
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389746"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a>XML 웹 서비스에서 데이터 집합 사용

<xref:System.Data.DataSet>은 인터넷에서 데이터 전송을 쉽게 할 수 있도록 비연결 디자인으로 설계되었습니다. **DataSet은** XML 웹 서비스에서 클라이언트로 **데이터 집합의** 내용을 스트리밍하는 데 필요한 추가 코딩 없이 XML 웹 서비스에 대한 입력 또는 출력으로 지정할 수 있다는 점에서 "serializable"입니다. **DataSet은** DiffGram 형식을 사용하여 XML 스트림으로 암시적으로 변환되고 네트워크를 통해 전송된 다음 XML 스트림에서 수신 측의 **DataSet으로** 재구성됩니다. 이렇게 하여 간단하고 융통성 있는 방법으로 XML Web services를 사용하여 관계형 데이터를 전송하고 반환할 수 있습니다. DiffGram 형식에 대한 자세한 내용은 [DiffGrams](diffgrams.md)를 참조하십시오.  
  
 다음 예제에서는 **DataSet을** 사용하여 관계형 데이터(수정된 데이터 포함)를 전송하고 업데이트를 원래 데이터 원본으로 다시 해결하는 XML 웹 서비스 및 클라이언트를 만드는 방법을 보여 주며 있습니다.  
  
> [!NOTE]
> XML Web services를 만들 때는 항상 보안 측면을 고려하는 것이 좋습니다. XML 웹 서비스 보안에 대한 자세한 내용은 [ASP.NET 사용하여 만든 XML 웹 서비스 보안을](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))참조하십시오.  
  
## <a name="create-an-xml-web-service"></a>XML 웹 서비스 만들기
  
1. XML Web services를 만듭니다.  
  
     이 예제에서는 데이터를 반환하는 XML 웹 서비스가 만들어지며, 이 경우 **Northwind** 데이터베이스의 고객 목록이 생성되고 XML 웹 서비스가 원래 데이터 원본으로 다시 확인되는 데이터에 대한 업데이트가 포함된 **DataSet을** 수신합니다.  
  
     XML 웹 서비스는 두 가지 방법을 노출합니다: **GetCustomers**, 고객 목록을 반환하는 방법 및 **UpdateCustomers**, 데이터 원본으로 업데이트를 다시 확인합니다. XML Web services는 웹 서버에 있는 DataSetSample.asmx라는 파일로 저장됩니다. 다음 코드는 DataSetSample.asmx의 내용을 요약한 것입니다.  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     일반적인 시나리오에서 **UpdateCustomers** 메서드는 낙관적 동시성 위반을 catch하도록 작성됩니다. 위의 예제에서는 내용을 간단하게 하기 위해 제외되었습니다. 낙관적 동시성 에 대한 자세한 내용은 [낙관적 동시성을](../optimistic-concurrency.md)참조하십시오.  
  
2. XML Web services 프록시를 만듭니다.  
  
     XML Web services의 클라이언트는 SOAP 프록시가 있어야 노출된 메서드를 사용할 수 있습니다. Visual Studio로 이 프록시를 생성할 수 있습니다. 웹 참조를 Visual Studio 내의 기존 웹 서비스로 설정하면 이 단계에 기술된 모든 동작이 투명하게 일어납니다. 프록시 클래스를 직접 만들려면 추가 설명이 필요합니다. 그러나 대부분의 경우에는 Visual Studio를 사용하여 클라이언트 애플리케이션용 프록시 클래스를 만드는 것으로 충분합니다.  
  
     프록시는 웹 서비스 설명 언어 도구를 사용하여 만들 수 있습니다. 예를 들어 XML 웹 서비스가 URL에 `http://myserver/data/DataSetSample.asmx`노출되면 다음과 같은 명령을 사용하여 **WebData.DSSample의** 네임스페이스가 있는 Visual Basic .NET 프록시를 만들고 파일 sample.vb에 저장합니다.  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     다음 명령을 실행하면 sample.cs에 C# 프록시를 만들 수 있습니다.  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     그런 다음 프록시를 라이브러리로 컴파일하여 XML Web services 클라이언트에 가져올 수 있습니다. 다음 명령을 실행하면 sample.vb에 저장된 Visual Basic .NET 프록시 코드를 sample.dll로 컴파일할 수 있습니다.  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     다음 명령을 실행하면 sample.cs에 저장된 C# 프록시 코드를 sample.dll로 컴파일할 수 있습니다.  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. XML Web services 클라이언트를 만듭니다.  
  
     Visual Studio에서 웹 서비스 프록시 클래스를 생성하려면 클라이언트 프로젝트를 만들고 솔루션 탐색기 창에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음**서비스 참조** **추가를** > 선택합니다. 서비스 **참조 추가** 대화 상자에서 **고급**을 선택한 다음 웹 **참조 추가를**선택합니다. 사용 가능한 웹 서비스 목록에서 웹 서비스를 선택합니다(현재 솔루션 내에서 또는 현재 컴퓨터에서 웹 서비스를 사용할 수 없는 경우 웹 서비스 끝점의 주소를 제공해야 할 수 있습니다). 이전 단계의 설명에 따라 XML Web services 프록시를 직접 만드는 경우 프록시를 클라이언트 코드에 가져와 XML Web services 메서드를 사용합니다.

     다음 샘플 코드는 프록시 라이브러리를 **가져오고, GetCustomers를** 호출하여 고객 목록을 가져오고, 새 고객을 추가한 다음 **UpdateCustomers**에 대한 업데이트와 함께 **DataSet을** 반환합니다.  
  
     이 예제는 수정된 행만 **UpdateCustomers**에 전달해야 하기 때문에 **DataSet.GetChanges에서** 반환된 **DataSet을** 전달합니다. **UpdateCustomers** **UpdateCustomers는** 해결된 **데이터 집합을**반환한 다음 기존 **DataSet에** **병합하여** 업데이트에서 해결된 변경 내용 및 행 오류 정보를 통합할 수 있습니다. 다음 코드는 Visual Studio를 사용하여 웹 참조를 만들었으며 웹 참조 **추가** 대화 상자에서 DsSample에 대한 웹 참조의 이름을 변경했다고 가정합니다.  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     프록시 클래스를 직접 만드는 경우 다음 추가 단계를 수행해야 합니다. 샘플을 컴파일하려면 앞에서 만든 프록시 라이브러리(sample.dll)와 관련 .NET 라이브러리를 제공합니다. 다음 명령을 실행하면 client.vb 파일에 저장된 샘플의 Visual Basic .NET 버전을 컴파일할 수 있습니다.  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     다음 명령을 실행하면 client.cs 파일에 저장된 샘플의 C# 버전을 컴파일할 수 있습니다.  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET](../index.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [DataTables](datatables.md)
- [DataAdapter에서 DataSet 채우기](../populating-a-dataset-from-a-dataadapter.md)
- [DataAdapters로 데이터 원본 업데이트](../updating-data-sources-with-dataadapters.md)
- [DataAdapter 매개 변수](../dataadapter-parameters.md)
- [웹 서비스 설명 언어 도구(Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [ADO.NET 개요](../ado-net-overview.md)
