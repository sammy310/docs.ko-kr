---
title: XML Web Service에서 데이터 집합 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: 7b284a8f085ab7e93651c829ac16e47fb63a8b51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034478"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="3c476-102">XML Web Service에서 데이터 집합 사용</span><span class="sxs-lookup"><span data-stu-id="3c476-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="3c476-103"><xref:System.Data.DataSet>은 인터넷에서 데이터 전송을 쉽게 할 수 있도록 비연결 디자인으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="3c476-104">합니다 **데이터 집합** 는 "직렬화"에 대 한 입력으로 지정할 수도 있고 추가 코딩 없이 XML Web services에서 출력의 콘텐츠를 스트리밍하는 데 필요한 합니다 **데이터 집합** XML 웹 서비스에서 클라이언트 및 백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="3c476-105">**데이터 집합** DiffGram 형식을 사용 하 여 XML 스트림을로 암시적으로 변환, 네트워크를 통해 보내고 다음으로 XML 스트림에서 재구성을 **데이터 집합** 수신측에 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="3c476-106">이렇게 하여 간단하고 융통성 있는 방법으로 XML Web services를 사용하여 관계형 데이터를 전송하고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="3c476-107">DiffGram 형식에 대 한 자세한 내용은 참조 하세요. [Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-107">For more information about the DiffGram format, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>  
  
 <span data-ttu-id="3c476-108">다음 예제에는 XML 웹 서비스 및 사용 하는 클라이언트를 만드는 방법을 보여 줍니다 합니다 **데이터 집합** 를 (수정 된 데이터 포함)는 관계형 데이터를 전송 및 모든 업데이트를 데이터 원본에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c476-109">XML Web services를 만들 때는 항상 보안 측면을 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="3c476-110">XML 웹 서비스 보안에 대 한 내용은 참조 하세요 [보안 XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="3c476-111">DataSet을 반환하고 사용하는 XML Web services를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3c476-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1. <span data-ttu-id="3c476-112">XML Web services를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="3c476-113">예제에서는 XML 웹 서비스를 만들어집니다의 고객 목록을이 경우 데이터를 반환 하는 합니다 **Northwind** 받고 데이터베이스에 **데이터 집합** 데이터에 대 한 업데이트를 사용 하 여는 XML 웹 서비스 데이터 원본에 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="3c476-114">XML 웹 서비스는 두 가지 방법을 제공합니다. **GetCustomers**, 고객의 목록을 반환 하 고 **UpdateCustomers**, 데이터 원본에 다시 업데이트를 해결 하려면.</span><span class="sxs-lookup"><span data-stu-id="3c476-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="3c476-115">XML Web services는 웹 서버에 있는 DataSetSample.asmx라는 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="3c476-116">다음 코드는 DataSetSample.asmx의 내용을 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="3c476-117">일반적인 시나리오의 경우에 **UpdateCustomers** 메서드를 작성 하 여 낙관적 동시성 위반을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="3c476-118">위의 예제에서는 내용을 간단하게 하기 위해 제외되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="3c476-119">낙관적 동시성에 대 한 자세한 내용은 참조 하세요. [낙관적 동시성](../../../../../docs/framework/data/adonet/optimistic-concurrency.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="3c476-120">XML Web services 프록시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="3c476-121">XML Web services의 클라이언트는 SOAP 프록시가 있어야 노출된 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="3c476-122">Visual Studio로 이 프록시를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="3c476-123">웹 참조를 Visual Studio 내의 기존 웹 서비스로 설정하면 이 단계에 기술된 모든 동작이 투명하게 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="3c476-124">프록시 클래스를 직접 만들려면 추가 설명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="3c476-125">그러나 대부분의 경우에는 Visual Studio를 사용하여 클라이언트 응용 프로그램용 프록시 클래스를 만드는 것으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="3c476-126">프록시는 웹 서비스 설명 언어 도구를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="3c476-127">예를 들어, XML 웹 서비스 URL에 노출 되는 경우 `http://myserver/data/DataSetSample.asmx`, 네임 스페이스를 사용 하 여 Visual Basic.NET 프록시를 만들려면 다음과 같은 명령을 실행할 **WebData.DSSample** sample.vb 파일에에서 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="3c476-128">다음 명령을 실행하면 sample.cs에 C# 프록시를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="3c476-129">그런 다음 프록시를 라이브러리로 컴파일하여 XML Web services 클라이언트에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="3c476-130">다음 명령을 실행하면 sample.vb에 저장된 Visual Basic .NET 프록시 코드를 sample.dll로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="3c476-131">다음 명령을 실행하면 sample.cs에 저장된 C# 프록시 코드를 sample.dll로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="3c476-132">XML Web services 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="3c476-133">Visual studio 웹 서비스 프록시 클래스를 생성 하려는 경우 단순히 클라이언트 프로젝트를 만들을 솔루션 탐색기 창에서 프로젝트를 마우스 오른쪽 단추로 클릭 **웹 참조 추가**에서 웹 서비스를 선택 합니다. (이 필요할 수 있습니다 웹 서비스 끝점의 주소를 제공 합니다. 웹 서비스를 현재 솔루션 내에서 또는 현재 컴퓨터에서 사용할 수 없는 경우.)는 사용 가능한 웹 서비스 목록 이전 단계의 설명에 따라 XML Web services 프록시를 직접 만드는 경우 프록시를 클라이언트 코드에 가져와 XML Web services 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="3c476-134">다음 샘플 코드에서는 프록시 라이브러리를 호출을 가져옵니다 **GetCustomers** 고객의 목록을 가져오려면에 추가한 새 고객이 다음 반환 된 **데이터 집합** 업데이트를 사용 하 여 **UpdateCustomers** .</span><span class="sxs-lookup"><span data-stu-id="3c476-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="3c476-135">전달 하는 **데이터 집합** 반환한 **DataSet.GetChanges** 하 **UpdateCustomers** 수정 된 행만 전달할 필요가 없으므로  **UpdateCustomers**합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="3c476-136">**UpdateCustomers** 확인 된 반환 **데이터 집합**를 할 수 있습니다는 **병합** 기존 **데이터 집합** 된 변경 내용 및 통합 행 업데이트 작업에서 오류 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="3c476-137">다음 코드에 웹 참조를 만들려면 Visual Studio를 사용 하 고 웹 참조의 DsSample로 바꾼 것으로 가정 합니다 **웹 참조 추가** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="3c476-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="3c476-138">프록시 클래스를 직접 만드는 경우 다음 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="3c476-139">샘플을 컴파일하려면 앞에서 만든 프록시 라이브러리(sample.dll)와 관련 .NET 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="3c476-140">다음 명령을 실행하면 client.vb 파일에 저장된 샘플의 Visual Basic .NET 버전을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="3c476-141">다음 명령을 실행하면 client.cs 파일에 저장된 샘플의 C# 버전을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c476-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3c476-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c476-142">See also</span></span>

- [<span data-ttu-id="3c476-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3c476-143">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="3c476-144">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="3c476-144">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="3c476-145">DataTable</span><span class="sxs-lookup"><span data-stu-id="3c476-145">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="3c476-146">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="3c476-146">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="3c476-147">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="3c476-147">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="3c476-148">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c476-148">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- <span data-ttu-id="3c476-149">[웹 서비스 기술 언어 도구 (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3c476-149">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="3c476-150">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3c476-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
