---
title: 빠른 시작(WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 49d11556d3703331b4cdf5bf83a69f6b15bca8ed
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881988"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="8dd25-102">빠른 시작(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8dd25-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="8dd25-103">이 빠른 시작을 사용 하면 WCF Data Services에 익숙해질 수 및 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 일련의 항목을 지 원하는 작업의 [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="8dd25-104">학습할 내용</span><span class="sxs-lookup"><span data-stu-id="8dd25-104">What you'll learn</span></span>

<span data-ttu-id="8dd25-105">이 빠른 시작에서 첫 번째 작업에는 Northwind 샘플 데이터베이스에서 OData 피드에 노출 하는 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="8dd25-106">이후 항목에서는 OData 액세스는 웹 브라우저를 사용 하 여 피드 및 Windows Presentation Foundation (WPF) 클라이언트 라이브러리를 사용 하 여 OData를 사용 하는 클라이언트 응용 프로그램 피드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8dd25-107">전제 조건</span><span class="sxs-lookup"><span data-stu-id="8dd25-107">Prerequisites</span></span>

<span data-ttu-id="8dd25-108">이 퀵 스타트를 수행하려면 다음 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="8dd25-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8dd25-109">Visual Studio</span></span>

- <span data-ttu-id="8dd25-110">SQL Server의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-110">An instance of SQL Server.</span></span> <span data-ttu-id="8dd25-111">여기에 SQL Server Express 기본 설치의 일부로 또는 Visual Studio 2015에 포함 되는 **데이터 저장소 및 처리** Visual Studio 2017에서 워크 로드.</span><span class="sxs-lookup"><span data-stu-id="8dd25-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="8dd25-112">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="8dd25-112">The Northwind sample database.</span></span> <span data-ttu-id="8dd25-113">이 샘플 데이터베이스를 다운로드하려면 [SQL Server용 샘플 데이터베이스](https://go.microsoft.com/fwlink/?linkid=24758)다운로드 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dd25-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="8dd25-114">WCF data services 퀵 스타트 작업</span><span class="sxs-lookup"><span data-stu-id="8dd25-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="8dd25-115">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="8dd25-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="8dd25-116">ASP.NET 응용 프로그램과 데이터 모델을 정의하고, 데이터 서비스를 만들고, 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="8dd25-117">웹 브라우저에서 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="8dd25-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="8dd25-118">Visual Studio에서 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 노출된 피드로 전송하여 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="8dd25-119">.NET Framework 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="8dd25-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="8dd25-120">OData 피드를 사용할 Windows 컨트롤에 데이터 바인딩, 변경, 바인딩된 컨트롤에서 데이터를 WPF 앱을 만들고 변경 내용을 데이터 서비스로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd25-121">완성된 퀵 스타트 버전의 프로젝트 파일은 [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) 페이지에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd25-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8dd25-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8dd25-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8dd25-123">빠른 시작 시작</span><span class="sxs-lookup"><span data-stu-id="8dd25-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="8dd25-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="8dd25-124">See also</span></span>

- [<span data-ttu-id="8dd25-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8dd25-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
