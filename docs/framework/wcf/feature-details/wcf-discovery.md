---
description: '자세한 정보: WCF 검색'
title: WCF 검색
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 67fa5800209676b11e9e49171483bf514b6a190a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779636"
---
# <a name="wcf-discovery"></a><span data-ttu-id="ccd62-103">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="ccd62-103">WCF Discovery</span></span>

<span data-ttu-id="ccd62-104">WCF (Windows Communication Foundation)는 WS-Discovery 프로토콜을 사용 하 여 상호 운용 가능한 방식으로 런타임에 서비스를 검색할 수 있도록 지 원하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-104">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="ccd62-105">WCF 서비스는 멀티 캐스트 메시지 또는 검색 프록시 서버를 사용 하 여 네트워크에 대 한 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-105">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="ccd62-106">클라이언트 애플리케이션은 네트워크나 검색 프록시 서버를 검색하여 일련의 조건을 만족하는 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-106">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="ccd62-107">이 단원의 항목에서는 이 기능의 프로그램 모델에 대한 개요와 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-107">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccd62-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ccd62-108">In This Section</span></span>  

 [<span data-ttu-id="ccd62-109">WCF Discovery 개요</span><span class="sxs-lookup"><span data-stu-id="ccd62-109">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="ccd62-110">WCF에서 제공 하는 WS-Discovery 지원에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-110">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="ccd62-111">WCF Discovery 개체 모델</span><span class="sxs-lookup"><span data-stu-id="ccd62-111">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="ccd62-112">개체 모델의 클래스와 WS-Discovery 지원의 확장성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-112">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="ccd62-113">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="ccd62-113">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="ccd62-114">WCF (Windows Communication Foundation) 서비스를 검색할 수 있도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-114">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="ccd62-115">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="ccd62-115">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="ccd62-116">검색 프록시, 검색 프록시에 등록할 검색 가능한 서비스 및 검색 프록시를 사용하여 검색 가능한 서비스를 찾는 클라이언트를 구현하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-116">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="ccd62-117">검색 버전 관리</span><span class="sxs-lookup"><span data-stu-id="ccd62-117">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="ccd62-118">일부 새 검색 기능의 프로토타입 구현에 대해 간략하게 설명하고</span><span class="sxs-lookup"><span data-stu-id="ccd62-118">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="ccd62-119">사용할 검색 버전을 선택하는 방법에 대해서도 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-119">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="ccd62-120">구성 파일에서 검색 구성</span><span class="sxs-lookup"><span data-stu-id="ccd62-120">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="ccd62-121">구성에서 검색을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-121">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="ccd62-122">Discovery 클라이언트 채널 사용</span><span class="sxs-lookup"><span data-stu-id="ccd62-122">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="ccd62-123">WCF 클라이언트 응용 프로그램을 작성할 때 검색 클라이언트 채널을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccd62-123">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
