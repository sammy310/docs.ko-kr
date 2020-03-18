---
title: Apache Spark용 .NET이란?
description: .NET 코드를 작성하는 곳이라면 어디서나 Spark를 사용하는 무료 오픈 소스 및 플랫폼 간 빅 데이터 분석 프레임워크인 .NET for Apache Spark에 대해 알아봅니다.
author: mamccrea
ms.topic: overview
ms.date: 10/15/2019
ms.openlocfilehash: 12fccd478cedaccf455043feb3afa7b12221bf0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458194"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="9e31c-103">Apache Spark용 .NET이란?</span><span class="sxs-lookup"><span data-stu-id="9e31c-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="9e31c-104">[Apache Spark](what-is-spark.md)는 대규모 데이터 세트(일반적으로 테라바이트 또는 페타바이트 데이터)에 대한 분석에 사용되는 범용 분산 처리 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-104">[Apache Spark](what-is-spark.md) is a general-purpose distributed processing engine for analytics over large data sets - typically terabytes or petabytes of data.</span></span> <span data-ttu-id="9e31c-105">인기 있는 오픈 소스 빅 데이터 분석 프레임워크에 대한 무료 오픈 소스 및 플랫폼 간 .NET 지원인 .NET for Apache Spark를 통해 이제 이미 알고 있는 언어를 사용하여 빅 데이터 애플리케이션에 Apache Spark의 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-105">With .NET for Apache Spark, the free, open-source, and cross-platform .NET Support for the popular open-source big data analytics framework, you can now add the power of Apache Spark to your big data applications using languages you already know.</span></span>

## <a name="why-choose-net-for-apache-spark"></a><span data-ttu-id="9e31c-106">.NET for Apache Spark를 선택하는 이유</span><span class="sxs-lookup"><span data-stu-id="9e31c-106">Why choose .NET for Apache Spark?</span></span>

<span data-ttu-id="9e31c-107">.NET for Apache Spark에서는 개발자가 .NET 환경 또는 코드 기반을 가진 빅 데이터 분석 환경에 참여할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-107">.NET for Apache Spark empowers developers with .NET experience or code bases to participate in the world of big data analytics.</span></span> <span data-ttu-id="9e31c-108">.NET for Apache Spark에서는 C# 및 F#의 Spark를 사용하기 위한 고성능 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-108">.NET for Apache Spark provides high performance APIs for using Spark from C# and F#.</span></span> <span data-ttu-id="9e31c-109">C# 및 F#에서 다음에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-109">With C# and F#, you can access:</span></span>

* <span data-ttu-id="9e31c-110">구조적 데이터 작업을 위한 DataFrame 및 SparkSQL.</span><span class="sxs-lookup"><span data-stu-id="9e31c-110">DataFrame and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="9e31c-111">스트리밍 데이터 작업을 위한 Spark 구조적 스트리밍.</span><span class="sxs-lookup"><span data-stu-id="9e31c-111">Spark Structured Streaming for working with streaming data.</span></span>
* <span data-ttu-id="9e31c-112">SQL 구문으로 쿼리 작성을 위한 Spark SQL.</span><span class="sxs-lookup"><span data-stu-id="9e31c-112">Spark SQL for writing queries with SQL syntax.</span></span>
* <span data-ttu-id="9e31c-113">더 빠른 학습 및 예측을 위한 기계 학습 통합(즉, [ML.NET](https://dot.net/ml)과 함께 Apache Spark에 .NET 사용).</span><span class="sxs-lookup"><span data-stu-id="9e31c-113">Machine learning integration for faster training and prediction (that is, use .NET for Apache Spark alongside [ML.NET](https://dot.net/ml)).</span></span>

<span data-ttu-id="9e31c-114">.NET for Apache Spark는 .NET 구현에서 공통적인 .NET API의 공식 사양인 .NET Standard를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-114">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="9e31c-115">따라서 .NET 코드를 작성하는 곳이라면 어디서나 .NET for Apache Spark를 사용할 수 있으므로 이미 .NET 개발자로 보유하고 있는 모든 지식, 기술, 코드 및 라이브러리를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-115">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="9e31c-116">.NET for Apache Spark는 .NET Core를 사용하여 Windows, Linux 및 macOS에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-116">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="9e31c-117">.NET Framework를 사용하여 Windows에서도 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-117">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="9e31c-118">Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks 및 Databricks on AWS를 비롯한 모든 주요 클라우드 공급자에 애플리케이션을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-118">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-for-apache-spark-architecture"></a><span data-ttu-id="9e31c-119">.NET for Apache Spark 아키텍처</span><span class="sxs-lookup"><span data-stu-id="9e31c-119">.NET for Apache Spark architecture</span></span>

<span data-ttu-id="9e31c-120">Spark에 대한 C#/F# 언어 바인딩은 더 쉬운 확장성을 제공하는 새로운 Spark interop 계층에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-120">The C#/ F# language binding to Spark is written on a new Spark interop layer which offers easier extensibility.</span></span> <span data-ttu-id="9e31c-121">이 새로운 Spark interop 계층은 언어 확장에 대한 모범 사례를 사용하여 작성되었으며 interop 및 성능에 맞게 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-121">This new layer of Spark interop was written using the best practices for language extension and optimizes for interop and performance.</span></span> <span data-ttu-id="9e31c-122">장기적으로 이 확장성은 Spark의 다른 언어에 대한 지원을 추가하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-122">Long term, this extensibility can be used for adding support for other languages in Spark.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e31c-123">![.NET for Apache Spark 아키텍처](media/dotnet-spark-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="9e31c-123">![.NET for Apache Spark architecture](media/dotnet-spark-architecture.png)</span></span>

<span data-ttu-id="9e31c-124">[제안](https://issues.apache.org/jira/browse/SPARK-26257)에서 Spark 언어 확장에 대한 interop 지원에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-124">You can learn about interop support for Spark language extensions from [the proposal](https://issues.apache.org/jira/browse/SPARK-26257).</span></span>

## <a name="net-for-apache-spark-performance"></a><span data-ttu-id="9e31c-125">.NET for Apache Spark 성능</span><span class="sxs-lookup"><span data-stu-id="9e31c-125">.NET for Apache Spark performance</span></span>

<span data-ttu-id="9e31c-126">[TPC-H 벤치마크](http://www.tpc.org/tpch/)를 사용하여 Python 및 Scala와 비교했을 때 .NET for Apache Spark는 대부분의 경우 잘 작동하며, 사용자 정의 함수 성능이 중요할 경우 Python보다 2배 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-126">When compared against Python and Scala using the [TPC-H benchmark](http://www.tpc.org/tpch/), .NET for Apache Spark performs well in most cases and is 2x faster than Python when user-defined function performance is critical.</span></span> <span data-ttu-id="9e31c-127">벤치마크 성능 개선을 위해 지속적으로 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-127">There is an ongoing effort to improve and benchmark performance.</span></span>

<span data-ttu-id="9e31c-128">사용자 고유의 벤치마킹을 수행하려면 [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark)에서 사용 가능한 벤치마크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e31c-128">To do your own benchmarking, see the benchmarks available on the [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span></span>

## <a name="net-for-apache-spark-roadmap"></a><span data-ttu-id="9e31c-129">.NET for Apache Spark 로드맵</span><span class="sxs-lookup"><span data-stu-id="9e31c-129">.NET for Apache Spark roadmap</span></span>

<span data-ttu-id="9e31c-130">공식 [.NET for Apache Spark 로드맵](https://github.com/dotnet/spark/blob/master/ROADMAP.md)에서 단기 및 장기 요금제에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-130">Learn about short term and long term plans from the official [.NET for Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span></span>

## <a name="net-foundation"></a><span data-ttu-id="9e31c-131">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="9e31c-131">.NET Foundation</span></span>

<span data-ttu-id="9e31c-132">.NET for Apache Spark 프로젝트는 [.NET Foundation](https://www.dotnetfoundation.org/)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-132">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="9e31c-133">참여</span><span class="sxs-lookup"><span data-stu-id="9e31c-133">Contributions</span></span>

<span data-ttu-id="9e31c-134">.NET for Apache Spark 팀은 GitHub 이슈 및 끌어오기 요청에 모두 참여하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-134">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="9e31c-135">먼저 [기존 이슈](https://github.com/dotnet/spark/issues)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-135">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="9e31c-136">기존 이슈를 찾을 수 없는 경우 [새 이슈를 엽니다](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="9e31c-136">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e31c-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e31c-137">Next steps</span></span>

<span data-ttu-id="9e31c-138">.NET for Apache Spark를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9e31c-138">Try .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9e31c-139">자습서: .NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="9e31c-139">Tutorial: Get started with .NET for Apache Spark</span></span>](./tutorials/get-started.md)
