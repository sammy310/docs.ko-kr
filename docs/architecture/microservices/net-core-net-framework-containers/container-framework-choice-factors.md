---
title: 의사 결정 테이블. Docker에 사용할 .NET Framework
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | 의사 결정 테이블, Docker에 사용할 .NET Framework
ms.date: 01/13/2021
ms.openlocfilehash: 35f101b3f4030e081068677b3754363bf6cd8210
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188662"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>의사 결정 테이블: Docker에 사용할 .NET Framework

다음 의사 결정 테이블에서는 .NET Framework 또는 .NET 5를 사용할지 여부를 간략히 설명합니다. Linux 컨테이너의 경우 Linux 기반 Docker 호스트(VM 또는 서버)가 필요하고, Windows 컨테이너의 경우 Windows Server 기반 Docker 호스트(VM 또는 서버)가 필요하다는 사실을 기억해야 합니다.

> [!IMPORTANT]
> 개발 컴퓨터에서 Docker 호스트(Linux 또는 Windows)를 하나 실행해야 합니다. 한 솔루션에서 함께 실행하고 테스트할 관련 마이크로 서비스가 전부 동일한 컨테이너 플랫폼에서 실행되어야 합니다.

| 아키텍처/앱 형식 | Linux 컨테이너 | Windows 컨테이너 |
|-------------------------|------------------|--------------------|
| 컨테이너의 마이크로 서비스 | .NET 5 | .NET 5 |
| 모놀리식 앱 | .NET 5 | .NET Framework <br/> .NET 5 |
| 최고의 성능 및 확장성 | .NET 5 | .NET 5 |
| 컨테이너에 대한 Windows Server 레거시 앱(“갈색 필드”) 마이그레이션 | -- | .NET Framework |
| 새 컨테이너 기반 개발(“녹색 필드”) | .NET 5 | .NET 5 |
| ASP.NET Core | .NET 5 | .NET 5(권장) <br/> .NET Framework |
| ASP.NET 4(MVC 5, Web API 2 및 Web Forms) | -- | .NET Framework |
| SignalR 서비스 | .NET Core 2.1 이상 버전 | .NET Framework <br/> .NET Core 2.1 이상 버전 |
| WCF, WF 및 기타 레거시 프레임워크 | .NET Core의 WCF(클라이언트 라이브러리 전용) | .NET Framework <br/> .NET 5의 WCF(클라이언트 라이브러리 전용) |
| Azure 서비스 사용 | .NET 5 <br/> (궁극적으로 대부분 Azure 서비스에서 .NET 5용 클라이언트 SDK를 제공할 예정) | .NET Framework <br/> .NET 5 <br/> (궁극적으로 대부분 Azure 서비스에서 .NET 5용 클라이언트 SDK를 제공할 예정) |

>[!div class="step-by-step"]
>[이전](net-framework-container-scenarios.md)
>[다음](net-container-os-targets.md)
