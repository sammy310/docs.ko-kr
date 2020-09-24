---
title: SQL Server 인스턴스 열거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: 2966157921894356836765edee6160d8e0f3e6e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156136"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="752e9-102">SQL Server의 인스턴스 열거(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="752e9-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>

<span data-ttu-id="752e9-103">SQL Server에서 애플리케이션이 현재 네트워크 내에서 SQL Server 인스턴스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="752e9-104"><xref:System.Data.Sql.SqlDataSourceEnumerator> 클래스는 표시되는 모든 서버에 대한 정보가 포함된 <xref:System.Data.DataTable>을 제공하여 애플리케이션 개발자에게 이 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="752e9-105">이 반환된 테이블은 사용자가 새 연결을 만들려고 할 때 제공되는 목록과 일치하는 네트워크상에서 사용 가능한 서버 인스턴스의 목록을 포함하며, **Connection Properties** 대화 상자에서 사용 가능한 모든 서버가 포함된 드롭다운 목록을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="752e9-106">표시되는 결과가 항상 완전하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="752e9-107">대부분의 Windows 서비스와 마찬가지로 최소 권한으로 SQL Browser 서비스를 실행하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="752e9-108">SQL Browser 서비스와 이 서비스의 동작을 관리하는 방법에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="752e9-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="752e9-109">열거자 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="752e9-109">Retrieving an Enumerator Instance</span></span>  

 <span data-ttu-id="752e9-110">사용 가능한 SQL Server 인스턴스에 대한 정보가 포함된 테이블을 검색하려면 먼저 공유/정적 <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> 속성을 사용하여 열거자를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="752e9-111">정적 인스턴스를 검색한 후에는 사용 가능한 서버에 대한 정보가 포함된 <xref:System.Data.DataTable>을 반환하는 <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="752e9-112">메서드 호출에서 반환된 테이블에는 다음 열이 포함되어 있으며, 모든 열은 `string` 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="752e9-113">열</span><span class="sxs-lookup"><span data-stu-id="752e9-113">Column</span></span>|<span data-ttu-id="752e9-114">설명</span><span class="sxs-lookup"><span data-stu-id="752e9-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="752e9-115">**데이터 열이 추적에서 캡처되고 서버를 사용할 수 있으면**</span><span class="sxs-lookup"><span data-stu-id="752e9-115">**ServerName**</span></span>|<span data-ttu-id="752e9-116">서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-116">Name of the server.</span></span>|  
|<span data-ttu-id="752e9-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="752e9-117">**InstanceName**</span></span>|<span data-ttu-id="752e9-118">서버 인스턴스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-118">Name of the server instance.</span></span> <span data-ttu-id="752e9-119">서버를 기본 인스턴스로 실행하는 경우에는 비어있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="752e9-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="752e9-120">**IsClustered**</span></span>|<span data-ttu-id="752e9-121">서버가 클러스터의 일부인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="752e9-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="752e9-122">**Version**</span></span>|<span data-ttu-id="752e9-123">서버 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-123">Version of the server.</span></span> <span data-ttu-id="752e9-124">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="752e9-124">For example:</span></span><br /><br /> <span data-ttu-id="752e9-125">-   9.00.x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="752e9-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="752e9-126">-   10.0.xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="752e9-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="752e9-127">-   10.50.x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="752e9-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="752e9-128">-   11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="752e9-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="752e9-129">열거 제한</span><span class="sxs-lookup"><span data-stu-id="752e9-129">Enumeration Limitations</span></span>  

 <span data-ttu-id="752e9-130">사용 가능한 서버가 모두 나열될 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="752e9-131">이 목록은 제한 시간, 네트워크 트래픽과 같은 요인에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="752e9-132">이로 인해 두 번의 연속 호출에서 목록이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="752e9-133">동일한 네트워크에 있는 서버만 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="752e9-134">브로드캐스트 패킷은 일반적으로 라우터를 트래버스하지 않습니다. 즉, 나열된 서버가 표시되지 않을 수 있지만 호출에서 안정적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="752e9-135">나열된 서버에는 `IsClustered` 및 버전과 같은 추가 정보가 있을 수도 있고 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="752e9-136">이는 목록을 가져온 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="752e9-137">SQL Server 브라우저 서비스를 통해 나열된 서버에서는 Windows 인프라를 통해 찾은 정보(이름만 나열됨)보다 더 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="752e9-138">서버 열거는 완전 신뢰로 실행되는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="752e9-139">부분적으로 신뢰할 수 있는 환경에서 실행되는 어셈블리는 <xref:System.Data.SqlClient.SqlClientPermission> CAS(코드 액세스 보안) 권한이 있는 경우에도 이를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="752e9-140">SQL Server에서는 SQL Browser라고 하는 외부 Windows 서비스를 사용하여 <xref:System.Data.Sql.SqlDataSourceEnumerator>에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="752e9-141">이 서비스는 기본적으로 사용하도록 설정되어 있지만 관리자가 해제하거나 사용하지 않도록 설정하여 서버 인스턴스를 이 클래스에 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="752e9-142">예제</span><span class="sxs-lookup"><span data-stu-id="752e9-142">Example</span></span>  

 <span data-ttu-id="752e9-143">다음 콘솔 애플리케이션에서는 표시되는 모든 SQL Server 인스턴스에 대한 정보를 검색하여 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="752e9-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="752e9-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="752e9-144">See also</span></span>

- [<span data-ttu-id="752e9-145">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="752e9-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="752e9-146">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="752e9-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
