---
title: Apache Spark용 .NET이란?
description: .NET 코드를 작성하는 곳이라면 어디서나 Spark를 사용하는 무료 오픈 소스 및 플랫폼 간 빅 데이터 분석 프레임워크인 .NET for Apache Spark에 대해 알아봅니다.
author: mamccrea
ms.topic: overview
ms.date: 10/09/2020
ms.openlocfilehash: 2c743cf7f88d857fb87aed123bd687c353fd8b84
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955358"
---
# <a name="what-is-net-for-apache-spark"></a>Apache Spark용 .NET이란?

[Apache Spark](what-is-spark.md)는 대규모 데이터 세트(일반적으로 테라바이트 또는 페타바이트 데이터)에 대한 분석에 사용되는 범용 분산 처리 엔진입니다. 인기 있는 오픈 소스 빅 데이터 분석 프레임워크에 대한 무료 오픈 소스 및 플랫폼 간 .NET 지원인 .NET for Apache Spark를 통해 이제 이미 알고 있는 언어를 사용하여 빅 데이터 애플리케이션에 Apache Spark의 기능을 추가할 수 있습니다.

## <a name="why-choose-net-for-apache-spark"></a>.NET for Apache Spark를 선택하는 이유

.NET for Apache Spark에서는 개발자가 .NET 환경 또는 코드 기반을 가진 빅 데이터 분석 환경에 참여할 수 있도록 합니다. .NET for Apache Spark에서는 C# 및 F#의 Spark를 사용하기 위한 고성능 API를 제공합니다. C# 및 F#에서 다음에 액세스할 수 있습니다.

* 구조적 데이터 작업을 위한 DataFrame 및 SparkSQL.
* 스트리밍 데이터 작업을 위한 Spark 구조적 스트리밍.
* SQL 구문으로 쿼리 작성을 위한 Spark SQL.
* 더 빠른 학습 및 예측을 위한 기계 학습 통합(즉, [ML.NET](https://dot.net/ml)과 함께 Apache Spark에 .NET 사용).

.NET for Apache Spark는 .NET 구현에서 공통적인 .NET API의 공식 사양인 .NET Standard를 준수합니다. 따라서 .NET 코드를 작성하는 곳이라면 어디서나 .NET for Apache Spark를 사용할 수 있으므로 이미 .NET 개발자로 보유하고 있는 모든 지식, 기술, 코드 및 라이브러리를 다시 사용할 수 있습니다.

.NET for Apache Spark는 .NET Core를 사용하여 Windows, Linux 및 macOS에서 실행됩니다. .NET Framework를 사용하여 Windows에서도 실행됩니다. Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks 및 Databricks on AWS를 비롯한 모든 주요 클라우드 공급자에 애플리케이션을 배포할 수 있습니다.

## <a name="net-for-apache-spark-architecture"></a>.NET for Apache Spark 아키텍처

Spark에 대한 C#/F# 언어 바인딩은 더 쉬운 확장성을 제공하는 새로운 Spark interop 계층에 기록됩니다. 이 새로운 Spark interop 계층은 언어 확장에 대한 모범 사례를 사용하여 작성되었으며 interop 및 성능에 맞게 최적화되었습니다. 장기적으로 이 확장성은 Spark의 다른 언어에 대한 지원을 추가하는 데 사용될 수 있습니다.

> [!div class="mx-imgBorder"]
> ![.NET for Apache Spark 아키텍처](media/dotnet-spark-architecture.png)

[제안](https://issues.apache.org/jira/browse/SPARK-26257)에서 Spark 언어 확장에 대한 interop 지원에 대해 알아볼 수 있습니다.

## <a name="net-for-apache-spark-performance"></a>.NET for Apache Spark 성능

[TPC-H 벤치마크](http://www.tpc.org/tpch/)를 사용하여 Python 및 Scala와 비교했을 때 .NET for Apache Spark는 대부분의 경우 잘 작동하며, 사용자 정의 함수 성능이 중요할 경우 Python보다 2배 더 빠릅니다. 벤치마크 성능 개선을 위해 지속적으로 노력하고 있습니다.

사용자 고유의 벤치마킹을 수행하려면 [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark)에서 사용 가능한 벤치마크를 참조하세요.

## <a name="net-for-apache-spark-roadmap"></a>.NET for Apache Spark 로드맵

공식 [.NET for Apache Spark 로드맵](https://github.com/dotnet/spark/blob/master/ROADMAP.md)에서 단기 및 장기 요금제에 대해 알아봅니다.

## <a name="net-foundation"></a>.NET Foundation

.NET for Apache Spark 프로젝트는 [.NET Foundation](https://www.dotnetfoundation.org/)의 일부입니다.

## <a name="contributions"></a>참여

.NET for Apache Spark 팀은 GitHub 이슈 및 끌어오기 요청에 모두 참여하는 것이 좋습니다. 먼저 [기존 이슈](https://github.com/dotnet/spark/issues)를 찾습니다. 기존 이슈를 찾을 수 없는 경우 [새 이슈를 엽니다](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).

## <a name="next-steps"></a>다음 단계

.NET for Apache Spark를 사용해 보세요.
> [!div class="nextstepaction"]
> [자습서: .NET for Apache Spark 시작](./tutorials/get-started.md)
