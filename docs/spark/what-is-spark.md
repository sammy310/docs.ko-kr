---
title: Apache Spark란?
description: Apache Spark 및 빅 데이터 시나리오에 대해 알아봅니다.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458168"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="a4828-103">Apache Spark란?</span><span class="sxs-lookup"><span data-stu-id="a4828-103">What is Apache Spark?</span></span>

<span data-ttu-id="a4828-104">[Apache Spark](https://spark.apache.org/)는 메모리 내 처리를 지원하여 빅 데이터를 분석하는 애플리케이션의 성능을 향상시키는 오픈 소스 병렬 처리 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="a4828-105">빅 데이터 솔루션은 기존 데이터베이스에 비해 너무 크거나 복잡한 데이터를 처리하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="a4828-106">Spark는 메모리에서 대량의 데이터를 처리하므로 디스크 기반 대체 방법보다 훨씬 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="a4828-107">일반적인 빅 데이터 시나리오</span><span class="sxs-lookup"><span data-stu-id="a4828-107">Common big data scenarios</span></span>

<span data-ttu-id="a4828-108">대용량 데이터를 저장 및 처리하거나, 비정형 데이터를 변환하거나, 스트리밍 데이터를 처리해야 하는 경우 빅 데이터 아키텍처를 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="a4828-109">Spark는 여러 빅 데이터 시나리오에 사용할 수 있는 범용 분산 처리 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="a4828-110">ETL(추출, 변환 및 로드)</span><span class="sxs-lookup"><span data-stu-id="a4828-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="a4828-111">[ETL(추출, 변환 및 로드)](/azure/architecture/data-guide/relational-data/etl)은 하나 이상의 원본에서 데이터를 수집하고, 데이터를 수정하고, 데이터를 새 데이터 저장소로 이동하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="a4828-112">다음을 포함하여 데이터를 변환하는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="a4828-113">Filtering</span><span class="sxs-lookup"><span data-stu-id="a4828-113">Filtering</span></span>
* <span data-ttu-id="a4828-114">정렬</span><span class="sxs-lookup"><span data-stu-id="a4828-114">Sorting</span></span>
* <span data-ttu-id="a4828-115">집계</span><span class="sxs-lookup"><span data-stu-id="a4828-115">Aggregating</span></span>
* <span data-ttu-id="a4828-116">조인</span><span class="sxs-lookup"><span data-stu-id="a4828-116">Joining</span></span>
* <span data-ttu-id="a4828-117">정리</span><span class="sxs-lookup"><span data-stu-id="a4828-117">Cleaning</span></span>
* <span data-ttu-id="a4828-118">중복 제거</span><span class="sxs-lookup"><span data-stu-id="a4828-118">Deduplicating</span></span>
* <span data-ttu-id="a4828-119">유효성 검사 중</span><span class="sxs-lookup"><span data-stu-id="a4828-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="a4828-120">실시간 데이터 스트림 처리</span><span class="sxs-lookup"><span data-stu-id="a4828-120">Real-time data stream processing</span></span>

<span data-ttu-id="a4828-121">스트리밍 또는 실시간 데이터는 이동 중인 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="a4828-122">IoT 디바이스, 웹 로그, 클릭스트림의 원격 분석은 모두 데이터 스트리밍의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="a4828-123">실시간 데이터를 처리하여 지리 공간적 분석, 원격 모니터링 및 변칙 검색과 같은 유용한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="a4828-124">관계형 데이터와 마찬가지로 데이터를 출력 싱크로 이동하기 전에 스트리밍 데이터를 필터링, 집계 및 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="a4828-125">Apache Spark는 [Spark Streaming](https://spark.apache.org/streaming/)을 통해 [실시간 데이터 스트림 처리](/azure/architecture/data-guide/big-data/real-time-processing)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="a4828-126">일괄 처리</span><span class="sxs-lookup"><span data-stu-id="a4828-126">Batch processing</span></span>

<span data-ttu-id="a4828-127">[일괄 처리](/azure/architecture/data-guide/big-data/batch-processing)는 미사용 빅 데이터를 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="a4828-128">장기 실행 작업을 병렬로 사용하여 매우 큰 데이터 세트를 필터링, 집계 및 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="a4828-129">MLlib를 통한 기계 학습</span><span class="sxs-lookup"><span data-stu-id="a4828-129">Machine learning through MLlib</span></span>

<span data-ttu-id="a4828-130">기계 학습은 고급 분석 문제에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="a4828-131">컴퓨터는 기존 데이터를 사용하여 미래의 동작, 결과 및 추세를 예상하거나 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="a4828-132">Apache Spark의 [MLlib](https://spark.apache.org/mllib/) 기계 학습 라이브러리에는 여러 기계 학습 알고리즘과 유틸리티가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="a4828-133">GraphX를 통한 그래프 처리</span><span class="sxs-lookup"><span data-stu-id="a4828-133">Graph processing through GraphX</span></span>

<span data-ttu-id="a4828-134">그래프는 가장자리로 연결된 노드의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="a4828-135">계층적 데이터 또는 상호 연결 관계의 데이터가 있는 경우 그래프 데이터베이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="a4828-136">Apache Spark의 [GraphX](https://spark.apache.org/graphx/) API를 사용하여 이 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="a4828-137">Spark SQL을 통한 SQL 및 정형 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="a4828-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="a4828-138">정형(형식 지정된) 데이터를 사용하는 경우 [Spark SQL](https://spark.apache.org/sql/)을 사용하여 Spark 애플리케이션에서 SQL 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="a4828-139">Apache Spark 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a4828-139">Apache Spark architecture</span></span>

<span data-ttu-id="a4828-140">마스터/작업자 아키텍처를 사용하는 Apache Spark에는 드라이버, 실행기 및 클러스터 관리자의 세 가지 주요 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Apache Spark 아키텍처](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="a4828-142">드라이버</span><span class="sxs-lookup"><span data-stu-id="a4828-142">Driver</span></span>

<span data-ttu-id="a4828-143">드라이버는 C# 콘솔 앱과 같은 프로그램과 Spark 세션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="a4828-144">Spark 세션은 프로그램을 가져와서 실행기에서 처리하는 더 작은 작업으로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="a4828-145">실행자</span><span class="sxs-lookup"><span data-stu-id="a4828-145">Executors</span></span>

<span data-ttu-id="a4828-146">각 실행기 또는 작업자 노드는 드라이버로부터 작업을 받고 해당 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="a4828-147">실행기는 클러스터라고 하는 엔터티에 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="a4828-148">클러스터 관리자</span><span class="sxs-lookup"><span data-stu-id="a4828-148">Cluster manager</span></span>

<span data-ttu-id="a4828-149">클러스터 관리자는 드라이버 및 실행기 모두와 통신하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="a4828-150">리소스 할당 관리</span><span class="sxs-lookup"><span data-stu-id="a4828-150">Manage resource allocation</span></span>
* <span data-ttu-id="a4828-151">프로그램 분할 관리</span><span class="sxs-lookup"><span data-stu-id="a4828-151">Manage program division</span></span>
* <span data-ttu-id="a4828-152">프로그램 실행 관리</span><span class="sxs-lookup"><span data-stu-id="a4828-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="a4828-153">언어 지원</span><span class="sxs-lookup"><span data-stu-id="a4828-153">Language support</span></span>

<span data-ttu-id="a4828-154">Apache Spark에서 지원하는 프로그래밍 언어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="a4828-155">스칼라</span><span class="sxs-lookup"><span data-stu-id="a4828-155">Scala</span></span>
* <span data-ttu-id="a4828-156">Python</span><span class="sxs-lookup"><span data-stu-id="a4828-156">Python</span></span>
* <span data-ttu-id="a4828-157">Java</span><span class="sxs-lookup"><span data-stu-id="a4828-157">Java</span></span>
* <span data-ttu-id="a4828-158">SQL</span><span class="sxs-lookup"><span data-stu-id="a4828-158">SQL</span></span>
* <span data-ttu-id="a4828-159">R</span><span class="sxs-lookup"><span data-stu-id="a4828-159">R</span></span>
* <span data-ttu-id="a4828-160">.NET</span><span class="sxs-lookup"><span data-stu-id="a4828-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="a4828-161">Spark API</span><span class="sxs-lookup"><span data-stu-id="a4828-161">Spark APIs</span></span>

<span data-ttu-id="a4828-162">Apache Spark에서 지원하는 API는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-162">Apache Spark supports the following APIs:</span></span>

* [<span data-ttu-id="a4828-163">Spark Scala API</span><span class="sxs-lookup"><span data-stu-id="a4828-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [<span data-ttu-id="a4828-164">Spark Java API</span><span class="sxs-lookup"><span data-stu-id="a4828-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [<span data-ttu-id="a4828-165">Spark Python API</span><span class="sxs-lookup"><span data-stu-id="a4828-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [<span data-ttu-id="a4828-166">Spark R API</span><span class="sxs-lookup"><span data-stu-id="a4828-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* <span data-ttu-id="a4828-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), 기본 제공 함수</span><span class="sxs-lookup"><span data-stu-id="a4828-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4828-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a4828-168">Next steps</span></span>

<span data-ttu-id="a4828-169">.NET 애플리케이션에서 Apache Spark를 사용하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="a4828-170">Apache Spark용 .NET을 사용하면 .NET 환경과 비즈니스 논리를 갖춘 개발자는 C# 및 F#에서 빅 데이터 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4828-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a4828-171">Apache Spark용 .NET이란?</span><span class="sxs-lookup"><span data-stu-id="a4828-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
