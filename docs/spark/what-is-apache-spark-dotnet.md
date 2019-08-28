---
title: Apache Spark용 .NET이란?
description: .NET 코드를 작성하는 곳이라면 어디서나 Spark를 사용하는 무료 오픈 소스 및 플랫폼 간 빅 데이터 분석 프레임워크인 .NET for Apache Spark에 대해 알아봅니다.
author: mamccrea
ms.topic: overview
ms.date: 05/06/2019
ms.openlocfilehash: e72a1fe196b4374903146fd439033d5dafb83eaf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2019
ms.locfileid: "69576890"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="65220-103">Apache Spark용 .NET이란?</span><span class="sxs-lookup"><span data-stu-id="65220-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="65220-104">[Apache Spark](https://spark.apache.org/)는 일반적으로 테라바이트나 페타바이트 데이터가 포함된 대규모 데이터 세트에 대한 분석에 사용되는 범용 분산 처리 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="65220-104">[Apache Spark](https://spark.apache.org/) is a general-purpose distributed processing engine for analytics over large data sets-typically terabytes or petabytes of data.</span></span> <span data-ttu-id="65220-105">개발자는 .NET for Apache Spark를 통해 Apache Spark에 액세스하여 이미 알고 있는 언어 지원과 함께 애플리케이션에 Spark 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-105">.NET for Apache Spark makes Apache Spark accessible for developers, bringing the power of Spark to your applications with support for languages you already know.</span></span>

<span data-ttu-id="65220-106">C# 및 F#에서 다음에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-106">With C# and F#, you can access:</span></span>

* <span data-ttu-id="65220-107">구조적 데이터 작업을 위한 Dataframe 및 SparkSQL.</span><span class="sxs-lookup"><span data-stu-id="65220-107">Dataframe and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="65220-108">스트리밍 데이터 작업을 위한 Spark 구조적 스트리밍.</span><span class="sxs-lookup"><span data-stu-id="65220-108">Spark Structured Streaming for working with streaming data.</span></span>

<span data-ttu-id="65220-109">.NET for Apache Spark는 .NET 구현에서 공통적인 .NET API의 공식 사양인 .NET Standard를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="65220-109">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="65220-110">따라서 .NET 코드를 작성하는 곳이라면 어디서나 .NET for Apache Spark를 사용할 수 있으므로 이미 .NET 개발자로 보유하고 있는 모든 지식, 기술, 코드 및 라이브러리를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-110">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="65220-111">.NET for Apache Spark는 .NET Core를 사용하여 Windows, Linux 및 macOS에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="65220-111">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="65220-112">.NET Framework를 사용하여 Windows에서도 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="65220-112">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="65220-113">Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks 및 Databricks on AWS를 비롯한 모든 주요 클라우드 공급자에 애플리케이션을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-113">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-foundation"></a><span data-ttu-id="65220-114">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="65220-114">.NET Foundation</span></span>

<span data-ttu-id="65220-115">.NET for Apache Spark 프로젝트는 [.NET Foundation](https://www.dotnetfoundation.org/)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="65220-115">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="65220-116">참여</span><span class="sxs-lookup"><span data-stu-id="65220-116">Contributions</span></span>

<span data-ttu-id="65220-117">.NET for Apache Spark 팀은 GitHub 이슈 및 끌어오기 요청에 모두 참여하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-117">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="65220-118">먼저 [기존 이슈](https://github.com/dotnet/spark/issues)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="65220-118">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="65220-119">기존 이슈를 찾을 수 없는 경우 [새 이슈를 엽니다](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="65220-119">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>
