---
title: 사용 하 여 Azure Table storage 시작F#
description: Azure Table storage 또는 Azure Cosmos DB를 사용 하 여 클라우드에 구조화 된 데이터를 저장 합니다.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 54c777acd454e4f675175b814675c185e41ad9a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086704"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="fa45b-103">Azure Table storage와 F를 사용 하 여 Azure Cosmos DB Table API 시작\#</span><span class="sxs-lookup"><span data-stu-id="fa45b-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="fa45b-104">Azure Table storage는 클라우드에 구조화 된 NoSQL 데이터를 저장 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="fa45b-105">Table storage는 스키마 없이 디자인을 사용 하 여 키/특성 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="fa45b-106">테이블 저장소는 스키마 때문에 응용 프로그램 진화에 필요에 따라 데이터에 맞게 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="fa45b-107">데이터 액세스가 빠르고 비용 효율적으로 모든 종류의 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="fa45b-108">테이블 저장소는 일반적으로 전통적인 SQL 비슷한 양의 데이터에 비해 비용이 매우 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="fa45b-109">웹 응용 프로그램, 주소록, 장치 정보 및 다른 유형의 서비스에 필요한 메타 데이터에 대 한 사용자 데이터와 같은 유연한 데이터 집합을 저장할 Table storage를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="fa45b-110">테이블의 엔터티 수를 저장할 수 있습니다 하 고 저장소 계정에는 임의 개수의 테이블을 저장소 계정의 용량 제한까지 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="fa45b-111">Azure Cosmos DB는 Azure Table storage 용으로 작성 및와 같은 프리미엄 기능이 필요한 응용 프로그램에 대 한 Table API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="fa45b-112">턴키 전역 배포</span><span class="sxs-lookup"><span data-stu-id="fa45b-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="fa45b-113">전 세계 전용된 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="fa45b-114">99 번째 백분위 수에서 1 자리 밀리초 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="fa45b-115">고가용성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="fa45b-116">자동 보조 인덱싱입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="fa45b-117">Azure Table storage 용으로 작성 된 응용 프로그램 코드 변경 없이 Table API를 사용 하 여 Azure Cosmos DB에 마이그레이션 하 고 프리미엄 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="fa45b-118">Table API는.NET, Java, Python 및 Node.js에 대 한 사용할 수 있는 클라이언트 Sdk에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="fa45b-119">자세한 내용은 [Azure Cosmos DB Table API 소개](https://docs.microsoft.com/azure/cosmos-db/table-introduction)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="fa45b-120">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="fa45b-120">About this tutorial</span></span>

<span data-ttu-id="fa45b-121">이 자습서에서는 작성 하는 방법을 보여 줍니다. F# Azure Table storage 또는 Azure Cosmos DB 테이블 API를, 만들기 및 테이블을 삭제 및 삽입, 업데이트, 삭제 및 테이블 데이터 쿼리를 포함 하 여 사용 하 여 몇 가지 일반적인 작업을 수행 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa45b-122">전제 조건</span><span class="sxs-lookup"><span data-stu-id="fa45b-122">Prerequisites</span></span>

<span data-ttu-id="fa45b-123">이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account) 하거나 [Azure Cosmos DB 계정](https://azure.microsoft.com/try/cosmosdb/)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="fa45b-124">만들기는 F# 스크립트 및 시작 F# 대화형</span><span class="sxs-lookup"><span data-stu-id="fa45b-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="fa45b-125">이 문서의 샘플에서 사용할 수는 F# 응용 프로그램 또는 F# 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="fa45b-126">만들려는 F# 스크립트를 사용 하 여 파일을 만듭니다는 `.fsx` 예를 들어 확장 `tables.fsx`에서 F# 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="fa45b-127">다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 패키지 및 참조 `WindowsAzure.Storage.dll` 를사용하여스크립트에서`#r`지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="fa45b-128">에 대해 다시 수행 `Microsoft.WindowsAzure.ConfigurationManager` Microsoft.Azure 네임 스페이스를 가져오기 위해.</span><span class="sxs-lookup"><span data-stu-id="fa45b-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="fa45b-129">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="fa45b-129">Add namespace declarations</span></span>

<span data-ttu-id="fa45b-130">다음을 추가 합니다 `open` 의 맨 위에 문을 `tables.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="fa45b-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="fa45b-131">Azure Storage 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="fa45b-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="fa45b-132">Azure Storage Table service에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="fa45b-133">Azure portal에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="fa45b-134">연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="fa45b-135">Azure Cosmos DB 연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="fa45b-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="fa45b-136">Azure Cosmos DB에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="fa45b-137">Azure portal에서 연결 문자열을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="fa45b-138">Cosmos DB 계정에 Azure portal로 이동 **설정을** > **연결 문자열**를 클릭 합니다 **복사** 기본 연결을 복사 하는 단추 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="fa45b-139">자습서의 경우 다음 예제와 같이 스크립트에서 연결 문자열을 입력:</span><span class="sxs-lookup"><span data-stu-id="fa45b-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="fa45b-140">그러나 이것이 **좋지** 실제 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="fa45b-141">저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="fa45b-142">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="fa45b-143">다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fa45b-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="fa45b-144">손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="fa45b-145">실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="fa45b-146">구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="fa45b-147">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="fa45b-148">.NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="fa45b-149">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="fa45b-149">Parse the connection string</span></span>

<span data-ttu-id="fa45b-150">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="fa45b-151">반환 된 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="fa45b-152">Table service 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="fa45b-152">Create the Table service client</span></span>

<span data-ttu-id="fa45b-153">`CloudTableClient` 클래스를 사용 하면 테이블 및 Table storage의 엔터티를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="fa45b-154">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="fa45b-155">이제 데이터를 읽어 오고 테이블 저장소에 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="fa45b-156">테이블 생성하기</span><span class="sxs-lookup"><span data-stu-id="fa45b-156">Create a table</span></span>

<span data-ttu-id="fa45b-157">이 예제에는 아직 존재 하지 않는 경우 테이블을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="fa45b-158">테이블에 엔터티 추가</span><span class="sxs-lookup"><span data-stu-id="fa45b-158">Add an entity to a table</span></span>

<span data-ttu-id="fa45b-159">상속 되는 형식에 엔터티 `TableEntity`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="fa45b-160">확장할 수 있습니다 `TableEntity` 원하는 어떤 방식으로든 형식 에서만 *해야* 매개 변수가 없는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="fa45b-161">둘 다 있는 속성만 `get` 고 `set` Azure 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="fa45b-162">엔터티의 파티션과 행 키 테이블에서 엔터티를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="fa45b-163">동일한 파티션 키를 가진 엔터티는 다른 파티션 키를 사용 하는 것 보다 더 빠르게 쿼리할 수 있지만 다양 한 파티션 키를 사용 하 여 병렬 작업 확장성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="fa45b-164">예로 `Customer` 를 사용 하는 `lastName` 파티션 키로 및 `firstName` 행 키로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="fa45b-165">이제 추가 `Customer` 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="fa45b-166">이렇게 하려면 만들기를 `TableOperation` 테이블에서 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="fa45b-167">만든이 경우에 `Insert` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="fa45b-168">엔터티 일괄 삽입</span><span class="sxs-lookup"><span data-stu-id="fa45b-168">Insert a batch of entities</span></span>

<span data-ttu-id="fa45b-169">단일 쓰기 작업을 사용 하 여 테이블에 엔터티를 일괄을 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="fa45b-170">일괄 처리 작업을 사용 하면 단일 실행에 대 한 작업을 결합 하 하지만 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="fa45b-171">업데이트를 수행할 수 있습니다, 삭제 하 고 동일한 일괄 처리 작업에서 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="fa45b-172">일괄 처리 작업을 최대 100 개의 엔터티가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="fa45b-173">일괄 처리 작업의 모든 엔터티에 동일한 파티션 키에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="fa45b-174">일괄 처리 작업에서 쿼리를 수행할 수 있지만, 일괄 처리의 유일한 작업 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="fa45b-175">두 삽입 일괄 처리 작업으로 결합 하는 일부 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="fa45b-176">파티션의 모든 엔터티 검색</span><span class="sxs-lookup"><span data-stu-id="fa45b-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="fa45b-177">테이블 파티션의 모든 엔터티를 쿼리하려면 사용을 `TableQuery` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="fa45b-178">여기에서 필터링 할 엔터티에 대 한 "Smith" 인 파티션 키.</span><span class="sxs-lookup"><span data-stu-id="fa45b-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="fa45b-179">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="fa45b-180">파티션의 엔터티 범위 검색</span><span class="sxs-lookup"><span data-stu-id="fa45b-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="fa45b-181">파티션의 모든 엔터티를 쿼리하지 않으려면 파티션 키 필터를 행 키 필터와 결합 하 여 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="fa45b-182">여기에서 두 필터를 사용 하면 "Smith" 파티션의 모든 엔터티를 가져온 행 키 (이름)로 시작 하는 문자 "M" 알파벳에서 보다 이전입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="fa45b-183">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="fa45b-184">단일 엔터티 검색</span><span class="sxs-lookup"><span data-stu-id="fa45b-184">Retrieve a single entity</span></span>

<span data-ttu-id="fa45b-185">단일 특정 엔터티를 검색 하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="fa45b-186">여기에서 사용 하 여는 `TableOperation` 고객 "Ben Smith"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="fa45b-187">컬렉션 대신 받게는 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="fa45b-188">Table service에서 단일 엔터티를 검색 하는 가장 빠른 방법은 쿼리에서 파티션 키와 행 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="fa45b-189">이제 결과 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="fa45b-190">엔터티 바꾸기</span><span class="sxs-lookup"><span data-stu-id="fa45b-190">Replace an entity</span></span>

<span data-ttu-id="fa45b-191">엔터티를 업데이트 하려면 Table service에서 검색, 엔터티 개체를 수정한 다음 변경 내용을 다시 사용해 서 Table service에 저장 된 `Replace` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="fa45b-192">이렇게 하면 작업이 실패 하는 경우, 검색 된 이후 서버에서 엔터티가 변경 되지 않은 엔터티를 서버에서 완전히 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="fa45b-193">다른 원본의 변경 내용을 실수로 덮어쓰는에서 응용 프로그램을 방지 하기 위해이 오류는입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="fa45b-194">삽입 또는 바꾸기 엔터티</span><span class="sxs-lookup"><span data-stu-id="fa45b-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="fa45b-195">경우에 따라 엔터티를 테이블에 있는지 여부를 모르는 경우</span><span class="sxs-lookup"><span data-stu-id="fa45b-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="fa45b-196">및에 저장 된 현재 값을 더 이상 필요 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="fa45b-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="fa45b-197">사용할 수 있습니다 `InsertOrReplace` 엔터티를 만들거나 해당 상태에 관계 없이 존재 하는 경우 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="fa45b-198">엔터티 속성 하위 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="fa45b-198">Query a subset of entity properties</span></span>

<span data-ttu-id="fa45b-199">테이블 쿼리 전체가 아닌 엔터티에서 일부 속성만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="fa45b-200">프로젝션 이라고 하는이 기술은 특히 큰 엔터티에 대의 쿼리 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="fa45b-201">이때 돌아가게만 전자 메일 주소를 사용 하 여 `DynamicTableEntity` 고 `EntityResolver`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="fa45b-202">이 코드는 테이블 서비스의 계정을 사용 하는 경우에 실행 되도록 프로젝션 로컬 저장소 에뮬레이터에서 지원 되지 않습니다는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="fa45b-203">페이지에서 엔터티를 비동기적으로 검색</span><span class="sxs-lookup"><span data-stu-id="fa45b-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="fa45b-204">많은 수의 엔터티를 읽는 처리할 때 검색 될 때 기다리지 않고 이러한 모든 반환 하는 경우에 분할 된 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="fa45b-205">여기서 돌아가게 결과 페이지에서 반환할 결과의 큰 집합을 기다리는 동안 실행이 차단 되지 않도록 하는 비동기 워크플로 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="fa45b-206">하면 이제이 계산 동기적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="fa45b-207">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="fa45b-207">Delete an entity</span></span>

<span data-ttu-id="fa45b-208">검색 한 후 엔터티를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="fa45b-209">엔터티 업데이트와 마찬가지로 엔터티 것을 검색 한 후 변경 된 경우 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="fa45b-210">테이블 삭제</span><span class="sxs-lookup"><span data-stu-id="fa45b-210">Delete a table</span></span>

<span data-ttu-id="fa45b-211">저장소 계정에서 테이블을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="fa45b-212">삭제 된 테이블을 삭제 후 기간에 대 한 다시 만들어야 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="fa45b-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fa45b-213">Next steps</span></span>

<span data-ttu-id="fa45b-214">이제 테이블 저장소의 기본 사항을 배웠으므로 다음 링크를 더 복잡 한 저장소 작업 및 Azure Cosmos DB Table API에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa45b-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="fa45b-215">Azure Cosmos DB Table API 소개</span><span class="sxs-lookup"><span data-stu-id="fa45b-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="fa45b-216">.NET 용 storage 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="fa45b-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="fa45b-217">Azure Storage 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="fa45b-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="fa45b-218">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="fa45b-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="fa45b-219">연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="fa45b-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="fa45b-220">.NET에서 Azure Table Storage 시작</span><span class="sxs-lookup"><span data-stu-id="fa45b-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
