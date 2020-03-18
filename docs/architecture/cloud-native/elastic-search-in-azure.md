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
# <a name="elasticsearch-in-a-cloud-native-app"></a>클라우드 네이티브 앱의 탄력적 검색

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch는 분산 검색 및 분석 시스템으로 다양한 유형의 데이터에 걸쳐 복잡한 검색 기능을 사용할 수 있습니다. 그것은 오픈 소스널리 인기. 다음 회사가 Elasticsearch를 응용 프로그램에 통합하는 방법을 고려하십시오.

- 전체 텍스트 및 증분 (입력으로 검색) 검색에 대한 [위키 백과.](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/)
- [GitHub를](https://www.elastic.co/customers/github) 사용하여 8백만 개 이상의 코드 리포지토리를 인덱싱하고 노출합니다.  
- 컨테이너 라이브러리를 검색 가능한 으로 만들기 위한 [Docker입니다.](https://www.elastic.co/customers/docker)

Elasticsearch는 [아파치 루센](https://lucene.apache.org/core/) 전체 텍스트 검색 엔진 위에 내장되어 있습니다. Lucene은 고성능 문서 인덱싱 및 쿼리를 제공합니다. 페이지를 키워드에 매핑하는 대신 책 끝에 있는 용어집처럼 페이지에 키워드를 매핑하는 역인덱싱 스키마를 사용하여 데이터를 인덱싱합니다. Lucene은 강력한 쿼리 구문 기능을 가지고 있으며 다음을 통해 데이터를 쿼리할 수 있습니다.

- 용어 (전체 단어)
- 접두사(단어로 시작)
- 와일드카드("\*또는 "?" 필터 사용)
- 구(문서의 텍스트 시퀀스)
- 부울 값(쿼리를 결합하는 복잡한 검색)

루센은 검색을 위해 낮은 수준의 배관을 제공하지만 Elasticsearch는 루센 위에 있는 서버를 제공합니다. Elasticsearch는 Lucene의 인덱싱 및 검색 기능에 액세스하는 RESTful API를 포함하여 작업 루센을 단순화하는 높은 수준의 기능을 추가합니다. 또한 대규모 확장성, 내결함성 및 고가용성이 가능한 분산 인프라를 제공합니다.

복잡한 검색 요구 사항이 있는 대규모 클라우드 네이티브 응용 프로그램의 경우 Elasticsearch를 Azure에서 관리되는 서비스로 사용할 수 있습니다. Microsoft Azure 마켓플레이스에는 개발자가 Azure에서 Elasticsearch 클러스터를 배포하는 데 사용할 수 있는 미리 구성된 템플릿이 있습니다.

Microsoft Azure 마켓플레이스에서 개발자는 빌드된 미리 구성된 템플릿을 사용하여 Azure에 Elasticsearch 클러스터를 신속하게 배포할 수 있습니다. Azure 관리 오퍼링을 사용하여 최대 50개의 데이터 노드, 20개의 조정 노드 및 3개의 전용 마스터 노드를 배포할 수 있습니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 네이티브 시스템의 데이터에 대한 자세한 설명입니다. 모놀리식 애플리케이션의 데이터 스토리지와 클라우드 네이티브 시스템의 데이터 스토리지 패턴을 대조하는 것으로 시작했습니다. 서비스 간 쿼리, 분산 트랜잭션 및 대량 시스템을 처리하기 위한 패턴을 포함하여 클라우드 네이티브 시스템에서 구현된 데이터 패턴을 살펴보았습니다. SQL을 NoSQL 데이터와 대조했습니다. Microsoft 중심 및 오픈 소스 옵션을 모두 포함하는 Azure에서 사용할 수 있는 데이터 저장소 옵션을 살펴보았습니다. 마지막으로 클라우드 네이티브 응용 프로그램에서 캐싱 및 Elasticsearch에 대해 설명했습니다.

### <a name="references"></a>참조

- [CQRS(명령 및 쿼리 책임 분리) 패턴](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [이벤트 소싱 패턴](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [RDBMSs vs. NoSQL 데이터베이스: 개요](https://maxivak.com/rdbms-vs-nosql-databases/)

- [CAP 정리에서 RDBMS 파티션이 관용적이지 않은 이유는 무엇입니까?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [구체화된 뷰](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [오픈 소스 데이터베이스에 대해 알아야 할 모든 것](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [보상 트랜잭션 패턴](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [사가 무늬](https://microservices.io/patterns/data/saga.html)

- [사가 패턴 | 마이크로 서비스를 사용하여 비즈니스 트랜잭션을 구현하는 방법](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [보상 트랜잭션 패턴](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [9볼 뒤처지다: 코스모스 DB 일관성 수준 설명](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [다양한 유형의 NoSQL 데이터베이스 파트 II 탐색](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [RDBMS, NoSQL 및 NewSQL 데이터베이스에서. 존 라이언과의 인터뷰](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL 대 NoSQL 대 NewSQL: 전체 비교](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: Kubernetes-네이티브 데이터베이스의 네 가지 속성](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [바퀴벌레DB](https://www.cockroachlabs.com/)

- [티DB](https://pingcap.com/en/)

- [유가바이트DB](https://www.yugabyte.com/)

- [비트 (주)](https://vitess.io/)

- [Elasticsearch: 최선의 가이드](http://shop.oreilly.com/product/0636920028505.do)
  
- [아파치 루센 소개](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[이전](azure-caching.md)
>[다음](resiliency.md) <!-- Next Chapter -->
