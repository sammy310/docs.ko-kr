---
title: 의사 결정 테이블. Docker에 사용할 .NET Framework
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | 의사 결정 테이블, Docker에 사용할 .NET Framework
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675820"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>의사 결정 테이블: Docker에 사용할 .NET Framework

다음 의사 결정 테이블에서는 .NET Framework 또는 .NET Core를 사용 할지 여부를 간략하게 설명합니다. Linux 컨테이너의 경우 Linux 기반 Docker 호스트(VM 또는 서버)가 필요하고, Windows 컨테이너의 경우 Windows Server 기반 Docker 호스트(VM 또는 서버)가 필요하다는 사실을 기억해야 합니다.

> [!IMPORTANT]
> 개발 컴퓨터에서 Docker 호스트(Linux 또는 Windows)를 하나 실행해야 합니다. 한 솔루션에서 함께 실행하고 테스트할 관련 마이크로 서비스가 전부 동일한 컨테이너 플랫폼에서 실행되어야 합니다.

<table>
<thead>
<tr class="header">
<th><strong>아키텍처/앱 형식</strong></th>
<th><strong>Linux 컨테이너</strong></th>
<th><strong>Windows 컨테이너</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>컨테이너의 마이크로 서비스</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>모놀리식 앱</td>
<td>.NET Core</td>
<td><p>.NET Framework</p>
<p>.NET Core</p></td>
</tr>
<tr class="odd">
<td>최고의 성능 및 확장성</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>컨테이너에 대한 Windows Server 레거시 앱(“갈색 필드”) 마이그레이션</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="odd">
<td>새 컨테이너 기반 개발(“녹색 필드”)</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>ASP.NET Core</td>
<td>.NET Core</td>
<td><p>.NET Core(권장)</p>
<p>.NET Framework</p></td>
</tr>
<tr class="odd">
<td>ASP.NET 4(MVC 5, Web API 2 및 Web Forms)</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="even">
<td>SignalR 서비스</td>
<td>.NET Core 2.1 이상 버전</td>
<td><p>.NET Framework</p>
<p>.NET Core 2.1 이상 버전</p></td>
</tr>
<tr class="odd">
<td>WCF, WF 및 기타 레거시 프레임워크</td>
<td>.NET Core의 WCF(WCF 클라이언트 라이브러리만)</td>
<td><p>.NET Framework</p>
<p>.NET Core의 WCF(WCF 클라이언트 라이브러리만)</p></td>
</tr>
<tr class="even">
<td>Azure 서비스 사용</td>
<td><p>.NET Core</p>
<p>(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)</p></td>
<td><p>.NET Framework</p>
<p>.NET Core</p>
<p>(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)</p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[이전](net-framework-container-scenarios.md)
>[다음](net-container-os-targets.md)
