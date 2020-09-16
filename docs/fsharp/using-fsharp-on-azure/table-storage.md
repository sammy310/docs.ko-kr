---
title: F#을 사용하여 Azure Table 스토리지 시작
description: Azure Table Storage 또는 Azure Cosmos DB를 사용하여 클라우드에 구조화된 데이터를 저장합니다.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: eb25fda0bb3c658eed2f675d6ba79c689a9080a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548353"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="dd426-103">F를 사용 하 여 Azure Table storage 및 Azure Cosmos DB Table API 시작\#</span><span class="sxs-lookup"><span data-stu-id="dd426-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="dd426-104">Azure Table Storage는 클라우드에 구조화된 NoSQL 데이터를 저장하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="dd426-105">Table Storage는 스키마 없이 디자인된 키/특성 스토리지입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="dd426-106">Table Storage는 스키마가 없기 때문에 애플리케이션의 요구 사항이 변화함에 따라 데이터를 쉽게 적응시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="dd426-107">모든 종류의 애플리케이션에서 빠르고 비용 효율적으로 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="dd426-108">비슷한 양의 데이터일 때 Table Storage는 일반적으로 전통적인 SQL에 비해 비용이 매우 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="dd426-109">Table Storage를 사용하여 웹 애플리케이션의 사용자 데이터, 주소록, 디바이스 정보 및 서비스에 필요한 다른 유형의 메타데이터와 같은 유연한 데이터 세트을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="dd426-110">테이블에 저장할 수 있는 엔터티 수에는 제한이 없으며, 스토리지 계정에 포함할 수 있는 테이블의 수에는 스토리지 계정의 최대 용량 한도까지 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="dd426-111">Azure Cosmos DB는 Azure Table storage 용으로 작성 되었으며 다음과 같은 프리미엄 기능이 필요한 응용 프로그램에 대 한 Table API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="dd426-112">턴키 전역 배포</span><span class="sxs-lookup"><span data-stu-id="dd426-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="dd426-113">전 세계적인 전용 처리량</span><span class="sxs-lookup"><span data-stu-id="dd426-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="dd426-114">99번째 백분위수에서 1자리 밀리초 대기 시간</span><span class="sxs-lookup"><span data-stu-id="dd426-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="dd426-115">보장된 고가용성</span><span class="sxs-lookup"><span data-stu-id="dd426-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="dd426-116">자동 보조 인덱싱.</span><span class="sxs-lookup"><span data-stu-id="dd426-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="dd426-117">Azure Table Storage에 대해 작성된 애플리케이션은 코드를 변경하지 않고 테이블 API를 사용하여 Azure Cosmos DB로 마이그레이션할 수 있으며 프리미엄 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="dd426-118">테이블 API에는 .NET, Java, Python 및 Node.js에 사용할 수 있는 클라이언트 SDK가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="dd426-119">자세한 내용은 [Azure Cosmos DB Table API 소개](/azure/cosmos-db/table-introduction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd426-119">For more information, see [Introduction to Azure Cosmos DB Table API](/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="dd426-120">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="dd426-120">About this tutorial</span></span>

<span data-ttu-id="dd426-121">이 자습서에서는 테이블 만들기 및 삭제, 테이블 데이터 삽입, 업데이트, 삭제 및 쿼리를 비롯 하 여 Azure Table storage 또는 Azure Cosmos DB Table API를 사용 하 여 몇 가지 일반적인 작업을 수행 하는 F # 코드를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd426-122">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dd426-122">Prerequisites</span></span>

<span data-ttu-id="dd426-123">이 가이드를 사용 하려면 먼저 [Azure storage 계정](/azure/storage/storage-create-storage-account) 또는 [Azure Cosmos DB 계정을](https://azure.microsoft.com/try/cosmosdb/)만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="dd426-124">F # 스크립트를 만들고 F# 대화형를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="dd426-125">이 문서의 샘플은 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="dd426-126">F # 스크립트를 만들려면 `.fsx` `tables.fsx` f # 개발 환경에서 확장명을 사용 하 여 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="dd426-127">그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 패키지를 설치 하 `WindowsAzure.Storage` 고 `WindowsAzure.Storage.dll` 지시어를 사용 하 여 스크립트에 참조 합니다 `#r` .</span><span class="sxs-lookup"><span data-stu-id="dd426-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="dd426-128">Microsoft Azure 네임 스페이스를 얻기 위해 다시이 작업을 수행 `Microsoft.WindowsAzure.ConfigurationManager` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="dd426-129">네임스페이스 선언 추가</span><span class="sxs-lookup"><span data-stu-id="dd426-129">Add namespace declarations</span></span>

<span data-ttu-id="dd426-130">`tables.fsx` 파일 맨 위에 다음 `open` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="dd426-131">Azure Storage 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="dd426-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="dd426-132">Azure Storage Table service에 연결 하는 경우이 자습서에 대 한 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="dd426-133">Azure Portal에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="dd426-134">연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd426-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="dd426-135">Azure Cosmos DB 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="dd426-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="dd426-136">Azure Cosmos DB에 연결 하는 경우이 자습서에 대 한 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="dd426-137">Azure Portal에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="dd426-138">Azure Portal의 Cosmos DB 계정에서 **설정**  >  **연결 문자열**로 이동 하 고 **복사** 단추를 클릭 하 여 기본 연결 문자열을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span>

<span data-ttu-id="dd426-139">자습서의 경우 다음 예제와 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="dd426-140">그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="dd426-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="dd426-141">스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="dd426-142">항상 스토리지 계정 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="dd426-143">다른 사용자에게 배포하거나 하드 코딩하거나 다른 사람이 액세스할 수 있는 일반 텍스트 파일에 저장하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="dd426-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="dd426-144">손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="dd426-145">실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="dd426-146">구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="dd426-147">Azure 구성 관리자 사용은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="dd426-148">.NET Framework의 형식과 같은 API를 사용할 수도 있습니다 `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="dd426-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="dd426-149">연결 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="dd426-149">Parse the connection string</span></span>

<span data-ttu-id="dd426-150">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="dd426-151">그러면이 반환 `CloudStorageAccount` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="dd426-152">Table service 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="dd426-152">Create the Table service client</span></span>

<span data-ttu-id="dd426-153">`CloudTableClient`클래스를 사용 하면 테이블 저장소에서 테이블과 엔터티를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="dd426-154">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="dd426-155">이제 데이터를 읽어 오고 Table Storage에 데이터를 기록하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="dd426-156">테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="dd426-156">Create a table</span></span>

<span data-ttu-id="dd426-157">이 예제에서는 테이블이 없는 경우 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="dd426-158">테이블에 엔터티 추가</span><span class="sxs-lookup"><span data-stu-id="dd426-158">Add an entity to a table</span></span>

<span data-ttu-id="dd426-159">엔터티에는에서 상속 되는 형식이 있어야 `TableEntity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="dd426-160">원하는 방식으로 확장할 수 `TableEntity` 있지만 형식에 매개 변수가 없는 생성자가 *있어야 합니다* .</span><span class="sxs-lookup"><span data-stu-id="dd426-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="dd426-161">및를 모두 포함 하는 속성만 `get` `set` Azure 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="dd426-162">엔터티의 파티션 및 행 키는 테이블에서 엔터티를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="dd426-163">동일한 파티션 키를 가진 엔터티는 다른 파티션 키를 가진 엔터티보다 더 빨리 쿼리할 수 있지만 다양한 파티션 키를 사용하면 병렬 작업 확장성이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="dd426-164">다음은를 `Customer` `lastName` 파티션 키로 사용 하 고을 행 키로 사용 하는의 예입니다 `firstName` .</span><span class="sxs-lookup"><span data-stu-id="dd426-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="dd426-165">이제 `Customer` 테이블에를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="dd426-166">이렇게 하려면 `TableOperation` 테이블에서 실행 되는를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="dd426-167">이 경우 작업을 만듭니다 `Insert` .</span><span class="sxs-lookup"><span data-stu-id="dd426-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="dd426-168">엔터티 일괄 삽입</span><span class="sxs-lookup"><span data-stu-id="dd426-168">Insert a batch of entities</span></span>

<span data-ttu-id="dd426-169">단일 쓰기 작업을 사용 하 여 엔터티 일괄 처리를 테이블에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="dd426-170">일괄 처리 작업을 통해 작업을 단일 실행으로 결합할 수 있지만 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="dd426-171">동일한 일괄 작업에서 업데이트, 삭제 및 삽입을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="dd426-172">일괄 처리 작업에는 최대 100 개의 엔터티가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="dd426-173">일괄 처리 작업의 모든 엔터티에는 동일한 파티션 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="dd426-174">일괄 처리 작업에서 쿼리를 수행할 수 있지만 일괄 처리에서 유일한 작업 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="dd426-175">다음은 두 개의 삽입을 일괄 처리 작업으로 결합 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="dd426-176">파티션의 모든 엔터티 검색</span><span class="sxs-lookup"><span data-stu-id="dd426-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="dd426-177">테이블에서 파티션의 모든 엔터티를 쿼리하려면 `TableQuery` 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="dd426-178">여기서 "Smith"가 파티션 키인 엔터티를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="dd426-179">이제 결과를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="dd426-180">파티션의 엔터티 범위 검색</span><span class="sxs-lookup"><span data-stu-id="dd426-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="dd426-181">파티션의 모든 엔터티를 쿼리하지 않으려면 파티션 키 필터를 행 키 필터와 결합하여 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="dd426-182">여기서는 두 개의 필터를 사용 하 여 행 키 (이름)가 알파벳의 "M" 보다 이전 문자로 시작 하는 "Smith" 파티션의 모든 엔터티를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="dd426-183">이제 결과를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="dd426-184">단일 엔터티 검색</span><span class="sxs-lookup"><span data-stu-id="dd426-184">Retrieve a single entity</span></span>

<span data-ttu-id="dd426-185">단일 특정 엔터티를 검색하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="dd426-186">여기서는를 사용 하 여 `TableOperation` 고객 "이혜준 씨 Smith"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="dd426-187">컬렉션 대신를 반환 `Customer` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="dd426-188">쿼리에서 파티션 키와 행 키를 모두 지정 하는 것은 Table service에서 단일 엔터티를 검색 하는 가장 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="dd426-189">이제 결과를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="dd426-190">엔터티 바꾸기</span><span class="sxs-lookup"><span data-stu-id="dd426-190">Replace an entity</span></span>

<span data-ttu-id="dd426-191">엔터티를 업데이트 하려면 Table service에서 엔터티를 검색 하 고 엔터티 개체를 수정한 다음 작업을 사용 하 여 변경 내용을 Table service에 다시 저장 합니다 `Replace` .</span><span class="sxs-lookup"><span data-stu-id="dd426-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="dd426-192">이렇게 하면 서버의 엔터티가 검색 된 후 변경 되어 작업이 실패 하는 경우를 제외 하 고 서버에서 엔터티가 완전히 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="dd426-193">이 오류는 응용 프로그램에서 실수로 다른 원본의 변경 내용을 덮어쓰는 것을 방지 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="dd426-194">엔터티 삽입 또는 바꾸기</span><span class="sxs-lookup"><span data-stu-id="dd426-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="dd426-195">경우에 따라 엔터티가 테이블에 있는지 여부를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="dd426-196">이 경우 저장 된 현재 값이 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="dd426-197">`InsertOrReplace`를 사용 하 여 엔터티를 만들거나, 상태에 관계 없이 엔터티를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="dd426-198">엔터티 속성 하위 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="dd426-198">Query a subset of entity properties</span></span>

<span data-ttu-id="dd426-199">테이블 쿼리는 엔터티의 일부 속성만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="dd426-200">프로젝션 이라고 하는이 기술은 특히 규모가 많은 엔터티의 경우 쿼리 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="dd426-201">여기서는 및를 사용 하 여 전자 메일 주소만 반환 `DynamicTableEntity` `EntityResolver` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="dd426-202">로컬 스토리지 에뮬레이터에서는 프로젝션이 지원되지 않으므로 이 코드는 Table service의 계정을 사용하는 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="dd426-203">페이지에서 엔터티를 비동기적으로 검색</span><span class="sxs-lookup"><span data-stu-id="dd426-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="dd426-204">다 수의 엔터티를 읽고 모두 반환 될 때까지 기다리지 않고 검색할 때 처리 하려면 분할 된 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="dd426-205">여기서는 대량 결과 집합이 반환 될 때까지 대기 하는 동안 실행이 차단 되지 않도록 비동기 워크플로를 사용 하 여 페이지에서 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="dd426-206">이제이 계산을 동기적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="dd426-207">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="dd426-207">Delete an entity</span></span>

<span data-ttu-id="dd426-208">엔터티를 검색 한 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="dd426-209">엔터티를 업데이트 하는 것 처럼 엔터티가 검색 된 후 변경 된 경우에는이 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="dd426-210">테이블 삭제</span><span class="sxs-lookup"><span data-stu-id="dd426-210">Delete a table</span></span>

<span data-ttu-id="dd426-211">저장소 계정에서 테이블을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="dd426-212">삭제된 테이블은 삭제 후 일정 기간 동안 다시 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd426-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="dd426-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dd426-213">Next steps</span></span>

<span data-ttu-id="dd426-214">이제 테이블 저장소의 기본 사항을 배웠으므로 다음 링크를 따라 좀 더 복잡 한 저장소 작업 및 Azure Cosmos DB Table API에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dd426-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="dd426-215">Azure Cosmos DB Table API 소개</span><span class="sxs-lookup"><span data-stu-id="dd426-215">Introduction to Azure Cosmos DB Table API</span></span>](/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="dd426-216">Storage Client Library for .NET 참조</span><span class="sxs-lookup"><span data-stu-id="dd426-216">Storage Client Library for .NET reference</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="dd426-217">Azure Storage 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="dd426-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="dd426-218">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="dd426-218">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="dd426-219">연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="dd426-219">Configuring Connection Strings</span></span>](/azure/storage/common/storage-configure-connection-string)
