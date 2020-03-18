---
title: 클라우드 네이티브 애플리케이션의 탄력적 검색
description: 클라우드 네이티브 응용 프로그램에 탄력적 검색 기능을 추가하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141291"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="f0ba5-103">클라우드 네이티브 앱의 탄력적 검색</span><span class="sxs-lookup"><span data-stu-id="f0ba5-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="f0ba5-104">Elasticsearch는 분산 검색 및 분석 시스템으로 다양한 유형의 데이터에 걸쳐 복잡한 검색 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="f0ba5-105">그것은 오픈 소스널리 인기.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-105">It's open source and widely popular.</span></span> <span data-ttu-id="f0ba5-106">다음 회사가 Elasticsearch를 응용 프로그램에 통합하는 방법을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="f0ba5-107">전체 텍스트 및 증분 (입력으로 검색) 검색에 대한 [위키 백과.](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="f0ba5-108">[GitHub를](https://www.elastic.co/customers/github) 사용하여 8백만 개 이상의 코드 리포지토리를 인덱싱하고 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="f0ba5-109">컨테이너 라이브러리를 검색 가능한 으로 만들기 위한 [Docker입니다.](https://www.elastic.co/customers/docker)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="f0ba5-110">Elasticsearch는 [아파치 루센](https://lucene.apache.org/core/) 전체 텍스트 검색 엔진 위에 내장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="f0ba5-111">Lucene은 고성능 문서 인덱싱 및 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="f0ba5-112">페이지를 키워드에 매핑하는 대신 책 끝에 있는 용어집처럼 페이지에 키워드를 매핑하는 역인덱싱 스키마를 사용하여 데이터를 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="f0ba5-113">Lucene은 강력한 쿼리 구문 기능을 가지고 있으며 다음을 통해 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="f0ba5-114">용어 (전체 단어)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-114">Term (a full word)</span></span>
- <span data-ttu-id="f0ba5-115">접두사(단어로 시작)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="f0ba5-116">와일드카드("\*또는 "?" 필터 사용)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="f0ba5-117">구(문서의 텍스트 시퀀스)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="f0ba5-118">부울 값(쿼리를 결합하는 복잡한 검색)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="f0ba5-119">루센은 검색을 위해 낮은 수준의 배관을 제공하지만 Elasticsearch는 루센 위에 있는 서버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="f0ba5-120">Elasticsearch는 Lucene의 인덱싱 및 검색 기능에 액세스하는 RESTful API를 포함하여 작업 루센을 단순화하는 높은 수준의 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="f0ba5-121">또한 대규모 확장성, 내결함성 및 고가용성이 가능한 분산 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="f0ba5-122">복잡한 검색 요구 사항이 있는 대규모 클라우드 네이티브 응용 프로그램의 경우 Elasticsearch를 Azure에서 관리되는 서비스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="f0ba5-123">Microsoft Azure 마켓플레이스에는 개발자가 Azure에서 Elasticsearch 클러스터를 배포하는 데 사용할 수 있는 미리 구성된 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="f0ba5-124">Microsoft Azure 마켓플레이스에서 개발자는 빌드된 미리 구성된 템플릿을 사용하여 Azure에 Elasticsearch 클러스터를 신속하게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="f0ba5-125">Azure 관리 오퍼링을 사용하여 최대 50개의 데이터 노드, 20개의 조정 노드 및 3개의 전용 마스터 노드를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="f0ba5-126">요약</span><span class="sxs-lookup"><span data-stu-id="f0ba5-126">Summary</span></span>

<span data-ttu-id="f0ba5-127">이 장에서는 클라우드 네이티브 시스템의 데이터에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="f0ba5-128">모놀리식 애플리케이션의 데이터 스토리지와 클라우드 네이티브 시스템의 데이터 스토리지 패턴을 대조하는 것으로 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="f0ba5-129">서비스 간 쿼리, 분산 트랜잭션 및 대량 시스템을 처리하기 위한 패턴을 포함하여 클라우드 네이티브 시스템에서 구현된 데이터 패턴을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="f0ba5-130">SQL을 NoSQL 데이터와 대조했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="f0ba5-131">Microsoft 중심 및 오픈 소스 옵션을 모두 포함하는 Azure에서 사용할 수 있는 데이터 저장소 옵션을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="f0ba5-132">마지막으로 클라우드 네이티브 응용 프로그램에서 캐싱 및 Elasticsearch에 대해 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ba5-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="f0ba5-133">참조</span><span class="sxs-lookup"><span data-stu-id="f0ba5-133">References</span></span>

- [<span data-ttu-id="f0ba5-134">CQRS(명령 및 쿼리 책임 분리) 패턴</span><span class="sxs-lookup"><span data-stu-id="f0ba5-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="f0ba5-135">이벤트 소싱 패턴</span><span class="sxs-lookup"><span data-stu-id="f0ba5-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="f0ba5-136">RDBMSs vs. NoSQL 데이터베이스: 개요</span><span class="sxs-lookup"><span data-stu-id="f0ba5-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="f0ba5-137">CAP 정리에서 RDBMS 파티션이 관용적이지 않은 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f0ba5-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="f0ba5-138">구체화된 뷰</span><span class="sxs-lookup"><span data-stu-id="f0ba5-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="f0ba5-139">오픈 소스 데이터베이스에 대해 알아야 할 모든 것</span><span class="sxs-lookup"><span data-stu-id="f0ba5-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="f0ba5-140">보상 트랜잭션 패턴</span><span class="sxs-lookup"><span data-stu-id="f0ba5-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="f0ba5-141">사가 무늬</span><span class="sxs-lookup"><span data-stu-id="f0ba5-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="f0ba5-142">사가 패턴 | 마이크로 서비스를 사용하여 비즈니스 트랜잭션을 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="f0ba5-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="f0ba5-143">보상 트랜잭션 패턴</span><span class="sxs-lookup"><span data-stu-id="f0ba5-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="f0ba5-144">9볼 뒤처지다: 코스모스 DB 일관성 수준 설명</span><span class="sxs-lookup"><span data-stu-id="f0ba5-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="f0ba5-145">다양한 유형의 NoSQL 데이터베이스 파트 II 탐색</span><span class="sxs-lookup"><span data-stu-id="f0ba5-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="f0ba5-146">RDBMS, NoSQL 및 NewSQL 데이터베이스에서. 존 라이언과의 인터뷰</span><span class="sxs-lookup"><span data-stu-id="f0ba5-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="f0ba5-147">SQL 대 NoSQL 대 NewSQL: 전체 비교</span><span class="sxs-lookup"><span data-stu-id="f0ba5-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="f0ba5-148">DASH: Kubernetes-네이티브 데이터베이스의 네 가지 속성</span><span class="sxs-lookup"><span data-stu-id="f0ba5-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="f0ba5-149">바퀴벌레DB</span><span class="sxs-lookup"><span data-stu-id="f0ba5-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="f0ba5-150">티DB</span><span class="sxs-lookup"><span data-stu-id="f0ba5-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="f0ba5-151">유가바이트DB</span><span class="sxs-lookup"><span data-stu-id="f0ba5-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="f0ba5-152">비트 (주)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="f0ba5-153">Elasticsearch: 최선의 가이드</span><span class="sxs-lookup"><span data-stu-id="f0ba5-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="f0ba5-154">아파치 루센 소개</span><span class="sxs-lookup"><span data-stu-id="f0ba5-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="f0ba5-155">[이전](azure-caching.md)
>[다음](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="f0ba5-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
