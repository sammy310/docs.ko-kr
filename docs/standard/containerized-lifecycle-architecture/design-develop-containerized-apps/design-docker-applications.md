---
title: Docker 애플리케이션 설계
description: 여기에서 찾을 하 여 마이크로 서비스 아키텍처에 대 한 참조 항목 이므로이 가이드에서 자세히 설명 하지 것입니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1d49f7509c0a12edfe375486429147e8fd240b2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799348"
---
# <a name="design-docker-applications"></a>Docker 애플리케이션 설계

1 장 컨테이너 및 Docker에 대 한 기본 개념을 도입 합니다. 해당 정보는 기본 수준의 시작 하는 데 필요한 정보입니다. 그러나 복잡 하 고 단일 서비스 또는 컨테이너 대신 여러 서비스로 구성 된 엔터프라이즈 응용 프로그램 수 있습니다. 이러한 선택적 사용 사례에 대 한 추가 접근 방법을 위해 알아야 디자인, 서비스 지향 아키텍처 (SOA)와 같은 고급 마이크로 서비스 개념 및 컨테이너 오케스트레이션 개념과 해야 합니다. 이 문서의 범위를 마이크로 서비스로 제한 되지 않지만 모든 Docker 응용 프로그램 수명 주기를 따라서 것은 탐색 방어에서 마이크로 서비스 아키텍처도 일반 SOA, 백그라운드 작업 또는 작업을 사용 하 여 컨테이너 및 Docker를 사용 하거나도 하기 때문에 모놀리식 응용 프로그램 배포 방법입니다.

**자세한 내용은** 엔터프라이즈 응용 프로그램 및 마이크로 서비스 아키텍처 방어에서 하는 방법에 대 한 자세한 내용은 가이드를 읽기 [NET 마이크로 서비스: 컨테이너 화 된.NET 응용 프로그램 아키텍처](../../microservices-architecture/index.md) 에서 다운로드할 수도 있습니다는 <https://aka.ms/MicroservicesEbook>합니다.

그러나 응용 프로그램 수명 주기 및 DevOps를 시작 하기 전에 반드시을 디자인 하는 방법을 알고 있어야 하며 응용 프로그램 및 디자인 선택 항목을 생성 합니다.

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](common-container-design-principles.md)