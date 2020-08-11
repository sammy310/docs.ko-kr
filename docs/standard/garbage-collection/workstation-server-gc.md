---
title: 워크스테이션 및 서버 GC(가비지 수집)
description: .NET에서 워크스테이션 및 서버 가비지 수집에 대해 알아봅니다.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 640b5f42c1f841c2537284e4721e827248e3d300
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87917015"
---
# <a name="workstation-and-server-garbage-collection"></a>워크스테이션 및 서버 가비지 수집

가비지 수집기는 자체 조정되며 다양한 시나리오에서 작동 가능합니다. 그러나 워크로드의 특성에 따라 [가비지 수집 형식을 설정](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection)할 수 있습니다. CLR은 다음 유형의 가비지 수집을 제공합니다.

- 워크스테이션 GC(가비지 수집)는 클라이언트 앱용으로 설계되었습니다. 독립 실행형 앱의 기본 GC 버전입니다. 호스트된 앱(예: ASP.NET에서 호스트된 앱)의 경우, 호스트는 기본 GC 버전을 결정합니다.

  워크스테이션 가비지 수집은 동시 수집 또는 비동시 수집일 수 있습니다. 동시(또는 *백그라운드*) 가비지 수집을 통해 가비지 수집 중 관리되는 스레드가 작업을 계속 수행할 수 있습니다. [백그라운드 가비지 수집](background-gc.md)이 .NET Framework 4 이상 버전에서 [동시 가비지 수집](background-gc.md#concurrent-garbage-collection)을 대체합니다.

- 높은 처리 속도 및 확장성이 필요한 서버 애플리케이션을 위한 서버 가비지 수집

  - .NET Core에서 서버 가비지 수집은 비동시 또는 백그라운드 작업일 수 있습니다.

  - .NET Framework 4.5 이상 버전에서 서버 가비지 수집은 비동시 또는 백그라운드 작업일 수 있습니다. .NET Framework 4 이전 버전에서는, 서버 가비지 수집이 동시에 수행되지 않습니다.

다음 그림에서는 서버에서 가비지 수집을 수행하는 전용 스레드를 보여 줍니다.

![서버 가비지 수집 스레드](media/gc-server.png)

## <a name="performance-considerations"></a>성능 고려 사항

### <a name="workstation-gc"></a>워크스테이션 GC

다음은 워크스테이션 가비지 수집 시 고려해야 하는 스레딩 및 성능 고려 사항입니다.

- 수집은 가비지 수집을 트리거한 사용자 스레드에서 발생하여 동일한 우선 순위를 유지합니다. 사용자 스레드는 일반적으로 보통 우선 순위로 실행되므로 보통 우선 순위 스레드에서 실행되는 가비지 수집기는 다른 스레드와 CPU 시간을 두고 경쟁해야 합니다. (네이티브 코드를 실행하는 스레드는 서버 또는 워크스테이션 가비지 수집에서 일시 중단되지 않습니다.)

- 프로세서가 하나뿐인 컴퓨터에서는 [구성 설정](../../core/run-time-config/garbage-collector.md#workstation-vs-server)에 관계없이 항상 워크스테이션 가비지 수집이 사용됩니다.

### <a name="server-gc"></a>서버 GC

다음은 서버 가비지 수집 시 고려해야 할 스레딩 및 성능 고려 사항입니다.

- 수집은 `THREAD_PRIORITY_HIGHEST` 우선 순위 수준에서 실행되는 여러 전용 스레드에서 발생합니다.

- 힙과 가비지 수집을 수행하기 위한 전용 스레드가 각 CPU에 제공되며, 힙은 동시에 수집됩니다. 각 힙에는 소형 개체 힙과 대형 개체 힙이 포함되며 모든 힙은 사용자 코드에서 액세스할 수 있습니다. 서로 다른 힙의 개체는 상호 참조할 수 있습니다.

- 여러 가비지 수집 스레드가 함께 작동하므로 같은 크기의 힙에서 서버 가비지 수집이 워크스테이션 가비지 수집에 비해 더 빠릅니다.

- 서버 가비지 수집은 세그먼트가 큰 경우가 많습니다. 그러나 이는 일반적인 경우일 뿐입니다. 세그먼트 크기는 구현에 따라 다르며 변경될 수 있습니다. 앱을 조정할 때 가비지 수집기에서 할당되는 세그먼트 크기를 가정하지 마세요.

- 서버 가비지 수집은 많은 리소스를 소비할 수 있습니다. 예를 들어, 프로세서가 4개인 컴퓨터에서 실행되는 서버 GC를 사용하는 12개의 프로세스가 있다고 가정합니다. 모든 프로세스가 동시에 가비지 수집에 발생하는 경우, 동일한 프로세서에 12개의 스레드가 예약되므로 서로 방해하게 됩니다. 프로세스가 활성 상태인 경우 모든 프로세스에서 서버 GC를 사용하는 것은 좋지 않습니다.

수백 개의 애플리케이션 인스턴스를 실행하는 경우 동시 가비지 수집이 사용하지 않도록 설정된 워크스테이션 가비지 수집을 사용할 수 있습니다. 이렇게 하면 컨텍스트 전환이 줄어들어 성능이 향상됩니다.

## <a name="see-also"></a>참조

- [백그라운드 가비지 수집](background-gc.md)
- [가비지 수집을 위한 런타임 구성 옵션](../../core/run-time-config/garbage-collector.md)
