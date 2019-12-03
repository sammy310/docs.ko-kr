---
title: WCF 개발자를 위한 부록 gRPC
description: 최신 마이크로 서비스 아키텍처에서 분산 트랜잭션 및 해당 구현에 대해 설명 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 9931681727f921e007c2f80852ad0e69cd7288de
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711463"
---
# <a name="appendix-a---transactions"></a>부록 A-트랜잭션

WCF (Windows Communication Foundation)는 분산 트랜잭션을 지원 하므로 여러 서비스에서 원자성 작업을 수행할 수 있습니다. 이 기능은 [Microsoft DTC(Distributed Transaction Coordinator)](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85))를 기반으로 합니다.

최신 마이크로 서비스 환경에서는 이러한 유형의 자동화 된 분산 트랜잭션 처리를 사용할 수 없습니다. 관계형 데이터베이스, NoSQL 데이터 저장소 및 메시징 시스템을 비롯 한 다양 한 기술이 포함 되어 있습니다. 단일 환경에서 사용 되는 운영 체제, 프로그래밍 언어 및 프레임 워크가 혼합 되어 있을 수도 있습니다.

WCF 분산 트랜잭션은 [2pc (2 단계 커밋)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol)로 알려진 기능을 구현한 것입니다. 성공 또는 실패에 따라 서비스 간에 메시지를 조정 하 고, 각 서비스 내에서 열린 트랜잭션을 만들고, 커밋 또는 롤백 메시지를 전송 하 여 2PC 트랜잭션을 수동으로 구현할 수 있습니다. 그러나 2PC 관리와 관련 된 복잡성은 시스템이 진화 함에 따라 급격 하 게 증가할 수 있습니다. Open 트랜잭션은 성능에 부정적인 영향을 줄 수 있는 데이터베이스 잠금을 보유 하 고 있으며,이로 인해 서비스 간 교착 상태가 발생할 수 있습니다.

가능 하면 분산 트랜잭션을 완전히 방지 하는 것이 좋습니다. 원자성 업데이트를 요구 하기 위해 데이터의 두 항목을 연결 하는 경우 동일한 서비스를 사용 하 여 두 항목을 모두 처리 하는 것이 좋습니다. 해당 서비스에 단일 요청 또는 메시지를 사용 하 여 이러한 원자성 변경을 적용 합니다.

가능 하지 않은 경우 [Saga 패턴](https://microservices.io/patterns/data/saga.html)을 사용 하는 것이 좋습니다. Saga 업데이트는 순차적으로 처리 됩니다. 각 업데이트가 성공 하면 다음 작업이 트리거됩니다. 이러한 트리거는 서비스에서 서비스로 전파 되거나 saga 코디네이터 또는 orchestrator에서 관리 될 수 있습니다. 프로세스 중에 업데이트에 실패 한 경우 이미 업데이트를 완료 한 서비스는 특정 논리를 적용 하 여 해당 업데이트를 되돌립니다.

또 다른 옵션은 [.Net 마이크로 서비스 e-서적](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/)에 설명 된 대로 DDD (도메인 기반 디자인) 및 CQRS (명령/쿼리 책임 분리)를 사용 하는 것입니다. 특히 도메인 이벤트 또는 [이벤트 소싱](https://martinfowler.com/eaaDev/EventSourcing.html) 을 사용 하면 업데이트를 즉시 적용 하지 않을 경우 일관 되 게 유지 하는 데 도움이 됩니다.

>[!div class="step-by-step"]
>[이전](application-performance-management.md)
