---
title: SQL Server의 인스턴스 열거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: c59db5869ed848071611cdbf985b45dc59790d69
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979991"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="f6e8c-102">SQL Server의 인스턴스 열거(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f6e8c-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="f6e8c-103">SQL Server를 사용 하면 응용 프로그램이 현재 네트워크 내에서 SQL Server 인스턴스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="f6e8c-104"><xref:System.Data.Sql.SqlDataSourceEnumerator> 클래스에서는 애플리케이션 개발자에게 이 정보를 노출시켜 표시되는 모든 서버에 대한 정보가 포함된 <xref:System.Data.DataTable>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="f6e8c-105">이 반환 된 테이블에는 사용자가 새 연결을 만들려고 할 때 제공 된 목록과 일치 하는 네트워크에서 사용할 수 있는 서버 인스턴스 목록이 포함 되어 있으며, **연결 속성** 대화 상자에서 사용 가능한 모든 서버를 포함 하는 드롭다운 목록이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="f6e8c-106">표시되는 결과가 항상 완전하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6e8c-107">대부분의 Windows 서비스와 마찬가지로, SQL Browser 서비스도 최소 권한으로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="f6e8c-108">SQL 브라우저 서비스와 이 서비스의 동작을 관리하는 방법에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="f6e8c-109">열거자 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="f6e8c-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="f6e8c-110">사용 가능한 SQL Server 인스턴스에 대한 정보가 포함된 테이블을 검색하려면 먼저 공유/정적 <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> 속성을 사용하여 열거자를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="f6e8c-111">정적 인스턴스를 검색했으면 <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> 메서드를 호출할 수 있습니다. 이 메서드는 사용 가능한 서버의 정보가 포함된 <xref:System.Data.DataTable>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="f6e8c-112">메서드 호출을 통해 반환된 테이블에는 다음 열이 포함되며, 모든 열에는 `string` 값이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="f6e8c-113">열</span><span class="sxs-lookup"><span data-stu-id="f6e8c-113">Column</span></span>|<span data-ttu-id="f6e8c-114">설명</span><span class="sxs-lookup"><span data-stu-id="f6e8c-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f6e8c-115">**데이터 열이 추적에서 캡처되고 서버를 사용할 수 있으면**</span><span class="sxs-lookup"><span data-stu-id="f6e8c-115">**ServerName**</span></span>|<span data-ttu-id="f6e8c-116">서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-116">Name of the server.</span></span>|  
|<span data-ttu-id="f6e8c-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="f6e8c-117">**InstanceName**</span></span>|<span data-ttu-id="f6e8c-118">서버 인스턴스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-118">Name of the server instance.</span></span> <span data-ttu-id="f6e8c-119">서버가 기본 인스턴스로 실행 중인 경우에는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="f6e8c-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="f6e8c-120">**IsClustered**</span></span>|<span data-ttu-id="f6e8c-121">서버가 클러스터의 일부인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="f6e8c-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="f6e8c-122">**Version**</span></span>|<span data-ttu-id="f6e8c-123">서버의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-123">Version of the server.</span></span> <span data-ttu-id="f6e8c-124">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="f6e8c-124">For example:</span></span><br /><br /> <span data-ttu-id="f6e8c-125">-9.00 (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="f6e8c-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="f6e8c-126">-10.0. xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="f6e8c-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="f6e8c-127">-10.50 (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="f6e8c-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="f6e8c-128">-   11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="f6e8c-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="f6e8c-129">열거 제한</span><span class="sxs-lookup"><span data-stu-id="f6e8c-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="f6e8c-130">사용 가능한 모든 서버가 나열되거나 나열되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="f6e8c-131">이 목록은 시간 제한 및 네트워크 트래픽 등의 요인에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="f6e8c-132">따라서 두 개를 연속해서 호출해도 목록이 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="f6e8c-133">동일한 네트워크의 서버만 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="f6e8c-134">브로드캐스트 패킷은 일반적으로 라우터를 순회하지 않기 때문에 나열된 서버를 표시하지 않을 수는 있지만 여러 호출에서 안정적입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="f6e8c-135">나열된 서버는 `IsClustered` 및 버전 등의 추가 정보를 제공하거나 제공하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="f6e8c-136">제공 여부는 목록을 가져온 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="f6e8c-137">SLQ Server 브라우저 서비스를 통해 나열된 서버에서는 Windows 인프라에서 찾은 정보(이름)보다 더 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6e8c-138">서버 열거는 완전 신뢰로 실행되는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="f6e8c-139">부분적으로 신뢰할 수 있는 환경에서 실행되는 어셈블리는 <xref:System.Data.SqlClient.SqlClientPermission> CAS(코드 액세스 보안) 권한을 가지고 있더라도 서버 열거를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="f6e8c-140">SQL Server SQL Browser 이라는 외부 Windows 서비스를 사용 하 여 <xref:System.Data.Sql.SqlDataSourceEnumerator>에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="f6e8c-141">이 서비스는 기본적으로 사용할 수 있지만 관리자는 이 서비스의 설정을 해제하거나 비활성화하여 이 클래스에 서버 인스턴스를 노출시키지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6e8c-142">예</span><span class="sxs-lookup"><span data-stu-id="f6e8c-142">Example</span></span>  
 <span data-ttu-id="f6e8c-143">다음 콘솔 애플리케이션에서는 표시되는 모든 SQL Server 인스턴스에 대한 정보를 검색하여 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e8c-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
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
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
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
  
## <a name="see-also"></a><span data-ttu-id="f6e8c-144">참조</span><span class="sxs-lookup"><span data-stu-id="f6e8c-144">See also</span></span>

- [<span data-ttu-id="f6e8c-145">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6e8c-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="f6e8c-146">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f6e8c-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
