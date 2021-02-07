---
description: '자세히 알아보기: ASP.NET 응용 프로그램의 SqlDependency'
title: ASP.NET 애플리케이션에서 SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 686586af834884f97ff8e62fdc792b3cdc23f507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767026"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="36b67-103">ASP.NET 애플리케이션에서 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="36b67-103">SqlDependency in an ASP.NET Application</span></span>

<span data-ttu-id="36b67-104">이 섹션의 예제는 ASP.NET <xref:System.Web.Caching.SqlCacheDependency> 개체를 활용하여 <xref:System.Data.SqlClient.SqlDependency>를 간접적으로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-104">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="36b67-105"><xref:System.Web.Caching.SqlCacheDependency> 개체는 <xref:System.Data.SqlClient.SqlDependency>를 사용하여 알림을 수신하고 캐시를 올바르게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-105">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36b67-106">이 샘플 코드에서는 [쿼리 알림을 사용 하도록 설정](enabling-query-notifications.md)하는 스크립트를 실행 하 여 쿼리 알림을 사용 하도록 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-106">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="36b67-107">샘플 애플리케이션 정보</span><span class="sxs-lookup"><span data-stu-id="36b67-107">About the Sample Application</span></span>  

 <span data-ttu-id="36b67-108">애플리케이션 예제에서는 단일 ASP.NET 웹 페이지를 사용하여 **AdventureWorks** SQL Server 데이터베이스의 제품 정보를 <xref:System.Web.UI.WebControls.GridView> 컨트롤에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-108">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="36b67-109">페이지가 로드되면 코드는 <xref:System.Web.UI.WebControls.Label> 컨트롤에 현재 시간을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-109">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="36b67-110">그런 다음 <xref:System.Web.Caching.SqlCacheDependency> 개체를 정의하고 최대 3분 동안 캐시 데이터를 저장하도록 <xref:System.Web.Caching.Cache> 개체의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-110">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="36b67-111">그런 다음 코드는 데이터베이스에 연결하고 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-111">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="36b67-112">페이지가 로드되고 애플리케이션이 실행 중인 경우 ASP.NET은 캐시에서 데이터를 검색하여 페이지의 시간이 변경되지 않는다는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-112">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="36b67-113">모니터링되는 데이터가 변경되면 ASP.NET은 캐시를 무효화하고 `GridView` 컨트롤을 새로운 데이터로 다시 채우고 `Label` 컨트롤에 표시되는 시간을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-113">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="36b67-114">샘플 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="36b67-114">Creating the Sample Application</span></span>  

 <span data-ttu-id="36b67-115">샘플 애플리케이션을 만들고 실행하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-115">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="36b67-116">새 ASP.NET 웹 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="36b67-116">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="36b67-117">Default.aspx 페이지에 <xref:System.Web.UI.WebControls.Label> 및 <xref:System.Web.UI.WebControls.GridView> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-117">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="36b67-118">페이지의 클래스 모듈을 열고 다음 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-118">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="36b67-119">페이지의 `Page_Load` 이벤트에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-119">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="36b67-120">`GetConnectionString` 및 `GetSQL`의 두 가지 도우미 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-120">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="36b67-121">정의된 연결 문자열은 통합 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-121">The connection string defined uses integrated security.</span></span> <span data-ttu-id="36b67-122">사용 중인 계정에 필요한 데이터베이스 권한이 있는지, 그리고 **AdventureWorks** 샘플 데이터베이스에서 알림을 사용했는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-122">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="36b67-123">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="36b67-123">Testing the Application</span></span>  

 <span data-ttu-id="36b67-124">애플리케이션은 웹 양식에 표시된 데이터를 캐시하고 활동이 없으면 3분마다 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="36b67-125">데이터베이스가 변경되면 즉시 캐시를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="36b67-126">Visual Studio에서 애플리케이션을 실행합니다. 그러면 페이지가 브라우저에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="36b67-127">표시된 캐시 새로 고침 시간은 캐시를 마지막으로 새로 고친 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="36b67-128">3분간 기다렸다가 페이지를 새로 고쳐 다시 게시 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="36b67-129">페이지에 표시된 시간이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="36b67-130">3분 이내에 페이지를 새로 고치면 페이지에 표시되는 시간이 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="36b67-131">이제 Transact-SQL UPDATE 명령을 사용하여 데이터베이스의 데이터를 업데이트하고 페이지를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="36b67-132">이제 표시된 시간은 캐시가 데이터베이스의 새 데이터로 새로 고쳐졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="36b67-133">캐시를 업데이트하는 경우에도 페이지에 표시되는 시간은 포스트백 이벤트가 발생할 때까지 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a><span data-ttu-id="36b67-134">SQL 종속성을 사용한 분산 캐시 동기화</span><span class="sxs-lookup"><span data-stu-id="36b67-134">Distributed cache synchronization using SQL Dependency</span></span>

<span data-ttu-id="36b67-135">[NCache](https://www.alachisoft.com/ncache) 와 같은 일부 타사 분산 캐시는 sql [종속성](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html)을 사용 하 여 sql database 및 캐시를 동기화 할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b67-135">Some of the third-party distributed caches such as [NCache](https://www.alachisoft.com/ncache) provide support to synchronize the SQL database and cache using [SQL Dependency](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html).</span></span> <span data-ttu-id="36b67-136">소스 코드 구현에 대 한 자세한 내용 및 예제는 [Distributed CACHE SQL 종속성 샘플](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36b67-136">For more information and an example source code implementation, see [Distributed cache SQL Dependency sample](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).</span></span>

## <a name="see-also"></a><span data-ttu-id="36b67-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36b67-137">See also</span></span>

- [<span data-ttu-id="36b67-138">SQL Server의 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="36b67-138">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="36b67-139">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="36b67-139">ADO.NET Overview</span></span>](../ado-net-overview.md)
