---
title: Azure의 데이터 저장소
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | Azure의 데이터 저장소
ms.date: 06/30/2019
ms.openlocfilehash: 1a86cecf005c6dbdfda5cf4cacfafaad4711c076
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841896"
---
# <a name="data-storage-in-azure"></a>Azure의 데이터 저장소

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

이 책 전반에서 보았듯이 응용 프로그램이 디자인, 배포 및 관리 되는 방식을 변경 하 고 있습니다. 클라우드로 전환할 때 중요 한 질문은 데이터를 어떻게 이동 하나요? 다행히 Azure 클라우드는 많은 옵션을 제공 합니다.

Azure 가상 컴퓨터를 프로 비전 하 고 선택한 데이터베이스를 설치할 수 있습니다. 이를 [IaaS (Infrastructure as a Service)](https://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas)라고 합니다. 이 방법은 온-프레미스 데이터베이스를 클라우드로 이동 하는 것을 간소화 하지만 가상 컴퓨터 및 데이터베이스를 관리 하는 부담을 이동 합니다.

대신, 완전히 관리 되는 [DBaaS (Database as a Service)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/) 가 더 나은 옵션입니다. Microsoft에서 호스팅, 유지 관리 및 라이선스를 관리 하는 동안 여러 가지 기본 제공 기능을 이용할 수 있습니다. Azure는 다양 한 종류의 완전히 관리 되는 데이터 저장소 옵션을 제공 하며, 각 옵션에는 특정 혜택이 있습니다. Just-in-time 용량과 종 량 제 모델을 모두 지원 합니다.

다음으로 Azure에서 제공 되는 DBaaS 옵션을 살펴보겠습니다. Microsoft가 계속 해 서 Azure를 "오픈 플랫폼"으로 유지 하 고, 다양 한 오픈 소스 관계형 및 NoSQL 데이터베이스에 대 한 관리 되는 지원을 제공 하 고, 다양 한 오픈 소스에 대 한 주요 기여를 활성 멤버로 유지 하는 것을 확인할 수 있습니다.

## <a name="azure-sql-database"></a>Azure SQL Database

[Azure SQL Database](https://docs.microsoft.com/azure/sql-database/) 은 Microsoft SQL Server 데이터베이스 엔진을 기반으로 하는 기능을 갖춘 범용 관계형 dbaas (데이터베이스)입니다. Microsoft에서 완벽 하 게 관리 되 고 있으며, 안정적인 고성능의 안전한 클라우드 데이터베이스입니다. 서비스는 SQL Server의 온-프레미스 버전에 있는 다양 한 기능을 공유 합니다.

몇 분 안에 SQL Database 서버와 데이터베이스를 프로 비전 할 수 있습니다. 응용 프로그램에 대 한 수요가 몇 명의 고객에서 수백만 명으로 증가 하는 경우 가동 중지 시간을 최소화 하면서 신속 하 게 Azure SQL Database 확장할 수 있습니다. CPU 전원, 메모리, IO 처리량 및 데이터베이스에 할당 된 저장소를 비롯 한 리소스를 동적으로 추가 하거나 제거할 수 있습니다.

그림 5-12은 Azure SQL Database에 대 한 배포 옵션을 보여 줍니다.

![Azure SQL 배포 옵션](./media/azure-sql-database-deployment-options.png)

**그림 5-12**. Azure SQL 배포 옵션

이전 그림에서 SQL Database를 배포할 때의 대안을 참고 합니다.

- [단일 데이터베이스](https://docs.microsoft.com/azure/sql-database/sql-database-single-database) 는 [SQL Database 서버](https://docs.microsoft.com/azure/sql-database/sql-database-servers)에서 관리 하는 리소스 집합을 . 단일 데이터베이스는 온-프레미스 SQL Server 배포에서 [포함 된 데이터베이스](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) 와 비슷합니다.

- SQL 데이터베이스 컬렉션이 설정 된 가격으로 단일 SQL Database 서버를 공유 하는 [탄력적 풀](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool) 입니다. 데이터베이스 그룹에 대 한 가격 성능을 최적화 하기 위해 필요에 따라 탄력적 풀에서 단일 데이터베이스를 이동할 수 있습니다.

- 가 시스템 및 사용자 데이터베이스의 컬렉션인 [Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) 온-프레미스 SQL Server와 거의 100%의 호환성을 제공 합니다. 이 옵션은 최대 35 TB의 더 큰 데이터베이스를 지원 하 고 더 나은 격리를 위해 [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) 에 배치 됩니다.

Azure SQL Database는 완전히 관리 되는 [PaaS (Platform as a Service 데이터베이스 엔진)](https://docs.microsoft.com/azure/sql-database/sql-database-paas) 로, 사용자 개입 없이 업그레이드, 패치, 백업 및 모니터링을 처리 합니다. 항상 안정적인 최신 버전의 SQL Server 데이터베이스 엔진 및 패치 된 OS를 실행 하 고 99.99%의 가용성을 보장 합니다. 하나의 기능인 [활성 지역 복제](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)를 사용 하 여 동일한 또는 다른 Azure 데이터 센터에서 읽기 가능한 보조 데이터베이스를 만들 수 있습니다. 오류가 발생 하면 보조 데이터베이스에 대 한 장애 조치 (failover)를 시작할 수 있습니다. 이 시점에서 다른 보조 데이터베이스는 새 주 데이터베이스에 자동으로 연결 됩니다. 하나 또는 여러 지역에서 최대 4 개의 보조 복제본이 지원 되며 이러한 보조 복제본은 읽기 전용 액세스 쿼리에도 사용할 수 있습니다.

Azure SQL Database에는 성능을 최대화 하 고 운영 비용을 절감 하는 데 도움이 되는 [기본 제공 모니터링 및 지능형 튜닝](https://docs.microsoft.com/azure/sql-database/sql-database-monitoring-tuning-index) 기능이 포함 되어 있습니다. 예를 들어 [자동 조정](https://docs.microsoft.com/azure/sql-database/sql-database-automatic-tuning) 기능은 AI 및 기계 학습에 따라 지속적인 성능 조정을 제공 합니다. 서비스는 실행 중인 워크 로드를 학습 하 고 튜닝 권장 사항을 적용할 수 있습니다. 자동 조정 기능을 사용 하 여 Azure SQL Database 실행이 길수록 성능이 향상 됩니다.

[서버](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) 를 사용 하지 않는 Azure SQL Database (이 책을 작성할 때 미리 보기로 제공 됨)는 워크 로드 요구 사항에 따라 자동으로 크기가 조정 되는 단일 데이터베이스에 대 한 계산 계층 이며 초당 사용 된 계산의 양에 대 한 요금을 청구 합니다. 서버를 사용 하지 않는 계산 계층은 비활성 기간 동안에도 데이터베이스를 자동으로 일시 중지 하므로 저장소 요금만 청구 됩니다. 작업이 반환 되 면 자동으로 다시 시작 됩니다.

마지막으로, 새로운 Azure SQL Database 하이퍼 [확장](https://azure.microsoft.com/services/sql-database/) 가격 책정 계층이 있습니다. 확장성이 뛰어난 저장소 아키텍처를 기반으로 하며, 필요에 따라 데이터베이스를 확장할 수 있으므로 저장소 리소스를 미리 프로 비전 할 필요가 없습니다. 계산 및 저장소 리소스를 독립적으로 확장 하 여 각 워크 로드의 성능을 최적화 하는 유연성을 제공할 수 있습니다. Azure SQL Database Hyperscale은 최대 100 TB의 저장소를 사용 하는 [OLTP](https://en.wikipedia.org/wiki/Online_transaction_processing) 처리 및 높은 처리량의 분석 워크 로드에 최적화 되어 있습니다.  읽기 집약적인 작업을 사용 하는 경우 하이퍼 확장은 읽기 작업을 오프 로드 하는 데 필요한 추가 읽기 복제본을 프로 비전 하 여 신속한 확장을 제공 합니다.

기존 Microsoft SQL Server stack 외에도 Azure는 널리 사용 되는 여러 오픈 소스 데이터베이스의 관리 되는 버전을 제공 합니다.

## <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) 는 [오픈 소스](https://en.wikipedia.org/wiki/Open-source_software) [관계형 데이터베이스](https://en.wikipedia.org/wiki/Relational_database_management_system)입니다. [전구 소프트웨어 스택의](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) 구성 요소 이며, Facebook, Twitter, YouTube 등의 많은 조직에서 사용 됩니다. Community edition은 무료로 제공 되며 enterprise edition은 라이선스를 구매 해야 합니다. 원래 1995에 생성 된 제품은 2008에서의 Sun Microsystems에 의해 구매한 것입니다 .이 제품은 2010의 Oracle에서 획득 했습니다.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) 는 오픈 소스 MySQL 서버 엔진을 기반으로 하는 완전히 관리 되는 엔터프라이즈급 관계형 데이터베이스 서비스입니다. MySQL Community edition을 구현 하는 경우 추가 비용 없이 다음과 같은 PaaS 기능을 포함 합니다.

- 기본 제공 되는 [고가용성](https://docs.microsoft.com/azure/mysql/concepts-high-availability)입니다.

- 포괄 [종 량 제 가격 책정](https://docs.microsoft.com/azure/mysql/concepts-pricing-tiers)을 사용 하는 예측 가능한 성능.

- 몇 초 내에 필요에 따라 [크기를 조정](https://docs.microsoft.com/azure/mysql/concepts-high-availability) 합니다.

- 휴지 상태의 중요 한 데이터를 보호 하 고 이동 합니다.

- 최대 35 일 동안 [자동 백업](https://docs.microsoft.com/azure/mysql/concepts-backup) 및 지정 [시간 복원](https://docs.microsoft.com/azure/mysql/concepts-backup) .

- 엔터프라이즈급 보안 및 규정 준수

이러한 기본 제공 PaaS 기능은 데이터 센터에 수백 개의 "전술" (전략적이 지 않은) 데이터베이스가 있지만 패치, 백업, 보안 및 성능 모니터링을 수행할 리소스가 없는 조직에 중요 합니다.

또한 [Azure 데이터 마이그레이션 서비스](https://azure.microsoft.com/services/database-migration/) 는 가동 중지 시간을 최소화 하면서 여러 데이터베이스 원본에서 Azure 데이터 플랫폼으로 데이터를 마이그레이션할 수 있습니다. 서비스는 평가 보고서를 생성 하 고 마이그레이션을 수행 하는 데 필요한 변경 내용 (중소 규모)을 안내 하는 권장 사항을 제공 합니다.

관리 되는 [Azure MySQL 서버](https://docs.microsoft.com/azure/mysql/concepts-servers) 는 서비스에 대 한 중앙 관리 지점입니다. 이는 온-프레미스 배포에 사용 되는 것과 동일한 MySQL 서버 엔진입니다. 이를 사용 하면 서버당 단일 데이터베이스를 만들어 모든 리소스를 사용 하거나 서버당 여러 데이터베이스를 만들어 리소스를 공유할 수 있습니다. 팀은 새로운 기술에 대해 알아보거나 가상 머신과 인프라를 관리 하지 않고도 원하는 오픈 소스 도구 및 플랫폼을 사용 하 여 응용 프로그램을 계속 개발할 수 있습니다.

## <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[Mariadb](https://mariadb.com/) 서버는 다른 인기 있는 오픈 소스 데이터베이스 서버입니다. Mysql의 원래 개발자가 mysql을 소유 하는 Oracle 구매한 Sun Microsystems 때 mysql의 포크로 만들어졌습니다. 이는 MariaDB가 오픈 소스를 유지 하도록 하기 위한 것입니다.

MariaDB는 [MySQL의 포크](https://blog.panoply.io/a-comparative-vmariadb-vs-mysql)이기 때문에 데이터 및 테이블 정의가 호환 되며 클라이언트 프로토콜, 구조 및 api가 결합 됩니다. MySQL 데이터 커넥터는 수정 없이는 MariaDB에서 작동 합니다.

MariaDB는 강력 하 고 많은 기업에서 사용 됩니다. Oracle은 계속 해 서 MySQL을 유지 관리 하 고, 강화 하 고, 지원 하는 반면, MariaDB는 제품 및 설명서에 대 한 공용 기여를 허용 하는 Aadb Foundation에서 관리 됩니다.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) 은 Azure 클라우드에서 완전히 관리 되는 Database as a Service입니다. 이는 [Mariadb community edition](https://mariadb.org/download/) 서버 엔진을 기반으로 합니다. 예측 가능한 성능과 동적 확장성으로 중요 업무용 워크 로드를 처리할 수 있습니다. 다른 Azure 데이터베이스 플랫폼과 마찬가지로 추가 비용 없이 다양 한 플랫폼 as a 서비스 기능을 포함 합니다.

- 기본 제공 되는 [고가용성](https://docs.microsoft.com/azure/mariadb/concepts-high-availability)입니다.

- 포괄 [종 량 제 가격 책정](https://docs.microsoft.com/azure/mariadb/concepts-pricing-tiers)을 사용 하는 예측 가능한 성능.

- 몇 초 내에 필요에 따라 [크기를 조정](https://docs.microsoft.com/azure/mariadb/concepts-high-availability) 합니다.

- 중요 한 데이터를 안전 하 게 보호 하 고 미사용 데이터를 보호 합니다.

- 최대 35 일 동안 [자동 백업](https://docs.microsoft.com/azure/mariadb/concepts-backup) 및 지정 [시간 복원](https://docs.microsoft.com/azure/mariadb/concepts-backup) .

- 엔터프라이즈급 보안 및 규정 준수

## <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) 는 30 년 이상 활성 개발을 갖춘 다른 인기 있는 오픈 소스 관계형 데이터베이스입니다. 범용 및 개체 관계형 데이터베이스 관리 시스템입니다. 해당 라이선스는 "자유로운" 것으로 간주 되 고 제품은 모든 형식으로 자유롭게 사용, 수정 및 배포할 수 있습니다. Apple, Red Hat 및 Fujitsu를 비롯 한 많은 대기업은 PostgreSQL를 사용 하 여 제품을 구축 했습니다.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) 은 오픈 소스 Postgres 데이터베이스 엔진을 기반으로 하는 완전히 관리 되는 관계형 데이터베이스 서비스입니다. 예측 가능한 성능, 보안, 고가용성 및 동적 확장성으로 중요 업무용 워크 로드를 처리할 수 있습니다. Java, Python, Node, C\#및 PHP를 C++비롯 한 몇 가지 오픈 소스 프레임 워크 및 언어를 지원 합니다. 명령줄 인터페이스 또는 [Azure 데이터 마이그레이션 서비스](https://azure.microsoft.com/services/database-migration/)를 통해 PostgreSQL 데이터베이스를 [마이그레이션할](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) 수 있습니다.

이 서비스에는 고유한 데이터베이스 패턴을 연구 하 고 PostgreSQL 데이터베이스의 성능을 최대화 하는 데 도움이 되는 사용자 지정 된 권장 사항 및 통찰력을 제공 하는 [기본 제공 인텔리전스](https://docs.microsoft.com/azure/postgresql/concepts-monitoring) 가 포함 되어 있습니다. [Advanced Threat Protection](https://docs.microsoft.com/azure/postgresql/concepts-data-access-and-security-threat-protection) 은 시계를 기준으로 데이터베이스를 모니터링 하 고 잠재적 악성 활동을 감지 하 여 사용자가 즉시 개입할 수 있도록 검색 시 경고 합니다.

Azure Database for PostgreSQL는 단일 서버 및 하이퍼 규모 (Citus)의 두 가지 배포 옵션으로 사용할 수 있으며,이 책을 작성할 때 미리 보기에 사용할 수 있습니다.

- [단일 서버](https://docs.microsoft.com/azure/postgresql/concepts-servers) 배포 옵션은 여러 데이터베이스에 대 한 중앙 관리 지점입니다. 온-프레미스 배포에 사용할 수 있는 것과 동일한 PostgreSQL 서버 엔진입니다. 이를 통해 모든 리소스를 사용 하거나 여러 데이터베이스를 만들어 리소스를 공유 하도록 서버당 단일 데이터베이스를 만들 수 있습니다. 가격은 코어 및 저장소에 따라 서버 별로 구성 됩니다.

- [Citus (Hyperscale) 옵션](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) 은 [Citus Data](https://www.citusdata.com/) 기술을 기반으로 합니다. 이를 통해 수백 개의 노드에서 단일 데이터베이스를 수평으로 확장 하 여 짧으며 빠른 성능 및 규모를 제공할 수 있으므로 고성능을 확장할 수 있습니다. 이 옵션을 사용 하면 엔진은 메모리에 더 많은 데이터를 맞추고, 수백 개의 노드에서 쿼리를 병렬화 하 고, 데이터를 더 빠르게 인덱싱할 수 있습니다. 하이퍼 크기 조정 기능은 PostgreSQL에 대 한 최신 혁신, 버전 및 도구와 호환 되므로 기존 PostgreSQL 전문 지식을 활용할 수 있습니다.

## <a name="cosmos-db"></a>Cosmos DB

Azure Cosmos DB은 낮은 대기 시간, 탄력적 확장성, 관리 되는 데이터 일관성 및 고가용성을 제공 하도록 설계 된 완전히 관리 되는 전역으로 분산 된 NoSQL 데이터베이스 서비스입니다. 간단히 말해서 응용 프로그램에서 전 세계 어디에서 나 빠른 응답 시간을 보장 해야 하는 경우 항상 온라인 상태 여야 하 고 처리량 및 저장소의 무제한 및 탄력적 확장성이 필요한 경우 Cosmos DB을 선택 하는 것이 좋습니다. 그림 5-13에는 Cosmos DB에 대 한 개략적인 개요가 나와 있습니다.

![Cosmos DB 개요](./media/cosmos-db-overview.png)

**그림 5-13**: Cosmos DB 개요

그림 5-13에서는 기본 제공 되는 다양 한 클라우드 기본 기능을 사용 하는 강력 하 고 융통성 있는 데이터베이스 서비스를 Cosmos DB 하는 방법을 설명 합니다. 이 섹션에서는이에 대해 좀 더 자세히 살펴보겠습니다.

### <a name="global-support"></a>글로벌 지원

전 세계 모든 Azure 지역에서 Cosmos 데이터베이스를 전역적으로 배포 하 고, 데이터를 사용자에 게 가깝게 배치 하 고, 응답 시간을 개선 하 고, 대기 시간을 줄일 수 있습니다. 응용 프로그램을 일시 중지 하거나 다시 배포 하지 않고 지역에서 데이터베이스를 추가 하거나 제거할 수 있습니다. 백그라운드에서 Cosmos DB는 구성 된 모든 지역에 데이터를 투명 하 게 복제 합니다.

Cosmos DB는 전역 수준에서 [능동/능동](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) 클러스터링을 지원 하 여 쓰기 및 읽기를 모두 지원 하도록 모든 또는 모든 데이터베이스 영역을 구성할 수 있도록 합니다.

Cosmos DB의 [다중 마스터](https://docs.microsoft.com/azure/cosmos-db/how-to-multi-master) 프로토콜 기능을 사용 하면 다음과 같은 기능을 사용할 수 있습니다.

- 무제한 탄력적 쓰기 및 읽기 확장성.

- 전 세계의 모든 읽기 및 쓰기 가용성 99.999%

- 99 번째 백분위 수에서 10 밀리초 이내에 보장 된 읽기 및 쓰기가 제공 됩니다.

내부적으로 Cosmos DB는 일관성 수준 보장 및 재정적 지원 서비스 수준 계약을 포함 하는 지역 간의 데이터 복제를 처리 합니다.

Cosmos DB [멀티 호 밍 api](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)를 사용 하면 응용 프로그램이 자동으로 가장 가까운 Azure 지역에 대해 인식 하 고 요청을 보낼 수 있습니다. 가장 가까운 지역은 구성 변경 없이 Cosmos DB로 식별 됩니다. 영역을 사용할 수 없게 되 고, Cosmos DB 자동 장애 조치 (failover)를 지원 하 고, 멀티 호 밍 기능이 사용 가능한 가장 가까운 다음 지역으로 요청을 자동으로 라우팅합니다.

### <a name="multi-model-support"></a>다중 모델 지원

Cosmos DB는 문서, 키-값 쌍, 넓은 열 및 그래프 표현을 포함 하 여 지원 되는 여러 NoSQL 모델을 사용 하 여 데이터와 상호 작용할 수 있도록 하는 *다중 모델 데이터 플랫폼* 입니다. 내부적으로 데이터는 문자열, 부울 및 숫자를 포함 하 여 기본 데이터 형식으로 구성 된 간단한 [구조체](https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/using-structs) 형식으로 저장 됩니다. 각 요청에 대해 데이터베이스 엔진은 데이터를 선택한 모델 표현으로 변환 합니다. 전용 Cosmos DB SQL 기반 API 또는 그림 5-14에 표시 된 [호환성 api](https://www.wikiwand.com/en/Cosmos_DB) 중에서 선택할 수 있습니다.

![Cosmos DB 공급자](./media/cosmos-db-providers.png)

**그림 5-14**: Cosmos DB 공급자

그림 5-14에서는 Cosmos DB에서 [Table Storage](https://azure.microsoft.com/services/storage/tables/)를 지 원하는 방법을 설명 합니다. Cosmos DB와 [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) 는 모두 동일한 기본 테이블 모델을 공유 하 고 여러 개의 동일한 테이블 작업을 노출 합니다. 그러나 [Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction) 는 Azure Storage API에서 사용할 수 없는 많은 프리미엄 향상 기능을 제공 합니다. 이러한 기능은 그림 5-15에서 대조 됩니다.

![Azure Table API](./media/azure-table-api.png)

**그림 5-15**: Azure Table API

Azure Table storage 용으로 작성 된 응용 프로그램은 코드를 변경 하지 않고 Table API를 사용 하 여 Azure Cosmos DB로 마이그레이션할 수 있습니다.

[Brownfield](https://en.wikipedia.org/wiki/Brownfield_(software_development)) 응용 프로그램 시나리오에서 개발 팀은 기존 데이터 나 응용 프로그램 코드를 최소한으로 변경 하 여 기존 Mongo, Gremlin 또는 Cassandra 데이터베이스를 Cosmos DB로 마이그레이션할 수 있습니다. [최적의](https://en.wikipedia.org/wiki/Greenfield_project) 시나리오의 경우 개발 팀은 MongoDB, Cassandra 및 Gremlin 플랫폼에 대해 완전히 지원 되는 오픈 소스 옵션을 포함 하 여 요구 사항 및 기본 설정을 가장 잘 충족 하는 데이터 모델을 선택할 수 있습니다.

### <a name="consistency-models"></a>일관성 모델

이전에는 *관계형 Vs NoSQL* 섹션에서 데이터의 무결성을 참조 하는 용어 인 *데이터 일관성*의 주제에 대해 설명 했습니다. 고가용성, 짧은 대기 시간 또는 둘 다에 대해 복제를 사용 하는 분산 데이터베이스는 읽기 일관성, 가용성 및 대기 시간 간에 기본적인 균형을 유지 해야 합니다.

대부분의 분산 데이터베이스를 통해 개발자는 두 가지 일관성 모델 ( [강력한 일관성](https://en.wikipedia.org/wiki/Strong_consistency) 과 [최종 일관성](https://en.wikipedia.org/wiki/Eventual_consistency)) 중에서 선택할 수 있습니다. *강력한 일관성* 은 데이터 프로그래밍의 골드 표준입니다. 모든 데이터베이스 복사본에서 업데이트가 복제 될 때까지 대기 시간이 발생 해야 하는 경우에도 쿼리 결과는 항상 최신 데이터를 반환 하도록 보장 합니다. 반면, *최종 일관성* 을 위해 구성 된 시스템은 데이터가 최신 복사본이 아니더라도 데이터를 즉시 반환 합니다. 이 옵션을 사용 하면 더 높은 가용성, 더 큰 규모 및 향상 된 성능을 제공 합니다.

Azure Cosmos DB는 그림 5-16에 나와 있는 [잘 정의 된 5 가지 일관성 모델](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) 의 스펙트럼을 제공 합니다. 이러한 옵션을 사용 하면 응용 프로그램의 요구 사항에 따라 가용성 및 성능에 대 한 정밀한 선택과 세부적인 절충을 만들 수 있습니다. 이러한 모델은 잘 정의 되 고 직관적 이며 Sla (서비스 수준 계약)에 의해 지원 됩니다.

![Cosmos DB 일관성 수준](./media/cosmos-db-consistency-levels.png)

**그림 5-16**: Cosmos DB 일관성 수준

### <a name="partitioning"></a>분할

Azure Cosmos DB는 자동 [분할](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) 을 사용 하 여 응용 프로그램의 성능 요구에 맞게 데이터베이스를 확장 합니다.

그림 5-17에 나와 있는 것 처럼 [데이터베이스, 컨테이너 및 항목](https://docs.microsoft.com/azure/cosmos-db/databases-containers-items)을 만들어 Cosmos DB 데이터의 데이터를 관리할 수 있습니다.

![엔터티 Cosmos DB](./media/cosmos-db-entities.png)

**그림 5-17**: Cosmos DB 엔터티의 계층 구조

그림 5-17에서는 데이터베이스 계정 내에 Cosmos DB 데이터베이스를 만들어서 시작 하는 방법을 설명 합니다. 해당 데이터베이스는 컨테이너 집합에 대 한 관리 단위가 됩니다. 컨테이너는 선택한 API 공급자 (이전 섹션에서 설명)를 기반으로 컬렉션, 테이블 또는 그래프로 표현할 수 있는 스키마에 관계 없이 항목의 그룹입니다. 항목은 컨테이너에 추가 하 고 문서, 행, 노드 또는 가장자리로 표시 되는 데이터입니다. 기본적으로 컨테이너에 추가 하는 모든 항목은 명시적 인덱스 또는 스키마 관리를 요구 하지 않고 자동으로 인덱싱됩니다.

컨테이너를 분할 하기 위해 항목은 [논리적 파티션](https://docs.microsoft.com/azure/cosmos-db/partition-data)이라는 별개의 하위 집합으로 나뉩니다. 논리적 파티션은 컨테이너의 각 항목과 연결 된 파티션 키의 값을 기반으로 생성 됩니다. 그림 5-18에서는 논리 파티션의 모든 항목에 동일한 파티션 키 값이 포함 되는 방법을 보여 줍니다.

![Cosmos DB 분할 메커니즘](./media/cosmos-db-partitioning.png)

**그림 5-18**: Cosmos DB 분할 메커니즘

그림 5-18에서 각 항목에는 ' city ' 또는 ' 공항 '의 파티션 키가 포함 되어 있는 방법이 나와 있습니다. 이 파티션 키는 항목의 논리적 파티션을 결정 합니다. 각 도시 코드는 왼쪽에 있는 컨테이너의 논리 파티션에 할당 되며 공항 코드를 사용 하 여 오른쪽에 있는 컨테이너에 할당 됩니다. 파티션 키 값을 항목의 ID 값과 결합 하면 항목을 고유 하 게 식별 하는 항목의 인덱스가 생성 됩니다.

내부적으로 Cosmos DB는 컨테이너의 확장성 및 성능 요구를 효율적으로 충족 하기 위해 [물리적 파티션의](https://docs.microsoft.com/azure/cosmos-db/partition-data) [논리 파티션](https://docs.microsoft.com/azure/cosmos-db/partition-data) 배치를 자동으로 관리 합니다. 응용 프로그램의 처리량 및 저장소 요구 사항이 증가 하면 Azure Cosmos DB 논리적 파티션을 이동 하 여 더 많은 수의 서버에 부하를 재배포할 수 있습니다. 이러한 재배포 작업은 Cosmos DB에서 관리 되며 중단 또는 가동 중지 시간 없이 수행 됩니다.

## <a name="azure-redis-cache"></a>Azure Redis Cache

성능 및 확장성을 향상 시키기 위한 캐싱의 이점은 잘 이해 됩니다.

클라우드 네이티브 응용 프로그램의 경우 캐싱을 추가 하는 일반적인 위치는 API 게이트웨이 내에 있습니다. 게이트웨이는 들어오는 모든 요청에 대 한 프런트 엔드 역할을 합니다. 캐싱을 추가 하 여 캐시 된 데이터를 반환 하 고 로컬 데이터베이스 또는 다운스트림 서비스로의 왕복을 방지 하 여 성능과 응답성을 높일 수 있습니다. 그림 5-19에서는 클라우드 네이티브 응용 프로그램에 대 한 캐싱 아키텍처를 보여 줍니다.

![클라우드 네이티브 앱에서 캐싱](./media/caching-in-a-cloud-native-app.png)

**그림 5-19**: 클라우드 네이티브 앱에서 캐싱

일반적인 캐싱 패턴은 캐시 배제 [패턴](https://docs.microsoft.com/azure/architecture/patterns/cache-aside)입니다. 들어오는 요청의 경우 먼저 그림 5-19의 #1 단계에 표시 된 응답에 대 한 캐시를 쿼리 합니다. 데이터를 찾았으면 즉시 반환 됩니다. 데이터가 캐시에 없으면 ( [캐시 누락](https://www.techopedia.com/definition/6308/cache-miss)이라고 함) 로컬 데이터베이스 또는 다운스트림 서비스 (단계 #2)에서 검색 되 고 이후 요청에 대 한 캐시에 기록 (#3 단계) 된 다음 호출자에 게 반환 됩니다. 시스템이 일관 되 고 정확 하 게 유지 되도록 캐시 된 데이터를 정기적으로 제거 해야 합니다.

또한 그림 5-19에서는 캐시를 서비스 경계 내에서 로컬로 구현 하지 않고 대신 클라우드 기반 지원 서비스로 사용 하는 방법에 대해 설명 합니다.

[Azure Redis Cache](https://azure.microsoft.com/services/cache/) 은 데이터 캐싱 및 메시징 브로커 서비스입니다. 응용 프로그램 데이터에 대 한 높은 처리량 및 짧은 대기 시간 액세스를 제공 합니다. Microsoft에서 완벽 하 게 관리 하 고, Azure 내에서 호스트 되며, Azure 내부 또는 외부의 모든 응용 프로그램에 액세스할 수 있습니다.

내부적으로 Azure Cache for Redis는 오픈 소스 [Redis 서버](https://redis.io/) 에서 지원 되며 [문자열](https://redis.io/topics/data-types#strings), [해시](https://redis.io/topics/data-types#hashes), [목록](https://redis.io/topics/data-types#sets), [집합](https://redis.io/topics/data-types#sets), [정렬 된 집합](https://redis.io/topics/data-types#sorted-sets)등의 데이터 구조를 기본적으로 지원 합니다. 응용 프로그램에서 Redis를 사용 하는 경우 Redis 용 Azure Cache와 동일 하 게 작동 합니다.

Redis 용 Azure Cache는 메모리 내 데이터 캐시, 분산 된 비관계형 데이터베이스 및 메시지 브로커로도 사용할 수 있습니다. 세 가지 가격 책정 계층에서 사용할 수 있습니다. 프리미엄 계층에는 클러스터링, 데이터 지 속성, 지역에서 복제, 가상 네트워크 보안 및 격리와 같은 많은 엔터프라이즈 수준 기능이 있습니다.

>[!div class="step-by-step"]
>[이전](data-patterns.md)
>[다음](resiliency.md)
