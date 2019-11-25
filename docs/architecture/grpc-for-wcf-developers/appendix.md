---
title: WCF 개발자를 위한 부록 gRPC
description: 최신 마이크로 서비스 아키텍처에서 분산 트랜잭션 및 해당 구현에 대해 설명 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 061aef016fd0e4303e1bbcbf0e73cec2b0c54f74
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968212"
---
# <a name="appendix-a---transactions"></a>부록 A-트랜잭션

WCF (Windows Communication Foundation)는 여러 서비스에서 원자성 작업을 수행할 수 있도록 지 원하는 분산 트랜잭션을 지원 합니다. 이 기능은 [Microsoft DTC(Distributed Transaction Coordinator)](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85))를 기반으로 합니다.

최신 마이크로 서비스 환경에서는 이러한 유형의 자동화 된 분산 트랜잭션 처리를 사용할 수 없습니다. 단일 환경에서 사용할 수 있는 운영 체제, 프로그래밍 언어 및 프레임 워크를 소개 하는 것이 아니라 관계형 데이터베이스, NoSQL 데이터 저장소 및 메시징 시스템을 비롯 한 다양 한 기술을 재생할 수 있습니다.

WCF 분산 트랜잭션은 [2pc (2 단계 커밋)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol)로 알려진 기능을 구현한 것입니다. 서비스 간에 메시지를 조정 하 고, 각 서비스 내에서 열린 트랜잭션을 만들고, 성공 또는 실패에 따라 "커밋" 또는 "롤백" 메시지를 전송 하 여 2PC 트랜잭션을 수동으로 구현할 수 있습니다. 그러나 2PC를 관리 하는 것과 관련 된 복잡성은 시스템이 진화 함에 따라 급격 하 게 증가 하 고, 성능에 부정적인 영향을 미칠 수 있는 데이터베이스 잠금을 보유 한 개방형 트랜잭션 및 서비스 간 교착 상태가 발생할 수 있습니다.

가능 하면 분산 트랜잭션을 완전히 방지 하는 것이 좋습니다. 원자성 업데이트를 요구 하기 위해 데이터의 두 항목을 연결 하는 경우 동일한 서비스를 사용 하 여 두 데이터 항목을 처리 하 고 해당 서비스에 단일 요청 또는 메시지를 사용 하 여 이러한 원자성 변경을 적용 하는 것이 좋습니다.

가능 하지 않은 경우 [Saga 패턴](https://microservices.io/patterns/data/saga.html)을 사용 하는 것이 좋습니다. Saga 업데이트는 순차적으로 처리 됩니다. 각 업데이트가 성공 하면 다음 작업이 트리거됩니다. 이러한 트리거는 서비스에서 서비스로 전파 되거나 saga 코디네이터 또는 "orchestrator"로 관리 될 수 있습니다. 프로세스 중에 업데이트에 실패 한 경우 이미 업데이트를 완료 한 서비스는 특정 논리를 적용 하 여 해당 업데이트를 되돌립니다.

또 다른 옵션은 [.Net 마이크로 서비스 e-서적](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/)에 설명 된 대로 DDD (도메인 기반 디자인) 및 CQRS (명령/쿼리 책임 분리)를 사용 하는 것입니다. 특히 도메인 이벤트 또는 [이벤트 소싱](https://martinfowler.com/eaaDev/EventSourcing.html) 을 사용 하면 즉시&mdash;적용 되지 않는 경우 업데이트를 일관 되 게&mdash;수 있습니다.

>[!div class="step-by-step"]
>[이전](application-performance-management.md)
