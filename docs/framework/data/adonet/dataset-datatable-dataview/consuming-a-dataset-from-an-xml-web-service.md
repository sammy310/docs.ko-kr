---
title: XML Web Services에서 데이터 집합 사용
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: e6dc32274cc3b0d7ec9d66a837a422c87fb2468b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416216"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="b56d2-102">XML web services에서 데이터 집합 사용</span><span class="sxs-lookup"><span data-stu-id="b56d2-102">Consume a DataSet from an XML web service</span></span>

<span data-ttu-id="b56d2-103"><xref:System.Data.DataSet>은 인터넷에서 데이터 전송을 쉽게 할 수 있도록 비연결 디자인으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="b56d2-104">데이터 **집합** 은 xml web services에서 클라이언트로 **데이터 집합** 의 내용을 스트리밍하는 데 필요한 추가 코딩 없이 xml web services의 입력 또는 출력으로 지정 될 수 있다는 것을 "serializable"로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="b56d2-105">**데이터 집합** 은 DiffGram 형식을 사용 하 여 암시적으로 xml 스트림으로 변환 된 다음 네트워크를 통해 전송 된 다음 수신 하는 끝의 **데이터 집합** 으로 xml 스트림에서 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="b56d2-106">이를 통해 XML Web services를 사용 하 여 관계형 데이터를 전송 하 고 반환 하는 간단 하 고 유연한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-106">This gives you a simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="b56d2-107">DiffGram 형식에 대 한 자세한 내용은 [diffgram](diffgrams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b56d2-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="b56d2-108">다음 예제에서는 **데이터 집합** 을 사용 하 여 관계형 데이터 (수정 된 데이터 포함)를 전송 하 고 원래 데이터 원본에 대 한 업데이트를 다시 확인 하는 XML Web services 및 클라이언트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b56d2-109">`DataSet`입력을 `DataTable` 신뢰할 수 없는 경우 XML Web services 호출의 일부로 또는 인스턴스를 전송 하는 것은 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-109">Transmitting `DataSet` or `DataTable` instances as part of XML Web service calls is not safe if the input is not trusted.</span></span> <span data-ttu-id="b56d2-110">자세한 내용은 [DataSet 및 DataTable 보안 지침](security-guidance.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b56d2-110">For more information, see [DataSet and DataTable security guidance](security-guidance.md).</span></span>
> <span data-ttu-id="b56d2-111">또한 XML Web services를 만들 때 항상 보안 문제를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-111">We also recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="b56d2-112">XML Web Services를 보호 하는 방법에 대 한 자세한 내용은 [ASP.NET를 사용 하 여 만든 Xml Web Services 보안](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b56d2-112">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
## <a name="create-an-xml-web-service"></a><span data-ttu-id="b56d2-113">XML web services 만들기</span><span class="sxs-lookup"><span data-stu-id="b56d2-113">Create an XML web service</span></span>
  
1. <span data-ttu-id="b56d2-114">XML Web services를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-114">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="b56d2-115">이 예제에서는 데이터를 반환 하는 XML Web services (이 경우 **Northwind** 데이터베이스의 고객 목록)를 생성 하 고 데이터에 대 한 업데이트를 포함 하는 데이터 **집합** 을 받습니다 .이 데이터는 xml web services가 원래 데이터 원본으로 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-115">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="b56d2-116">XML Web services는 **GetCustomers**, 고객 목록을 반환 하기 위한 두 가지 메서드 및 **UpdateCustomers**를 노출 하 여 업데이트를 다시 데이터 원본으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-116">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="b56d2-117">XML Web services는 웹 서버에 있는 DataSetSample.asmx라는 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-117">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="b56d2-118">다음 코드는 DataSetSample.asmx의 내용을 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-118">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="b56d2-119">일반적인 시나리오에서 낙관적 동시성 위반을 catch 하도록 **UpdateCustomers** 메서드가 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-119">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="b56d2-120">위의 예제에서는 내용을 간단하게 하기 위해 제외되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-120">For simplicity, the example does not include this.</span></span> <span data-ttu-id="b56d2-121">낙관적 동시성에 대 한 자세한 내용은 [낙관적 동시성](../optimistic-concurrency.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b56d2-121">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="b56d2-122">XML Web services 프록시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-122">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="b56d2-123">XML Web services의 클라이언트는 SOAP 프록시가 있어야 노출된 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-123">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="b56d2-124">Visual Studio로 이 프록시를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-124">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="b56d2-125">웹 참조를 Visual Studio 내의 기존 웹 서비스로 설정하면 이 단계에 기술된 모든 동작이 투명하게 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-125">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="b56d2-126">프록시 클래스를 직접 만들려면 추가 설명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-126">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="b56d2-127">그러나 대부분의 경우에는 Visual Studio를 사용하여 클라이언트 애플리케이션용 프록시 클래스를 만드는 것으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-127">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="b56d2-128">프록시는 웹 서비스 설명 언어 도구를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-128">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="b56d2-129">예를 들어, XML Web services가 URL에서 노출 되는 경우 `http://myserver/data/DataSetSample.asmx` 다음과 같은 명령을 실행 하 여 **WebData** 의 네임 스페이스를 사용 하는 Visual Basic .net 프록시를 만들고 파일 샘플에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-129">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b56d2-130">다음 명령을 실행하면 sample.cs에 C# 프록시를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-130">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b56d2-131">그런 다음 프록시를 라이브러리로 컴파일하여 XML Web services 클라이언트에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-131">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="b56d2-132">다음 명령을 실행하면 sample.vb에 저장된 Visual Basic .NET 프록시 코드를 sample.dll로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-132">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="b56d2-133">다음 명령을 실행하면 sample.cs에 저장된 C# 프록시 코드를 sample.dll로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-133">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="b56d2-134">XML Web services 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-134">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="b56d2-135">Visual Studio에서 웹 서비스 프록시 클래스를 생성 하도록 하려면 클라이언트 프로젝트를 만들고 솔루션 탐색기 창에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **Add**  >  **서비스 참조**추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-135">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, and then select **Add** > **Service Reference**.</span></span> <span data-ttu-id="b56d2-136">**서비스 참조 추가** 대화 상자에서 **고급**을 선택한 다음 **웹 참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-136">In the **Add Service Reference** dialog box, select **Advanced**, and then select **Add Web Reference**.</span></span> <span data-ttu-id="b56d2-137">사용 가능한 웹 서비스 목록에서 웹 서비스를 선택 합니다. 현재 솔루션 또는 현재 컴퓨터에서 웹 서비스를 사용할 수 없는 경우 웹 서비스 끝점의 주소를 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-137">Select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint if the Web service isn't available within the current solution or on the current computer).</span></span> <span data-ttu-id="b56d2-138">이전 단계의 설명에 따라 XML Web services 프록시를 직접 만드는 경우 프록시를 클라이언트 코드에 가져와 XML Web services 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-138">If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span>

     <span data-ttu-id="b56d2-139">다음 샘플 코드는 프록시 라이브러리를 가져오고 **GetCustomers** 를 호출 하 여 고객 목록을 가져오고 새 고객을 추가한 다음 **UpdateCustomers**에 대 한 업데이트가 포함 된 **데이터 집합** 을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-139">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="b56d2-140">이 예에서는 수정 된 행만 **UpdateCustomers**에 전달 해야 하므로 GetChanges에서 반환 된 **데이터 집합** 을 **UpdateCustomers** 에 전달 합니다 **.**</span><span class="sxs-lookup"><span data-stu-id="b56d2-140">The example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="b56d2-141">**UpdateCustomers** 는 확인 된 **데이터 집합**을 반환 합니다 .이 데이터 집합은 업데이트의 해결 된 변경 내용 및 모든 행 오류 정보를 통합 하기 위해 기존 **데이터 집합** 에 **병합할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-141">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="b56d2-142">다음 코드에서는 Visual Studio를 사용 하 여 웹 참조를 만들고 웹 **참조 추가** 대화 상자에서 dssample에 대 한 웹 참조의 이름을 바꾸 었는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-142">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="b56d2-143">프록시 클래스를 직접 만드는 경우 다음 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-143">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="b56d2-144">샘플을 컴파일하려면 앞에서 만든 프록시 라이브러리(sample.dll)와 관련 .NET 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-144">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="b56d2-145">다음 명령을 실행하면 client.vb 파일에 저장된 샘플의 Visual Basic .NET 버전을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-145">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="b56d2-146">다음 명령을 실행하면 client.cs 파일에 저장된 샘플의 C# 버전을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56d2-146">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b56d2-147">참조</span><span class="sxs-lookup"><span data-stu-id="b56d2-147">See also</span></span>

- [<span data-ttu-id="b56d2-148">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b56d2-148">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="b56d2-149">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="b56d2-149">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b56d2-150">DataTables</span><span class="sxs-lookup"><span data-stu-id="b56d2-150">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="b56d2-151">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="b56d2-151">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="b56d2-152">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="b56d2-152">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="b56d2-153">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b56d2-153">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="b56d2-154">[웹 서비스 기술 언어 도구 (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b56d2-154">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="b56d2-155">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b56d2-155">ADO.NET Overview</span></span>](../ado-net-overview.md)
