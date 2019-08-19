---
title: Apache Spark용 .NET이란?
description: .NET 코드를 작성 하는 모든 곳에서 Spark를 사용 하는 무료 오픈 소스 및 플랫폼 간 빅 데이터 분석 프레임 워크인 Apache Spark 용 .NET에 대해 알아보세요.
author: mamccrea
ms.topic: overview
ms.date: 05/06/2019
ms.openlocfilehash: e72a1fe196b4374903146fd439033d5dafb83eaf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2019
ms.locfileid: "69576890"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="39aeb-103">Apache Spark용 .NET이란?</span><span class="sxs-lookup"><span data-stu-id="39aeb-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="39aeb-104">[Apache Spark](https://spark.apache.org/) 은 일반적으로 테라바이트 또는 페타바이트의 데이터 집합에 대 한 분석을 위한 범용 분산 처리 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-104">[Apache Spark](https://spark.apache.org/) is a general-purpose distributed processing engine for analytics over large data sets-typically terabytes or petabytes of data.</span></span> <span data-ttu-id="39aeb-105">Apache Spark 용 .NET은 개발자가 Apache Spark 액세스할 수 있도록 하 여 이미 알고 있는 언어를 지 원하는 응용 프로그램에 대 한 Spark의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-105">.NET for Apache Spark makes Apache Spark accessible for developers, bringing the power of Spark to your applications with support for languages you already know.</span></span>

<span data-ttu-id="39aeb-106">및 C# F#를 사용 하 여 다음에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-106">With C# and F#, you can access:</span></span>

* <span data-ttu-id="39aeb-107">구조화 된 데이터로 작업 하기 위한 데이터 프레임 및 SparkSQL.</span><span class="sxs-lookup"><span data-stu-id="39aeb-107">Dataframe and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="39aeb-108">스트리밍 데이터를 사용 하기 위한 Spark 구조적 스트리밍입니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-108">Spark Structured Streaming for working with streaming data.</span></span>

<span data-ttu-id="39aeb-109">Apache Spark 용 .NET은 .NET 구현에서 공통적으로 사용 되는 .NET Api의 공식 사양과 .NET Standard를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-109">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="39aeb-110">즉, .net 코드를 작성 하는 모든 곳에서 Apache Spark .net을 사용 하 여 .net 개발자로 서 이미 보유 한 모든 기술 자료, 기술, 코드 및 라이브러리를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-110">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="39aeb-111">Apache Spark 용 .NET은 .NET Core를 사용 하 여 Windows, Linux 및 macOS에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-111">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="39aeb-112">또한 .NET Framework를 사용 하 여 Windows에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-112">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="39aeb-113">Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, AWS의 Databricks를 비롯 한 모든 주요 클라우드 공급자에 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-113">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-foundation"></a><span data-ttu-id="39aeb-114">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="39aeb-114">.NET Foundation</span></span>

<span data-ttu-id="39aeb-115">Apache Spark 용 .NET 프로젝트는 [.Net Foundation](https://www.dotnetfoundation.org/)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-115">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="39aeb-116">물을</span><span class="sxs-lookup"><span data-stu-id="39aeb-116">Contributions</span></span>

<span data-ttu-id="39aeb-117">Apache Spark 용 .NET 팀은 GitHub 문제와 끌어오기 요청 모두에 기여를 장려 합니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-117">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="39aeb-118">먼저 [기존 문제](https://github.com/dotnet/spark/issues)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="39aeb-118">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="39aeb-119">기존 문제를 찾을 수 없는 경우 [새 문제를 엽니다](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="39aeb-119">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>
