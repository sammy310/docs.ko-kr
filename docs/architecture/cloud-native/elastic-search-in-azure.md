---
title: 클라우드 네이티브 응용 프로그램의 Elasticsearch
description: 클라우드 네이티브 응용 프로그램에 탄력적 검색 기능을 추가 하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 6ea237eddc89a8c6843d6b34b05b1b71515a99b6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795040"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="01f67-103">클라우드 네이티브 앱의 Elasticsearch</span><span class="sxs-lookup"><span data-stu-id="01f67-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="01f67-104">Elasticsearch는 다양 한 유형의 데이터에서 복잡 한 검색 기능을 사용할 수 있도록 하는 분산 검색 및 분석 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="01f67-105">오픈 소스 이며 널리 사용 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-105">It's open source and widely popular.</span></span> <span data-ttu-id="01f67-106">다음 회사에서 Elasticsearch를 응용 프로그램에 통합 하는 방법을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="01f67-107">전체 텍스트 및 증분 (입력 시 검색) 검색을 위한 [위키백과](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) .</span><span class="sxs-lookup"><span data-stu-id="01f67-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="01f67-108">800만 개 이상의 코드 리포지토리를 인덱싱 및 노출 하는 [GitHub](https://www.elastic.co/customers/github) 입니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="01f67-109">컨테이너 라이브러리를 검색 가능 하 게 만들기 위한 [Docker](https://www.elastic.co/customers/docker) .</span><span class="sxs-lookup"><span data-stu-id="01f67-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="01f67-110">Elasticsearch는 [Apache Lucene](https://lucene.apache.org/core/) 전체 텍스트 검색 엔진 위에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="01f67-111">Lucene은 고성능 문서 인덱싱 및 쿼리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="01f67-112">반전 된 인덱싱 체계를 사용 하 여 데이터를 인덱싱합니다 .이는 페이지를 키워드로 매핑하는 대신 책의 끝에 있는 용어와 마찬가지로 키워드를 페이지에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="01f67-113">Lucene은 강력한 쿼리 구문 기능을 제공 하며 다음을 통해 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="01f67-114">Term (전체 단어)</span><span class="sxs-lookup"><span data-stu-id="01f67-114">Term (a full word)</span></span> 
- <span data-ttu-id="01f67-115">Prefix (시작 단어)</span><span class="sxs-lookup"><span data-stu-id="01f67-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="01f67-116">와일드 카드 ("\*" 또는 "?" 필터 사용)</span><span class="sxs-lookup"><span data-stu-id="01f67-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="01f67-117">구 (문서의 텍스트 시퀀스)</span><span class="sxs-lookup"><span data-stu-id="01f67-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="01f67-118">부울 값 (쿼리를 결합 하는 복잡 한 검색)</span><span class="sxs-lookup"><span data-stu-id="01f67-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="01f67-119">Lucene은 검색을 위해 낮은 수준의 통로를 제공 하지만, Elasticsearch는 Lucene 위에 있는 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="01f67-120">Elasticsearch는 Lucene의 인덱싱 및 검색 기능에 액세스 하는 RESTful API를 포함 하 여 작업 Lucene을 간소화 하는 고급 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="01f67-121">또한 대규모 확장성, 내결함성 및 고가용성을 지 원하는 분산 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="01f67-122">복잡 한 검색 요구 사항이 있는 대규모 클라우드 네이티브 응용 프로그램의 경우 Elasticsearch는 Azure에서 관리 서비스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="01f67-123">Microsoft Azure Marketplace는 개발자가 Azure에서 Elasticsearch 클러스터를 배포 하는 데 사용할 수 있는 미리 구성 된 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="01f67-124">Microsoft Azure Marketplace에서 개발자는 미리 구성 된 템플릿을 사용 하 여 Azure에서 Elasticsearch 클러스터를 신속 하 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="01f67-125">Azure에서 관리 하는 제품을 사용 하 여 최대 50 개의 데이터 노드, 20 개의 조정 노드 및 3 개의 전용 마스터 노드를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="01f67-126">요약</span><span class="sxs-lookup"><span data-stu-id="01f67-126">Summary</span></span>

<span data-ttu-id="01f67-127">이 장에서는 클라우드 네이티브 시스템의 데이터를 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="01f67-128">모놀리식 응용 프로그램의 데이터 저장소를 클라우드 네이티브 시스템의 데이터 저장 패턴으로 대조 하 여 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="01f67-129">서비스 간 쿼리, 분산 트랜잭션 및 대용량 시스템을 처리 하는 패턴을 포함 하 여 클라우드 네이티브 시스템에서 구현 된 데이터 패턴을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="01f67-130">SQL에서 NoSQL 데이터를 대조 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="01f67-131">Microsoft에서는 Microsoft 중심 및 오픈 소스 옵션을 모두 포함 하는 Azure에서 사용할 수 있는 데이터 저장소 옵션을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="01f67-132">마지막으로, 클라우드 네이티브 응용 프로그램에서 캐싱과 Elasticsearch에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="01f67-133">참조</span><span class="sxs-lookup"><span data-stu-id="01f67-133">References</span></span>

- [<span data-ttu-id="01f67-134">명령과 쿼리의 역할 분리 (CQRS) 패턴</span><span class="sxs-lookup"><span data-stu-id="01f67-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="01f67-135">이벤트 소싱 패턴</span><span class="sxs-lookup"><span data-stu-id="01f67-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="01f67-136">Rdbms 및 NoSQL 데이터베이스: 개요</span><span class="sxs-lookup"><span data-stu-id="01f67-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="01f67-137">CAP 정리에서 RDBMS 파티션 사용이 허용 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="01f67-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="01f67-138">구체화 된 뷰</span><span class="sxs-lookup"><span data-stu-id="01f67-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="01f67-139">오픈 소스 데이터베이스에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f67-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="01f67-140">보상 트랜잭션 패턴</span><span class="sxs-lookup"><span data-stu-id="01f67-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="01f67-141">Saga 패턴</span><span class="sxs-lookup"><span data-stu-id="01f67-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="01f67-142">Saga 패턴 | 마이크로 서비스를 사용 하 여 비즈니스 트랜잭션을 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="01f67-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="01f67-143">보상 트랜잭션 패턴</span><span class="sxs-lookup"><span data-stu-id="01f67-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="01f67-144">9-구슬 가져오기: Cosmos DB 일관성 수준 설명</span><span class="sxs-lookup"><span data-stu-id="01f67-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="01f67-145">여러 종류의 NoSQL 데이터베이스 탐색 파트 II</span><span class="sxs-lookup"><span data-stu-id="01f67-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="01f67-146">RDBMS, NoSQL 및 NewSQL 데이터베이스에서 John Ryan로 인터뷰</span><span class="sxs-lookup"><span data-stu-id="01f67-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="01f67-147">SQL vs NoSQL 및 NewSQL: 전체 비교</span><span class="sxs-lookup"><span data-stu-id="01f67-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="01f67-148">대시: Kubernetes 데이터베이스의 네 가지 속성</span><span class="sxs-lookup"><span data-stu-id="01f67-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="01f67-149">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="01f67-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="01f67-150">TiDB</span><span class="sxs-lookup"><span data-stu-id="01f67-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="01f67-151">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="01f67-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="01f67-152">Vitess</span><span class="sxs-lookup"><span data-stu-id="01f67-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="01f67-153">Elasticsearch: 결정적인 가이드</span><span class="sxs-lookup"><span data-stu-id="01f67-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="01f67-154">Apache Lucene 소개</span><span class="sxs-lookup"><span data-stu-id="01f67-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="01f67-155">[이전](azure-caching.md)
>[다음](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="01f67-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
