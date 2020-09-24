---
title: 클라우드 네이티브 복원력
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 기본 복원 력
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 5c4fb261515c151fd666cc33cbb020447716c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163559"
---
# <a name="cloud-native-resiliency"></a>클라우드 네이티브 복원력

복원 력은 시스템에서 오류에 대응 하 여 계속 작동 하는 기능입니다. 오류를 방지 하는 것은 아니지만 실패를 수락 하 고 클라우드-원시 서비스를 구성 하 여 응답 합니다. 가능 하면 신속 하 게 작동 하는 상태로 돌아갈 수 있습니다.

단일 프로세스에서 모든 항목을 함께 실행 하는 기존 모놀리식 응용 프로그램과 달리 클라우드 네이티브 시스템은 그림 6-1에 표시 된 것 처럼 분산 아키텍처를 수용 합니다.

![분산 클라우드-기본 환경](./media/distributed-cloud-native-environment.png)

**그림 6-1.** 분산 클라우드-기본 환경

위의 그림에서 각 마이크로 서비스 및 클라우드 기반 [지원 서비스](https://12factor.net/backing-services) 는 서버 인프라 전체에서 네트워크 기반 호출을 통해 통신 하는 별도의 프로세스로 실행 됩니다.

이 환경에서 작동 하는 서비스는 다양 한 문제를 해결 해야 합니다.

- 예기치 않은 네트워크 대기 시간-서비스 요청이 수신기로 이동 하는 시간입니다.

- [일시적인 오류](/azure/architecture/best-practices/transient-faults) -수명이 짧은 네트워크 연결 오류입니다.

- 장기 실행 동기 작업으로 차단을.

- 작동이 중단 되 고 다시 시작 되거나 이동 중인 호스트 프로세스입니다.

- 짧은 시간 동안 응답할 수 없는 오버 로드 된 마이크로 서비스입니다.

- 롤링 업그레이드 또는 한 노드에서 다른 노드로 서비스 이동과 같은 진행 중인 orchestrator 작업

- 하드웨어 오류.

클라우드 플랫폼은 이러한 많은 인프라 문제를 감지 하 고 완화할 수 있습니다. 다시 시작 하 고, 규모를 확장 하 고, 서비스를 다른 노드로 재배포할 수도 있습니다.  그러나이 기본 제공 보호 기능을 최대한 활용 하려면이 동적 환경에서 it 및 올립니다에 대응할 수 있도록 서비스를 설계 해야 합니다.

다음 섹션에서는 가동 중지 시간 및 중단을 최소화 하기 위해 서비스 및 관리 되는 클라우드 리소스가 활용할 수 있는 방어 기법을 살펴보겠습니다.

>[!div class="step-by-step"]
>[이전](elastic-search-in-azure.md)
>[다음](application-resiliency-patterns.md)
