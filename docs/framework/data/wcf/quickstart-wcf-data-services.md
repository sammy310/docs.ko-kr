---
title: 빠른 시작(WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121219"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="17ce5-102">빠른 시작(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="17ce5-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="17ce5-103">이 빠른 시작을 통해 시작 항목의 항목을 지원하는 일련의 작업을 통해 WCF 데이터 서비스 및 [Getting Started](getting-started-with-wcf-data-services.md)OData(개방형 데이터 프로토콜)에 익숙해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="17ce5-104">학습할 내용</span><span class="sxs-lookup"><span data-stu-id="17ce5-104">What you'll learn</span></span>

<span data-ttu-id="17ce5-105">이 빠른 시작의 첫 번째 작업은 Northwind 샘플 데이터베이스에서 OData 피드를 노출하는 데이터 서비스를 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="17ce5-106">이후 항목에서는 웹 브라우저를 사용하여 OData 피드에 액세스하고 클라이언트 라이브러리를 사용하여 OData 피드를 사용하는 WPF(Windows 프레젠테이션 기반) 클라이언트 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17ce5-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="17ce5-107">Prerequisites</span></span>

<span data-ttu-id="17ce5-108">이 빠른 시작을 완료하려면 다음 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="17ce5-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="17ce5-109">Visual Studio</span></span>

- <span data-ttu-id="17ce5-110">SQL 서버의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-110">An instance of SQL Server.</span></span> <span data-ttu-id="17ce5-111">여기에는 Visual Studio 2015의 기본 설치에 포함되는 SQL Server Express 또는 Visual Studio 2017 이상의 **데이터 저장소 및 처리** 워크로드의 일부로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="17ce5-112">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="17ce5-112">The Northwind sample database.</span></span> <span data-ttu-id="17ce5-113">데이터베이스를 설치하려면 [노스윈드에서](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)Transact-SQL 스크립트를 실행하고 Microsoft SQL Server에 대한 펍 샘플 데이터베이스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="17ce5-114">WCF 데이터 서비스 빠른 시작 작업</span><span class="sxs-lookup"><span data-stu-id="17ce5-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="17ce5-115">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="17ce5-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="17ce5-116">ASP.NET 애플리케이션과 데이터 모델을 정의하고, 데이터 서비스를 만들고, 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="17ce5-117">웹 브라우저에서 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="17ce5-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="17ce5-118">Visual Studio에서 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 노출된 피드로 전송하여 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="17ce5-119">.NET 프레임워크 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="17ce5-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="17ce5-120">WPF 앱을 만들어 OData 피드를 사용하고, 데이터를 Windows 컨트롤에 바인딩하고, 바인딩된 컨트롤의 데이터를 변경한 다음 변경 내용을 데이터 서비스로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="17ce5-121">완료된 버전의 퀵스타트에서 프로젝트 파일을 [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ce5-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="17ce5-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="17ce5-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="17ce5-123">빠른 시작 시작</span><span class="sxs-lookup"><span data-stu-id="17ce5-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="17ce5-124">참조</span><span class="sxs-lookup"><span data-stu-id="17ce5-124">See also</span></span>

- [<span data-ttu-id="17ce5-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="17ce5-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
