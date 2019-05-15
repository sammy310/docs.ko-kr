---
title: SOA 응용 프로그램
description: 컨테이너 SOA 응용 프로그램에 대 한 유용한 배포 옵션을 또한 수 있음을 염두에 두어야 합니다.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644756"
---
# <a name="service-oriented-applications"></a>서비스 지향 응용 프로그램

서비스 지향 아키텍처 (SOA) 다른 사람에 게 서로 다른 많은 요소를 의미 하는 남용된 용어를 했습니다. 하지만 공통 분모로 SOA (가장 일반적으로 HTTP 서비스) 하위 시스템 같은 다른 형식 또는 다른 경우 계층으로 분류할 수 있는 몇 가지 서비스를 분해 하 여 응용 프로그램의 아키텍처를 구성 하는 의미 합니다.

현재 컨테이너 이미지에 포함 된 모든 종속성 때문에 배포 관련 문제를 해결 하는 Docker 컨테이너로 해당 서비스를 배포할 수 있습니다. 그러나 Soa를 확장 해야 할 경우에 따라 단일 인스턴스를 배포 하는 경우 문제가 발생할 수 있습니다. Docker 클러스터링 소프트웨어 또는 오 케 스트레이 터를 사용 하 여이 문제를 처리할 수 있습니다. 살펴보겠습니다 다음 섹션에서 자세히 오 케 스트레이 터 경우 마이크로 서비스 접근 방식을 살펴봅니다.

Docker 컨테이너는 기존의 서비스 지향 아키텍처와 보다 발전된 마이크로 서비스 아키텍처 모두에 유용합니다(하지만 필수는 아님).

하루 끝 컨테이너 클러스터링 솔루션은 및 각 마이크로 서비스는 해당 데이터 모델을 소유 하는 고급 마이크로 서비스 아키텍처는 기존의 SOA 아키텍처에 유용 합니다. 및 덕분 여러 데이터베이스도 확장할 수 있습니다 SOA 서비스에서 공유 하는 모놀리식 데이터베이스와 함께 작업 하는 대신 데이터 계층입니다. 그러나 데이터를 분할 하는 방법에 대 한 토론 순수 하 게에 대 한 아키텍처 및 디자인 됩니다.

>[!div class="step-by-step"]
>[이전](state-and-data-in-docker-applications.md)
>[다음](orchestrate-high-scalability-availability.md)
