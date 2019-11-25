---
title: 관계형 데이터베이스를 Azure로 마이그레이션
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 관계형 데이터베이스를 Azure로 마이그레이션
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73093622"
---
# <a name="migrate-your-relational-databases-to-azure"></a>관계형 데이터베이스를 Azure로 마이그레이션

비전: Azure는 가장 포괄적인 데이터베이스 마이그레이션을 제공합니다.

Azure에서 데이터베이스 서버를 IaaS VM으로 직접 마이그레이션하거나(순수한 리프트 앤 시프트), 추가 혜택을 위해 Azure SQL Database로 마이그레이션할 수 있습니다. Azure SQL Database는 관리되는 인스턴스와 전체 DBaaS(Database-as-a-Service) 옵션을 제공합니다. 그림 3-1에서는 Azure에서 사용할 수 있는 여러 관계형 데이터베이스 마이그레이션 경로를 보여줍니다.

![Azure의 데이터베이스 마이그레이션 경로](./media/image3-1.png)

**그림 3-1.** Azure의 데이터베이스 마이그레이션 경로

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Azure SQL Database Managed Instance로 마이그레이션하는 경우

대부분의 경우 Azure SQL Database Managed Instance는 데이터를 Azure로 마이그레이션할 때 고려해야 할 최상의 옵션입니다. SQL Server 데이터베이스를 마이그레이션할 때 애플리케이션을 다시 설계하거나 데이터 또는 데이터 액세스 코드를 변경할 필요가 없다는 거의 100% 보장이 필요한 경우 Azure SQL Database의 관리되는 인스턴스 기능을 선택하세요.

Azure SQL Database Managed Instance는 SQL Server 인스턴스 수준 기능에 대한 추가 요구 사항이 있거나 표준 Azure SQL Database(단일 데이터베이스 모델)에서 제공되는 기능 이외에 격리 요구 사항이 있는 경우 최상의 옵션입니다. 위 선택은 가장 PaaS 지향적 선택이지만 기존 SQL Server와 동일한 기능을 제공하지는 않습니다. 마이그레이션이 마찰을 초래할 수 있습니다.

예를 들어 인스턴스 수준 SQL Server 기능에 상당한 투자를 한 조직은 SQL Managed Instance로 마이그레이션하는 이점을 누릴 수 있습니다. 인스턴스 수준 SQL Server 기능의 예로는 SQL CLR(공용 언어 런타임) 통합, SQL Server 에이전트, 데이터베이스 간 쿼리 등이 있습니다. 표준 Azure SQL Database(단일 데이터베이스 모델)에서는 이러한 기능을 지원하지 않습니다.

고도로 규제되는 산업에서 사업을 영위하고 보안을 위해 격리를 유지해야 하는 조직에서는 SQL Managed Instance 모델을 선택하는 것이 유용할 수 있습니다.

Azure SQL Database의 관리되는 인스턴스에는 다음과 같은 특징이 있습니다.

- Azure Virtual Network를 통한 보안 격리

- 애플리케이션 화면 호환성, 다음 기능을 사용:

  - SQL Server 에이전트 및 SQL Server Profiler

  - 데이터베이스 간 참조 및 쿼리, SQL CLR, 복제, CDC(변경 데이터 캡처) 및 Service Broker

- 데이터베이스 크기 최대 35TB

- 최소 가동 중지 시간 마이그레이션, 다음 기능을 사용:

  - Azure Database Migration Service

  - 네이티브 백업/복원 및 로그 전달

이러한 기능을 사용하여 기존 애플리케이션 데이터베이스를 Azure SQL Database로 마이그레이션하면 관리되는 인스턴스 모델에서 SQL Serve용 PaaS의 이점을 거의 100% 제공합니다. 관리되는 인스턴스는 애플리케이션 디자인을 변경하지 않고 인스턴스 수준 기능을 계속 사용하는 SQL Server 환경입니다.

관리되는 인스턴스는 현재 SQL Server를 사용 중이고 클라우드에서 유연한 네트워크 보안이 필요한 엔터프라이즈에 가장 적합할 수 있습니다. 마치 SQL 데이터베이스용 사설 가상 네트워크를 보유하는 것과 같습니다.

## <a name="when-to-migrate-to-azure-sql-database"></a>Azure SQL Database로 마이그레이션하는 경우

앞서 언급했듯이, 표준 Azure SQL Database는 완전히 관리되는 관계형 DBaaS입니다. SQL Database는 현재 전 세계 38개 데이터 센터에서 수백만 개의 프로덕션 데이터베이스를 관리합니다. 간단한 트랜잭션 데이터 관리부터 글로벌 규모로 고급 데이터 처리가 필요한 가장 데이터 집중적인 중요 업무용 애플리케이션의 구동에 이르기까지 광범위한 애플리케이션 및 워크로드를 지원합니다.

전체 PaaS 기능, 더 나은 가격 책정, 궁극적으로 더 저렴한 비용 때문에 표준 SQL 데이터베이스를 사용하고 추가 인스턴스 기능을 사용하지 않는 경우 "기본 선택"으로 표준 Azure SQL Database로 마이그레이션해야 합니다. SQL CLR 통합, SQL Server 에이전트, 데이터베이스 간 쿼리와 같은 SQL Server 기능은 표준 Azure SQL Database에서 지원되지 않습니다. 이러한 기능은 Azure SQL Database Managed Instance 모델에서만 사용할 수 있습니다.

Azure SQL Database는 앱 개발자용으로 빌드된 유일한 인텔리전트 클라우드 데이터베이스 서비스입니다. 또한 다중 테넌트 앱을 효율적으로 제공할 수 있도록 가동 중지 시간 없이 즉시 크기 조정되는 유일한 클라우드 데이터베이스 서비스입니다. 궁극적으로 Azure SQL Database를 사용하면 혁신에 더 많은 시간을 투자하고 출시 기간을 단축할 수 있습니다. 원하는 언어 및 플랫폼을 사용하여 보안 앱을 빌드하고 SQL 데이터베이스에 연결할 수 있습니다.

Azure SQL Database는 다음과 같은 이점을 제공합니다.

- 앱을 학습하고 적절히 조정하는 기본 제공 인텔리전스(기계 학습)

- 주문형 데이터베이스 프로비전

- 모든 워크로드를 위한 다양한 제품

- 99.99% 가용성 SLA, 유지 관리 없음

- 데이터 보호를 위한 지리적 복제 및 복원 서비스

- Azure SQL Database 특정 시점 복원 기능

- 하이브리드 및 마이그레이션을 포함하여 SQL Server 2016 호환성

표준 Azure SQL Database는 Azure SQL Database Managed Instance보다 PaaS에 가깝습니다. 관리되는 클라우드에서 더 많은 이점을 얻을 수 있으므로 표준 Azure SQL Database를 사용하는 것이 좋습니다. 그러나 Azure SQL Database는 일반 및 온-프레미스 SQL Server 인스턴스와는 다른 몇 가지 주요 차이점이 있습니다. 기존 애플리케이션의 데이터베이스 요구 사항, 또한 엔터프라이즈 요구 사항 및 정책에 따라 클라우드로 마이그레이션을 계획할 때 이 옵션이 가장 적합한 선택이 아닐 수 있습니다.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>원본 RDBMS를 VM(IaaS)으로 이동하는 경우

마이그레이션 옵션 중 하나는 Oracle, IBM DB2, MySQL, PostgreSQL 또는 SQL Server를 포함하여 원래 RDBMS(관계형 데이터베이스 관리 시스템)를 Azure VM에서 실행되는 유사한 서버로 이동하는 것입니다. 변경을 최소화하거나 전혀 변경하지 않고 클라우드로 가장 빠르게 마이그레이션해야 하는 기존 애플리케이션이 있는 경우 클라우드의 IaaS로 직접 마이그레이션하는 것이 타탕한 옵션일 수 있습니다. 클라우드의 모든 이점을 활용하는 가장 좋은 방법이 아닐 수 있지만 가장 빠른 초기 경로입니다.

현재 Microsoft Azure는 IaaS VM으로 배포된 [331가지의 데이터베이스 서버](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all)를 지원합니다. 여기에는 SQL Server, Oracle, MySQL, PostgreSQL, IBM DB2와 같이 널리 사용되는 RDBMS와 MongoDB, Cassandra, DataStax, MariaDB, Cloudera와 같은 여러 NoSQL 데이터베이스가 포함됩니다.

> [!NOTE]
> RDBMS를 Azure VM으로 이동하는 것이 데이터를 클라우드로 마이그레이션하는 가장 빠른 방법일 수 있지만(IaaS이기 때문), 이 방법은 IT 팀(데이터베이스 관리자 및 IT 전문가)에 상당한 투자가 필요합니다. 엔터프라이즈 팀은 고가용성, 재해 복구 및 SQL Server 패치 적용을 설정하고 관리할 수 있어야 합니다. 이러한 상황에서는 모든 관리 권한이 있는 사용자 지정 환경도 필요합니다.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>VM(IaaS)으로서의 SQL Server로 마이그레이션하는 경우

일반 VM으로서의 SQL Server로 마이그레이션해야 하는 경우도 일부 있습니다. SQL Server Reporting Services를 사용해야 하는 경우를 예로 들 수 있습니다. 그러나 대부분의 경우 Azure SQL Database Managed Instance가 온-프레미스 SQL Server로부터 마이그레이션하는 데 필요한 모든 것을 제공할 수 있으므로 SQL Server VM로의 마이그레이션은 마지막으로 시도해야 할 방법입니다.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Azure Database Migration Service를 사용하여 관계형 데이터베이스를 Azure로 마이그레이션

Azure Database Migration Service를 사용하여 SQL Server, Oracle, MySQL 등의 관계형 데이터베이스를 Azure로 마이그레이션할 수 있습니다. Azure VM에서 대상 데이터베이스가 Azure SQL Database, Azure SQL Database Managed Instance 또는 SQL Server인지는 상관이 없습니다.

평가 보고 기능을 포함하는 자동 워크플로가 데이터베이스를 마이그레이션하기 전에 수행해야 하는 변경 사항을 안내합니다. 준비가 되면 이 서비스가 원본 데이터베이스를 Azure로 마이그레이션합니다.

원래 RDBMS를 변경할 때마다 다시 테스트해야 할 수 있습니다. 테스트 결과에 따라 애플리케이션에서 SQL 문이나 ORM(개체-관계형 매핑) 코드를 변경해야 할 수도 있습니다.

다른 데이터베이스(예: IBM DB2)가 있을 때 리프트 앤 시프트 방식을 선택할 경우 더 복잡한 데이터 마이그레이션을 수행하려는 경우가 아니면 이러한 데이터베이스를 Azure에서 IaaS VM으로 계속 사용할 수 있습니다. 더 복잡한 데이터 마이그레이션은 새 스키마와 다른 프로그래밍 라이브러리를 사용하여 다른 데이터베이스 형식으로 마이그레이션하는 것이기 때문에 추가 작업이 필요합니다.

Azure Database Migration Service를 사용하여 데이터베이스를 마이그레이션하는 방법에 대한 자세한 내용은 [Azure SQL Database Managed Instance 및 Azure Database Migration Service를 사용하여 더 빠르게 클라우드로 이동](https://channel9.msdn.com/Events/Build/2017/P4008)을 참조하세요.

## <a name="additional-resources"></a>추가 자료

- **클라우드 SQL Server 옵션을 선택합니다. Azure SQL Database(PaaS) 또는 Azure VM(IaaS)의 SQL Server**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Azure SQL DB Managed Instance 및 Database Migration Service를 사용하여 더 빠르게 클라우드로 이동**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **클라우드에서 SQL Database로 SQL Server 데이터베이스 마이그레이션**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL Database**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **Virtual Machines의 SQL Server**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [이전](lift-and-shift-existing-apps-azure-iaas.md)
> [다음](modernize-existing-apps-to-cloud-optimized/index.md) <!-- Next Chapter -->
