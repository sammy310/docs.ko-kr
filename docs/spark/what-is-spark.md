---
title: Apache Spark란?
description: Apache Spark 및 빅 데이터 시나리오에 대해 알아봅니다.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458168"
---
# <a name="what-is-apache-spark"></a>Apache Spark란?

[Apache Spark](https://spark.apache.org/)는 메모리 내 처리를 지원하여 빅 데이터를 분석하는 애플리케이션의 성능을 향상시키는 오픈 소스 병렬 처리 프레임워크입니다. 빅 데이터 솔루션은 기존 데이터베이스에 비해 너무 크거나 복잡한 데이터를 처리하도록 설계되었습니다. Spark는 메모리에서 대량의 데이터를 처리하므로 디스크 기반 대체 방법보다 훨씬 빠릅니다.

## <a name="common-big-data-scenarios"></a>일반적인 빅 데이터 시나리오

대용량 데이터를 저장 및 처리하거나, 비정형 데이터를 변환하거나, 스트리밍 데이터를 처리해야 하는 경우 빅 데이터 아키텍처를 고려할 수 있습니다. Spark는 여러 빅 데이터 시나리오에 사용할 수 있는 범용 분산 처리 엔진입니다.

### <a name="extract-transform-and-load-etl"></a>ETL(추출, 변환 및 로드)

[ETL(추출, 변환 및 로드)](/azure/architecture/data-guide/relational-data/etl)은 하나 이상의 원본에서 데이터를 수집하고, 데이터를 수정하고, 데이터를 새 데이터 저장소로 이동하는 프로세스입니다. 다음을 포함하여 데이터를 변환하는 몇 가지 방법이 있습니다.

* 필터링
* 정렬
* 집계
* 조인
* 정리
* 중복 제거
* 유효성 검사 중

### <a name="real-time-data-stream-processing"></a>실시간 데이터 스트림 처리

스트리밍 또는 실시간 데이터는 이동 중인 데이터입니다. IoT 디바이스, 웹 로그, 클릭스트림의 원격 분석은 모두 데이터 스트리밍의 예입니다. 실시간 데이터를 처리하여 지리 공간적 분석, 원격 모니터링 및 변칙 검색과 같은 유용한 정보를 제공할 수 있습니다. 관계형 데이터와 마찬가지로 데이터를 출력 싱크로 이동하기 전에 스트리밍 데이터를 필터링, 집계 및 준비할 수 있습니다. Apache Spark는 [Spark Streaming](https://spark.apache.org/streaming/)을 통해 [실시간 데이터 스트림 처리](/azure/architecture/data-guide/big-data/real-time-processing)를 지원합니다.

### <a name="batch-processing"></a>일괄 처리

[일괄 처리](/azure/architecture/data-guide/big-data/batch-processing)는 미사용 빅 데이터를 처리하는 것입니다. 장기 실행 작업을 병렬로 사용하여 매우 큰 데이터 세트를 필터링, 집계 및 준비할 수 있습니다.

### <a name="machine-learning-through-mllib"></a>MLlib를 통한 기계 학습

기계 학습은 고급 분석 문제에 사용됩니다. 컴퓨터는 기존 데이터를 사용하여 미래의 동작, 결과 및 추세를 예상하거나 예측할 수 있습니다. Apache Spark의 [MLlib](https://spark.apache.org/mllib/) 기계 학습 라이브러리에는 여러 기계 학습 알고리즘과 유틸리티가 포함되어 있습니다.

### <a name="graph-processing-through-graphx"></a>GraphX를 통한 그래프 처리

그래프는 가장자리로 연결된 노드의 컬렉션입니다. 계층적 데이터 또는 상호 연결 관계의 데이터가 있는 경우 그래프 데이터베이스를 사용할 수 있습니다. Apache Spark의 [GraphX](https://spark.apache.org/graphx/) API를 사용하여 이 데이터를 처리할 수 있습니다.

### <a name="sql-and-structured-data-processing-with-spark-sql"></a>Spark SQL을 통한 SQL 및 정형 데이터 처리

정형(형식 지정된) 데이터를 사용하는 경우 [Spark SQL](https://spark.apache.org/sql/)을 사용하여 Spark 애플리케이션에서 SQL 쿼리를 사용할 수 있습니다.

## <a name="apache-spark-architecture"></a>Apache Spark 아키텍처

마스터/작업자 아키텍처를 사용하는 Apache Spark에는 드라이버, 실행기 및 클러스터 관리자의 세 가지 주요 구성 요소가 있습니다.

![Apache Spark 아키텍처](media/spark-architecture.png)

### <a name="driver"></a>드라이버

드라이버는 C# 콘솔 앱과 같은 프로그램과 Spark 세션으로 구성됩니다. Spark 세션은 프로그램을 가져와서 실행기에서 처리하는 더 작은 작업으로 분할됩니다.

### <a name="executors"></a>실행자

각 실행기 또는 작업자 노드는 드라이버로부터 작업을 받고 해당 작업을 실행합니다. 실행기는 클러스터라고 하는 엔터티에 상주합니다.

### <a name="cluster-manager"></a>클러스터 관리자

클러스터 관리자는 드라이버 및 실행기 모두와 통신하여 다음을 수행합니다.

* 리소스 할당 관리
* 프로그램 분할 관리
* 프로그램 실행 관리

## <a name="language-support"></a>언어 지원

Apache Spark에서 지원하는 프로그래밍 언어는 다음과 같습니다.

* 스칼라
* Python
* Java
* SQL
* R
* .NET

## <a name="spark-apis"></a>Spark API

Apache Spark에서 지원하는 API는 다음과 같습니다.

* [Spark Scala API](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [Spark Java API](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [Spark Python API](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [Spark R API](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), 기본 제공 함수

## <a name="next-steps"></a>다음 단계

.NET 애플리케이션에서 Apache Spark를 사용하는 방법에 대해 알아봅니다. Apache Spark용 .NET을 사용하면 .NET 환경과 비즈니스 논리를 갖춘 개발자는 C# 및 F#에서 빅 데이터 쿼리를 작성할 수 있습니다.
> [!div class="nextstepaction"]
> [Apache Spark용 .NET이란?](what-is-apache-spark-dotnet.md)
