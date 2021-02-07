---
description: '자세한 정보: 검색 버전 관리'
title: 검색 버전 관리
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 075fefce0477810336c8b857343984070ed89b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743189"
---
# <a name="discovery-versioning"></a><span data-ttu-id="bff70-103">검색 버전 관리</span><span class="sxs-lookup"><span data-stu-id="bff70-103">Discovery Versioning</span></span>

<span data-ttu-id="bff70-104">이 항목에서는 일부 새 검색 기능의 구현에 대해 간략하게 설명하고</span><span class="sxs-lookup"><span data-stu-id="bff70-104">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="bff70-105">사용할 검색 버전을 선택하는 방법에 대해서도 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-105">It also gives an overview on how to select the discovery version to use.</span></span>

## <a name="discovery-versioning"></a><span data-ttu-id="bff70-106">검색 버전 관리</span><span class="sxs-lookup"><span data-stu-id="bff70-106">Discovery Versioning</span></span>

<span data-ttu-id="bff70-107">검색 기능은 세 가지 버전의 WS_Discovery 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-107">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="bff70-108">검색 API를 사용하면 사용할 프로토콜 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-108">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="bff70-109">이 문서에서는 버전 관리 관련 설정에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-109">This document briefly describes the versioning-related settings.</span></span>

<span data-ttu-id="bff70-110">다음은 <xref:System.ServiceModel.Discovery.DiscoveryVersion> 속성을 포함하고 있고 해당 생성자에 <xref:System.ServiceModel.Discovery.DiscoveryVersion> 인수를 사용하는 검색 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-110">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>

### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="bff70-111">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="bff70-111">DiscoveryVersion.WSDiscoveryApril2005</span></span>

<span data-ttu-id="bff70-112">를 <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> 생성자 매개 변수로 제공 하면 구현 시 WS-Discovery 프로토콜의 April2005 버전이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-112">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="bff70-113">이 버전은 WS-Discovery 프로토콜 사양의 게시된 버전에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-113">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="bff70-114">WS-Discovery의 April2005 버전을 사용하는 레거시 애플리케이션과 상호 운용하려면 이 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-114">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>

### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="bff70-115">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="bff70-115">DiscoveryVersion.WSDiscovery11</span></span>

<span data-ttu-id="bff70-116">Api에서 사용 하는 기본 검색 버전은 <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11> 입니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-116">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="bff70-117">이 버전은 WS-Discovery 프로토콜의 현재 표준화된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-117">This is the current standardized version of the WS-Discovery protocol.</span></span>

## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="bff70-118">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="bff70-118">DiscoveryVersion.WSDiscoveryCD1</span></span>

<span data-ttu-id="bff70-119"><xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1>을 생성자 매개 변수로 제공하면 구현 시 WS-Discovery 프로토콜의 committee draft 1 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-119">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="bff70-120">WS-Discovery 프로토콜의 CD1 버전을 실행하는 구현과 상호 운용하려면 이 버전의 프로토콜을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-120">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>

## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="bff70-121">단일 서비스 호스트에서 다양한 검색 버전에 대해 여러 개의 UDP 검색 엔드포인트 지원</span><span class="sxs-lookup"><span data-stu-id="bff70-121">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>

<span data-ttu-id="bff70-122">단일 서비스 호스트에서 다양한 검색 버전에 대해 여러 개의 UDP 검색 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-122">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="bff70-123">이렇게 하려면 각 UDP 검색 엔드포인트에 고유한 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-123">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="bff70-124">다음 예제에 이 작업을 수행하는 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff70-124">The following example shows how to do this.</span></span>

```csharp
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);

newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionApril2005");

serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);
```
