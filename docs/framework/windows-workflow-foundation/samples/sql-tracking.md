---
title: SQL 추적
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243182"
---
# <a name="sql-tracking"></a><span data-ttu-id="49c10-102">SQL 추적</span><span class="sxs-lookup"><span data-stu-id="49c10-102">SQL tracking</span></span>

<span data-ttu-id="49c10-103">이 샘플에서는 추적 레코드를 SQL 데이터베이스에 기록하는 사용자 지정 SQL 추적 참가자를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-103">This sample demonstrates how to write a custom SQL tracking participant that writes tracking records to a SQL database.</span></span> <span data-ttu-id="49c10-104">WF(Windows 워크플로우 Foundation)는 워크플로 인스턴스 실행에 대한 가시성을 확보하기 위해 워크플로 추적을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="49c10-105">추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="49c10-106">워크플로 추적에 대한 자세한 내용은 [워크플로 추적 및 추적](../workflow-tracking-and-tracing.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="49c10-106">For more information about workflow tracking, see [Workflow Tracking and Tracing](../workflow-tracking-and-tracing.md).</span></span>

## <a name="use-the-sample"></a><span data-ttu-id="49c10-107">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="49c10-107">Use the sample</span></span>

1. <span data-ttu-id="49c10-108">SQL Server 2008 또는 SQL Server 2008 Express 이상 버전이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="49c10-109">샘플과 함께 제공되는 스크립트에서는 로컬 컴퓨터에 SQL Express 인스턴스가 사용되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="49c10-110">로컬 컴퓨터에 다른 인스턴스를 사용하고 있으면 샘플을 실행하기 전에 데이터베이스 관련 스크립트를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>

2. <span data-ttu-id="49c10-111">스크립트 디렉터리(\WF\Basic\Tracking\SqlTracking\CS\Scripts)에서 Trackingsetup.cmd를 실행하여 SQL Server 추적 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="49c10-112">이렇게 하면 TrackingSample이라는 데이터베이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-112">This creates a database called TrackingSample.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49c10-113">이 스크립트에서는 SQL Express의 기본 인스턴스를 기반으로 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="49c10-114">다른 데이터베이스 인스턴스를 기반으로 이를 설치하려면 Trackingsetup.cmd 스크립트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>

3. <span data-ttu-id="49c10-115">비주얼 스튜디오 2010에서 SqlTrackingSample.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-115">Open SqlTrackingSample.sln in Visual Studio 2010.</span></span>

4. <span data-ttu-id="49c10-116">**Ctrl**+**Shift**+**B를** 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-116">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

5. <span data-ttu-id="49c10-117">**F5** 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-117">Press **F5** to run the application.</span></span>

   <span data-ttu-id="49c10-118">브라우저 창이 열리고 애플리케이션의 디렉터리 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-118">The browser window opens and shows the directory listing for the application.</span></span>

6. <span data-ttu-id="49c10-119">브라우저에서 StockPriceService.xamlx를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-119">In the browser, click StockPriceService.xamlx.</span></span>

7. <span data-ttu-id="49c10-120">브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="49c10-121">이 주소를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-121">Copy this address.</span></span>

   <span data-ttu-id="49c10-122">로컬 서비스 WSDL 주소의 `http://localhost:65193/StockPriceService.xamlx?wsdl`예는 .</span><span class="sxs-lookup"><span data-stu-id="49c10-122">An example of the local service WSDL address is `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span></span>

8. <span data-ttu-id="49c10-123">파일 탐색기를 사용하여 WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-123">Using File Explorer, run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="49c10-124">Microsoft 비주얼 스튜디오 *10.0\Common7\IDE 디렉토리에*있습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-124">It's located in the *Microsoft Visual Studio 10.0\Common7\IDE directory*.</span></span>

9. <span data-ttu-id="49c10-125">WCF 테스트 클라이언트에서 **파일** 메뉴를 클릭하고 **서비스 추가를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="49c10-126">로컬 서비스 주소를 텍스트 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="49c10-127">**확인**을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-127">Click **OK** to close the dialog.</span></span>

10. <span data-ttu-id="49c10-128">WCF 테스트 클라이언트에서 **GetStockPrice**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="49c10-129">그러면 `GetStockPrice` 하나의 매개 변수를 가져와 값을 `Contoso` 입력하고 **호출을**클릭하는 작업이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>

11. <span data-ttu-id="49c10-130">내보낸 추적 레코드가 SQL 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="49c10-131">추적 레코드를 보려면 SQL Management Studio에서 TrackingSample 데이터베이스를 열고 테이블을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> <span data-ttu-id="49c10-132">테이블에 대해 선택 쿼리를 실행하면 해당 테이블에 저장되어 있는 추적 레코드 내의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-132">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>

   <span data-ttu-id="49c10-133">SQL Server 관리 스튜디오에 대한 자세한 내용은 [SQL Server 관리 스튜디오 소개를](/sql/ssms/sql-server-management-studio-ssms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="49c10-133">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms).</span></span> <span data-ttu-id="49c10-134">[여기에서](https://aka.ms/ssmsfullsetup)SQL 서버 관리 스튜디오를 다운로드하십시오.</span><span class="sxs-lookup"><span data-stu-id="49c10-134">Download SQL Server Management Studio [here](https://aka.ms/ssmsfullsetup).</span></span>

## <a name="uninstall-the-sample"></a><span data-ttu-id="49c10-135">샘플 제거</span><span class="sxs-lookup"><span data-stu-id="49c10-135">Uninstall the sample</span></span>

1. <span data-ttu-id="49c10-136">샘플 디렉토리에서 Trackingcleanup.cmd 스크립트를*실행합니다(\WF\Basic\Tracking\SqlTracking).*</span><span class="sxs-lookup"><span data-stu-id="49c10-136">Run theTrackingcleanup.cmd script in the sample directory (*\WF\Basic\Tracking\SqlTracking*).</span></span>

    > [!NOTE]
    > <span data-ttu-id="49c10-137">Trackingcleanup.cmd가 로컬 컴퓨터 SQL Express에서 데이터베이스를 삭제하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="49c10-138">다른 SQL Server 인스턴스를 사용하는 경우 Trackingcleanup.cmd를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49c10-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="49c10-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="49c10-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="49c10-141">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="49c10-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49c10-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a><span data-ttu-id="49c10-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49c10-143">See also</span></span>

- <span data-ttu-id="49c10-144">[AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="49c10-144">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
