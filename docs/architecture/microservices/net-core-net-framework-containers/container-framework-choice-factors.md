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
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="39603-104">의사 결정 테이블: Docker에 사용할 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="39603-105">다음 의사 결정 테이블에서는 .NET Framework 또는 .NET Core를 사용 할지 여부를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-105">The following decision table summarizes whether to use .NET Framework or .NET Core.</span></span> <span data-ttu-id="39603-106">Linux 컨테이너의 경우 Linux 기반 Docker 호스트(VM 또는 서버)가 필요하고, Windows 컨테이너의 경우 Windows Server 기반 Docker 호스트(VM 또는 서버)가 필요하다는 사실을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39603-107">개발 컴퓨터에서 Docker 호스트(Linux 또는 Windows)를 하나 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-107">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="39603-108">한 솔루션에서 함께 실행하고 테스트할 관련 마이크로 서비스가 전부 동일한 컨테이너 플랫폼에서 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-108">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="39603-109"><strong>아키텍처/앱 형식</strong></span><span class="sxs-lookup"><span data-stu-id="39603-109"><strong>Architecture / App Type</strong></span></span></th>
<th><span data-ttu-id="39603-110"><strong>Linux 컨테이너</strong></span><span class="sxs-lookup"><span data-stu-id="39603-110"><strong>Linux containers</strong></span></span></th>
<th><span data-ttu-id="39603-111"><strong>Windows 컨테이너</strong></span><span class="sxs-lookup"><span data-stu-id="39603-111"><strong>Windows Containers</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="39603-112">컨테이너의 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="39603-112">Microservices on containers</span></span></td>
<td><span data-ttu-id="39603-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-113">.NET Core</span></span></td>
<td><span data-ttu-id="39603-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-114">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39603-115">모놀리식 앱</span><span class="sxs-lookup"><span data-stu-id="39603-115">Monolithic app</span></span></td>
<td><span data-ttu-id="39603-116">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-116">.NET Core</span></span></td>
<td><p><span data-ttu-id="39603-117">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-117">.NET Framework</span></span></p>
<p><span data-ttu-id="39603-118">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-118">.NET Core</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39603-119">최고의 성능 및 확장성</span><span class="sxs-lookup"><span data-stu-id="39603-119">Best-in-class performance and scalability</span></span></td>
<td><span data-ttu-id="39603-120">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-120">.NET Core</span></span></td>
<td><span data-ttu-id="39603-121">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-121">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39603-122">컨테이너에 대한 Windows Server 레거시 앱(“갈색 필드”) 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="39603-122">Windows Server legacy app ("brown-field") migration to containers</span></span></td>
<td>--</td>
<td><span data-ttu-id="39603-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-123">.NET Framework</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39603-124">새 컨테이너 기반 개발(“녹색 필드”)</span><span class="sxs-lookup"><span data-stu-id="39603-124">New container-based development ("green-field")</span></span></td>
<td><span data-ttu-id="39603-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-125">.NET Core</span></span></td>
<td><span data-ttu-id="39603-126">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-126">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39603-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-127">ASP.NET Core</span></span></td>
<td><span data-ttu-id="39603-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-128">.NET Core</span></span></td>
<td><p><span data-ttu-id="39603-129">.NET Core(권장)</span><span class="sxs-lookup"><span data-stu-id="39603-129">.NET Core (recommended)</span></span></p>
<p><span data-ttu-id="39603-130">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-130">.NET Framework</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39603-131">ASP.NET 4(MVC 5, Web API 2 및 Web Forms)</span><span class="sxs-lookup"><span data-stu-id="39603-131">ASP.NET 4 (MVC 5, Web API 2, and Web Forms)</span></span></td>
<td>--</td>
<td><span data-ttu-id="39603-132">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-132">.NET Framework</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39603-133">SignalR 서비스</span><span class="sxs-lookup"><span data-stu-id="39603-133">SignalR services</span></span></td>
<td><span data-ttu-id="39603-134">.NET Core 2.1 이상 버전</span><span class="sxs-lookup"><span data-stu-id="39603-134">.NET Core 2.1 or higher version</span></span></td>
<td><p><span data-ttu-id="39603-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-135">.NET Framework</span></span></p>
<p><span data-ttu-id="39603-136">.NET Core 2.1 이상 버전</span><span class="sxs-lookup"><span data-stu-id="39603-136">.NET Core 2.1 or higher version</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39603-137">WCF, WF 및 기타 레거시 프레임워크</span><span class="sxs-lookup"><span data-stu-id="39603-137">WCF, WF, and other legacy frameworks</span></span></td>
<td><span data-ttu-id="39603-138">.NET Core의 WCF(WCF 클라이언트 라이브러리만)</span><span class="sxs-lookup"><span data-stu-id="39603-138">WCF in .NET Core (only the WCF client library)</span></span></td>
<td><p><span data-ttu-id="39603-139">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-139">.NET Framework</span></span></p>
<p><span data-ttu-id="39603-140">.NET Core의 WCF(WCF 클라이언트 라이브러리만)</span><span class="sxs-lookup"><span data-stu-id="39603-140">WCF in .NET Core (only the WCF client library)</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39603-141">Azure 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="39603-141">Consumption of Azure services</span></span></td>
<td><p><span data-ttu-id="39603-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-142">.NET Core</span></span></p>
<p><span data-ttu-id="39603-143">(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)</span><span class="sxs-lookup"><span data-stu-id="39603-143">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
<td><p><span data-ttu-id="39603-144">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="39603-144">.NET Framework</span></span></p>
<p><span data-ttu-id="39603-145">.NET Core</span><span class="sxs-lookup"><span data-stu-id="39603-145">.NET Core</span></span></p>
<p><span data-ttu-id="39603-146">(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)</span><span class="sxs-lookup"><span data-stu-id="39603-146">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
><span data-ttu-id="39603-147">[이전](net-framework-container-scenarios.md)
>[다음](net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="39603-147">[Previous](net-framework-container-scenarios.md)
[Next](net-container-os-targets.md)</span></span>
