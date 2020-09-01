---
title: 클라우드 네이티브 응용 프로그램의 Elasticsearch
description: 클라우드 네이티브 응용 프로그램에 탄력적 검색 기능을 추가 하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 70d1925d6b8c7bbe515ee4f178513dc61212ebce
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271804"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>클라우드 네이티브 앱의 Elasticsearch

Elasticsearch는 다양 한 유형의 데이터에서 복잡 한 검색 기능을 사용할 수 있도록 하는 분산 검색 및 분석 시스템입니다. 오픈 소스 이며 널리 사용 되 고 있습니다. 다음 회사에서 Elasticsearch를 응용 프로그램에 통합 하는 방법을 고려 합니다.

- 전체 텍스트 및 증분 (입력 시 검색) 검색을 위한 [위키백과](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) .
- 800만 개 이상의 코드 리포지토리를 인덱싱 및 노출 하는 [GitHub](https://www.elastic.co/customers/github) 입니다.  
- 컨테이너 라이브러리를 검색 가능 하 게 만들기 위한 [Docker](https://www.elastic.co/customers/docker) .

Elasticsearch는 [Apache Lucene](https://lucene.apache.org/core/) 전체 텍스트 검색 엔진 위에 빌드됩니다. Lucene은 고성능 문서 인덱싱 및 쿼리를 제공 합니다. 반전 된 인덱싱 체계를 사용 하 여 데이터를 인덱싱합니다 .이는 페이지를 키워드로 매핑하는 대신 책의 끝에 있는 용어와 마찬가지로 키워드를 페이지에 매핑합니다. Lucene은 강력한 쿼리 구문 기능을 제공 하며 다음을 통해 데이터를 쿼리할 수 있습니다.

- Term (전체 단어)
- Prefix (시작 단어)
- 와일드 카드 (" \* " 또는 "?" 필터 사용)
- 구 (문서의 텍스트 시퀀스)
- 부울 값 (쿼리를 결합 하는 복잡 한 검색)

Lucene은 검색을 위해 낮은 수준의 통로를 제공 하지만, Elasticsearch는 Lucene 위에 있는 서버를 제공 합니다. Elasticsearch는 Lucene의 인덱싱 및 검색 기능에 액세스 하는 RESTful API를 포함 하 여 작업 Lucene을 간소화 하는 고급 기능을 추가 합니다. 또한 대규모 확장성, 내결함성 및 고가용성을 지 원하는 분산 인프라를 제공 합니다.

복잡 한 검색 요구 사항이 있는 대규모 클라우드 네이티브 응용 프로그램의 경우 Elasticsearch는 Azure에서 관리 서비스로 사용할 수 있습니다. Microsoft Azure Marketplace는 개발자가 Azure에서 Elasticsearch 클러스터를 배포 하는 데 사용할 수 있는 미리 구성 된 템플릿을 제공 합니다.

Microsoft Azure Marketplace에서 개발자는 미리 구성 된 템플릿을 사용 하 여 Azure에서 Elasticsearch 클러스터를 신속 하 게 배포할 수 있습니다. Azure에서 관리 하는 제품을 사용 하 여 최대 50 개의 데이터 노드, 20 개의 조정 노드 및 3 개의 전용 마스터 노드를 배포할 수 있습니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 네이티브 시스템의 데이터를 자세히 살펴봅니다. 모놀리식 응용 프로그램의 데이터 저장소를 클라우드 네이티브 시스템의 데이터 저장 패턴으로 대조 하 여 시작 했습니다. 서비스 간 쿼리, 분산 트랜잭션 및 대용량 시스템을 처리 하는 패턴을 포함 하 여 클라우드 네이티브 시스템에서 구현 된 데이터 패턴을 살펴보았습니다. SQL에서 NoSQL 데이터를 대조 합니다. Microsoft에서는 Microsoft 중심 및 오픈 소스 옵션을 모두 포함 하는 Azure에서 사용할 수 있는 데이터 저장소 옵션을 살펴보았습니다. 마지막으로, 클라우드 네이티브 응용 프로그램에서 캐싱과 Elasticsearch에 대해 설명 했습니다.

### <a name="references"></a>참조

- [CQRS(명령 및 쿼리 책임 분리) 패턴](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [이벤트 소싱 패턴](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [CAP 정리에서 RDBMS 파티션 사용이 허용 되지 않는 이유는 무엇 인가요?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [구체화된 뷰](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [오픈 소스 데이터베이스에 대해 알고 있어야 합니다.](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [보상 트랜잭션 패턴](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Saga 패턴](https://microservices.io/patterns/data/saga.html)

- [Saga 패턴 | 마이크로 서비스를 사용 하 여 비즈니스 트랜잭션을 구현 하는 방법](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [보상 트랜잭션 패턴](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [9-구슬 가져오기: Cosmos DB 일관성 수준 설명](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [여러 종류의 NoSQL 데이터베이스 탐색 파트 II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [RDBMS, NoSQL 및 NewSQL 데이터베이스에서 John Ryan로 인터뷰](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL 및 NewSQL: 전체 비교](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [대시: Kubernetes 데이터베이스의 네 가지 속성](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [CockroachDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Vitess](https://vitess.io/)

- [Elasticsearch: 최선의 가이드](https://shop.oreilly.com/product/0636920028505.do)
  
- [Apache Lucene 소개](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[이전](azure-caching.md)
>[다음](resiliency.md) <!-- Next Chapter -->
