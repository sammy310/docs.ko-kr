---
title: DbProviderFactory 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
ms.openlocfilehash: c84229dc1c32217099eb7ed8b90accc04cc66148
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097410"
---
# <a name="obtaining-a-dbproviderfactory"></a><span data-ttu-id="a5459-102">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="a5459-102">Obtaining a DbProviderFactory</span></span>
<span data-ttu-id="a5459-103"><xref:System.Data.Common.DbProviderFactory>를 가져오는 프로세스에서는 데이터 공급자에 대한 정보가 <xref:System.Data.Common.DbProviderFactories> 클래스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-103">The process of obtaining a <xref:System.Data.Common.DbProviderFactory> involves passing information about a data provider to the <xref:System.Data.Common.DbProviderFactories> class.</span></span> <span data-ttu-id="a5459-104"><xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드는 이 정보를 기반으로 하여 강력한 형식의 공급자 팩터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-104">Based on this information, the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method creates a strongly typed provider factory.</span></span> <span data-ttu-id="a5459-105">예를 들어 <xref:System.Data.SqlClient.SqlClientFactory>를 만들려면 공급자 이름을 "System.Data.SqlClient"로 지정하는 문자열을 `GetFactory`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-105">For example, to create a <xref:System.Data.SqlClient.SqlClientFactory>, you can pass `GetFactory` a string with the provider name specified as "System.Data.SqlClient".</span></span> <span data-ttu-id="a5459-106">`GetFactory`의 다른 오버로드는 <xref:System.Data.DataRow>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-106">The other overload of `GetFactory` takes a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="a5459-107">공급자 팩터리를 만든 후에는 해당 메서드를 사용하여 다른 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-107">Once you create the provider factory, you can then use its methods to create additional objects.</span></span> <span data-ttu-id="a5459-108">`SqlClientFactory`의 메서드로는 <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> 및 <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-108">Some of the methods of a `SqlClientFactory` include <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A>, and <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5459-109">.NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> 및 <xref:System.Data.OleDb.OleDbFactory> 클래스도 이와 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-109">The .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory>, and <xref:System.Data.OleDb.OleDbFactory> classes also provide similar functionality.</span></span>  
  
## <a name="registering-dbproviderfactories"></a><span data-ttu-id="a5459-110">DbProviderFactories 등록</span><span class="sxs-lookup"><span data-stu-id="a5459-110">Registering DbProviderFactories</span></span>  
 <span data-ttu-id="a5459-111">팩터리 기반의 클래스를 지 원하는 각.NET Framework 데이터 공급자에서 구성 정보를 등록 합니다 **DbProviderFactories** 섹션을 **machine.config** 로컬 컴퓨터의 파일.</span><span class="sxs-lookup"><span data-stu-id="a5459-111">Each .NET Framework data provider that supports a factory-based class registers configuration information in the **DbProviderFactories** section of the **machine.config** file on the local computer.</span></span> <span data-ttu-id="a5459-112">다음 구성 파일 조각에서는 <xref:System.Data.SqlClient>의 구문과 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-112">The following configuration file fragment shows the syntax and format for <xref:System.Data.SqlClient>.</span></span>  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"   
     description=".Net Framework Data Provider for SqlServer"   
     type="System.Data.SqlClient.SqlClientFactory, System.Data,   
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 <span data-ttu-id="a5459-113">합니다 **고정** 특성은 기본 데이터 공급자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-113">The **invariant** attribute identifies the underlying data provider.</span></span> <span data-ttu-id="a5459-114">세 부분으로 이루어진 이 명명 구문은 새 팩터리를 만들 때뿐만 아니라 공급자 이름 및 관련된 연결 문자열을 런타임에 검색할 수 있도록 응용 프로그램 구성 파일에서 공급자를 식별하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-114">This three-part naming syntax is also used when creating a new factory and for identifying the provider in an application configuration file so that the provider name, along with its associated connection string, can be retrieved at run time.</span></span>  
  
## <a name="retrieving-provider-information"></a><span data-ttu-id="a5459-115">공급자 정보 검색</span><span class="sxs-lookup"><span data-stu-id="a5459-115">Retrieving Provider Information</span></span>  
 <span data-ttu-id="a5459-116"><xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하면 로컬 컴퓨터에 설치되어 있는 데이터 공급자에 대한 모든 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-116">You can retrieve information about all of the data providers installed on the local computer by using the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method.</span></span> <span data-ttu-id="a5459-117">반환을 <xref:System.Data.DataTable> 라는 **DbProviderFactories** 다음 표에서 설명 하는 열을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-117">It returns a <xref:System.Data.DataTable> named **DbProviderFactories** that contains the columns described in the following table.</span></span>  
  
|<span data-ttu-id="a5459-118">열 서수</span><span class="sxs-lookup"><span data-stu-id="a5459-118">Column ordinal</span></span>|<span data-ttu-id="a5459-119">열 이름</span><span class="sxs-lookup"><span data-stu-id="a5459-119">Column name</span></span>|<span data-ttu-id="a5459-120">예제 출력</span><span class="sxs-lookup"><span data-stu-id="a5459-120">Example output</span></span>|<span data-ttu-id="a5459-121">설명</span><span class="sxs-lookup"><span data-stu-id="a5459-121">Description</span></span>|  
|--------------------|-----------------|--------------------|-----------------|  
|<span data-ttu-id="a5459-122">0</span><span class="sxs-lookup"><span data-stu-id="a5459-122">0</span></span>|<span data-ttu-id="a5459-123">**이름**</span><span class="sxs-lookup"><span data-stu-id="a5459-123">**Name**</span></span>|<span data-ttu-id="a5459-124">SqlClient Data Provider</span><span class="sxs-lookup"><span data-stu-id="a5459-124">SqlClient Data Provider</span></span>|<span data-ttu-id="a5459-125">읽을 수 있는 데이터 공급자 이름</span><span class="sxs-lookup"><span data-stu-id="a5459-125">Readable name for the data provider</span></span>|  
|<span data-ttu-id="a5459-126">1</span><span class="sxs-lookup"><span data-stu-id="a5459-126">1</span></span>|<span data-ttu-id="a5459-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="a5459-127">**Description**</span></span>|<span data-ttu-id="a5459-128">.Net Framework Data Provider for SqlServer</span><span class="sxs-lookup"><span data-stu-id="a5459-128">.Net Framework Data Provider for SqlServer</span></span>|<span data-ttu-id="a5459-129">읽을 수 있는 데이터 공급자 설명</span><span class="sxs-lookup"><span data-stu-id="a5459-129">Readable description of the data provider</span></span>|  
|<span data-ttu-id="a5459-130">2</span><span class="sxs-lookup"><span data-stu-id="a5459-130">2</span></span>|<span data-ttu-id="a5459-131">**InvariantName**</span><span class="sxs-lookup"><span data-stu-id="a5459-131">**InvariantName**</span></span>|<span data-ttu-id="a5459-132">System.Data.SqlClient</span><span class="sxs-lookup"><span data-stu-id="a5459-132">System.Data.SqlClient</span></span>|<span data-ttu-id="a5459-133">데이터 공급자를 프로그래밍 방식으로 참조하는 데 사용할 수 있는 이름</span><span class="sxs-lookup"><span data-stu-id="a5459-133">Name that can be used programmatically to refer to the data provider</span></span>|  
|<span data-ttu-id="a5459-134">3</span><span class="sxs-lookup"><span data-stu-id="a5459-134">3</span></span>|<span data-ttu-id="a5459-135">**AssemblyQualifiedName**</span><span class="sxs-lookup"><span data-stu-id="a5459-135">**AssemblyQualifiedName**</span></span>|<span data-ttu-id="a5459-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="a5459-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span></span>|<span data-ttu-id="a5459-137">개체를 인스턴스화하는 데 충분한 정보가 포함된 팩터리 클래스의 정규화된 이름</span><span class="sxs-lookup"><span data-stu-id="a5459-137">Fully qualified name of the factory class, which contains enough information to instantiate the object</span></span>|  
  
 <span data-ttu-id="a5459-138">이 `DataTable`을 사용하면 런타임에 사용자가 <xref:System.Data.DataRow>를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-138">This `DataTable` can be used to enable a user to select a <xref:System.Data.DataRow> at run time.</span></span> <span data-ttu-id="a5459-139">그런 다음 선택한 `DataRow`를 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드에 전달하여 강력한 형식의 <xref:System.Data.Common.DbProviderFactory>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-139">The selected `DataRow` can then be passed to the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method to create a strongly typed <xref:System.Data.Common.DbProviderFactory>.</span></span> <span data-ttu-id="a5459-140">선택한 <xref:System.Data.DataRow>를 `GetFactory` 메서드에 전달하면 원하는 `DbProviderFactory` 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-140">A selected <xref:System.Data.DataRow> can be passed to the `GetFactory` method to create the desired `DbProviderFactory` object.</span></span>  
  
## <a name="listing-the-installed-provider-factory-classes"></a><span data-ttu-id="a5459-141">설치되어 있는 공급자 팩터리 클래스 나열</span><span class="sxs-lookup"><span data-stu-id="a5459-141">Listing the Installed Provider Factory Classes</span></span>  
 <span data-ttu-id="a5459-142">이 예제에서는 <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하여 설치되어 있는 공급자에 대한 정보가 포함된 <xref:System.Data.DataTable>을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-142">This example demonstrates how to use the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method to return a <xref:System.Data.DataTable> containing information about the installed providers.</span></span> <span data-ttu-id="a5459-143">이 코드는 `DataTable`의 각 행을 반복하여 현재 설치되어 있는 각 공급자에 대한 정보를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-143">The code iterates through each row in the `DataTable`, displaying information for each installed provider in the console window.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a><span data-ttu-id="a5459-144">응용 프로그램 구성 파일을 사용하여 팩터리 정보 저장</span><span class="sxs-lookup"><span data-stu-id="a5459-144">Using Application Configuration Files to Store Factory Information</span></span>  
 <span data-ttu-id="a5459-145">팩터리를 사용 하 여 작업에 사용 되는 디자인 패턴은 같은 응용 프로그램 구성 파일에서 공급자 및 연결 문자열 정보를 저장 해야 **app.config** Windows 응용 프로그램의 경우 및 **web.config**  ASP.NET 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-145">The design pattern used for working with factories entails storing provider and connection string information in an application configuration file, such as **app.config** for a Windows application, and **web.config** for an ASP.NET application.</span></span>  
  
 <span data-ttu-id="a5459-146">다음 구성 파일 조각에서는 SQL Server에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindSQL" 및 Access/Jet에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindAccess"라는 두 가지 명명된 연결 문자열을 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-146">The following configuration file fragment demonstrates how to save two named connection strings, "NorthwindSQL" for a connection to the Northwind database in SQL Server, and "NorthwindAccess" for a connection to the Northwind database in Access/Jet.</span></span> <span data-ttu-id="a5459-147">**고정** 이름에 사용 되는 **providerName** 특성.</span><span class="sxs-lookup"><span data-stu-id="a5459-147">The **invariant** name is used for the **providerName** attribute.</span></span>  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"   
     providerName="System.Data.SqlClient"   
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"   
     providerName="System.Data.OleDb"   
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a><span data-ttu-id="a5459-148">공급자 이름을 사용하여 연결 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="a5459-148">Retrieving a Connection String by Provider Name</span></span>  
 <span data-ttu-id="a5459-149">공급자 팩터리를 만들려면 연결 문자열뿐만 아니라 공급자 이름도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-149">In order to create a provider factory, you must supply a connection string as well as the provider name.</span></span> <span data-ttu-id="a5459-150">이 예제에는 고정 형식으로 공급자 이름을 전달 하 여 응용 프로그램 구성 파일에서 연결 문자열을 검색 하는 방법을 보여 줍니다. "*System.Data.ProviderName*"입니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-150">This example demonstrates how to retrieve a connection string from an application configuration file by passing the provider name in the invariant format "*System.Data.ProviderName*".</span></span> <span data-ttu-id="a5459-151">이 코드는 <xref:System.Configuration.ConnectionStringSettingsCollection>을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-151">The code iterates through the <xref:System.Configuration.ConnectionStringSettingsCollection>.</span></span> <span data-ttu-id="a5459-152">메서드가 성공하면 <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>이 반환되고, 그렇지 않으면 `null`(Visual Basic의 경우에는 `Nothing`)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-152">It returns the <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> on success; otherwise `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="a5459-153">공급자에 대한 항목이 여러 개 있으면 응용 프로그램 구성 파일에서 찾은 첫 번째 항목이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-153">If there are multiple entries for a provider, the first one found is returned.</span></span> <span data-ttu-id="a5459-154">자세한 정보 및 구성 파일에서 연결 문자열을 검색 하는 예제를 참조 하세요 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-154">For more information and examples of retrieving connection strings from configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5459-155">코드를 실행하려면 `System.Configuration.dll`에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-155">A reference to `System.Configuration.dll` is required in order for the code to run.</span></span>  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a><span data-ttu-id="a5459-156">DbProviderFactory 및 DbConnection 만들기</span><span class="sxs-lookup"><span data-stu-id="a5459-156">Creating the DbProviderFactory and DbConnection</span></span>  
 <span data-ttu-id="a5459-157">만드는 방법을 보여 주는이 예제는 <xref:System.Data.Common.DbProviderFactory> 및 <xref:System.Data.Common.DbConnection> 개체 형식으로 공급자 이름을 전달 하 여 "*System.Data.ProviderName*" 및 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-157">This example demonstrates how to create a <xref:System.Data.Common.DbProviderFactory> and <xref:System.Data.Common.DbConnection> object by passing it the provider name in the format "*System.Data.ProviderName*" and a connection string.</span></span> <span data-ttu-id="a5459-158">메서드가 성공하면 `DbConnection` 개체가 반환되고, 오류가 발생하면 `null` (Visual Basic의 경우에는 `Nothing`)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-158">A `DbConnection` object is returned on success; `null` (`Nothing` in Visual Basic) on any error.</span></span>  
  
 <span data-ttu-id="a5459-159">이 코드는 `DbProviderFactory`를 호출하여 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-159">The code obtains the `DbProviderFactory` by calling <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>.</span></span> <span data-ttu-id="a5459-160">그러면 <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> 메서드가 <xref:System.Data.Common.DbConnection> 개체를 만들고 <xref:System.Data.Common.DbConnection.ConnectionString%2A> 속성이 연결 문자열에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5459-160">Then the <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> method creates the <xref:System.Data.Common.DbConnection> object and the <xref:System.Data.Common.DbConnection.ConnectionString%2A> property is set to the connection string.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a5459-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5459-161">See also</span></span>

- [<span data-ttu-id="a5459-162">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="a5459-162">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [<span data-ttu-id="a5459-163">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="a5459-163">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- <span data-ttu-id="a5459-164">[구성 클래스 사용](https://docs.microsoft.com/previous-versions/aspnet/ms228063(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a5459-164">[Using the Configuration Classes](https://docs.microsoft.com/previous-versions/aspnet/ms228063(v=vs.100))</span></span>
- [<span data-ttu-id="a5459-165">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a5459-165">ADO.NET Overview</span></span>](ado-net-overview.md)
