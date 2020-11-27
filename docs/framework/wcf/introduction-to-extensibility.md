---
title: 확장성 소개
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
ms.openlocfilehash: 8f4cc490df49a91e448c02fef370ce828536f907
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262725"
---
# <a name="introduction-to-extensibility"></a><span data-ttu-id="9cbe9-102">확장성 소개</span><span class="sxs-lookup"><span data-stu-id="9cbe9-102">Introduction to Extensibility</span></span>

<span data-ttu-id="9cbe9-103">WCF (Windows Communication Foundation) 응용 프로그램 모델은 배포 응용 프로그램의 통신 요구 사항에 대 한 더 큰 부분을 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-103">The Windows Communication Foundation (WCF) application model is designed to solve the greater part of the communication requirements of any distributed application.</span></span> <span data-ttu-id="9cbe9-104">그러나 기본 애플리케이션 모델과 시스템 제공 구현이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-104">But there are always scenarios that the default application model and system-provided implementations do not support.</span></span> <span data-ttu-id="9cbe9-105">WCF 확장성 모델은 전체 응용 프로그램 모델을 대체 하는 지점까지 모든 수준에서 시스템 동작을 수정할 수 있도록 하 여 사용자 지정 시나리오를 지원 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-105">The WCF extensibility model is intended to support custom scenarios by enabling you to modify system behavior at every level, even to the point of replacing the entire application model.</span></span> <span data-ttu-id="9cbe9-106">이 항목에서는 다양한 확장명 영역에 대해 간략하게 설명하고 각 영역에 대한 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-106">This topic outlines the various areas of extension and points to more information about each.</span></span>  
  
## <a name="areas-to-extend"></a><span data-ttu-id="9cbe9-107">확장할 영역</span><span class="sxs-lookup"><span data-stu-id="9cbe9-107">Areas to Extend</span></span>  

 <span data-ttu-id="9cbe9-108">확장 가능 영역:</span><span class="sxs-lookup"><span data-stu-id="9cbe9-108">You can extend:</span></span>  
  
- <span data-ttu-id="9cbe9-109">애플리케이션 런타임.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-109">The application runtime.</span></span> <span data-ttu-id="9cbe9-110">이 영역에서는 애플리케이션에 대한 메시지 처리 및 디스패치를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-110">This extends the dispatching and the processing of messages for the application.</span></span> <span data-ttu-id="9cbe9-111">또한 이 영역은 보안 시스템, 메타데이터 시스템, serialization 시스템 확장을 비롯하여 애플리케이션을 기본 채널 시스템에 연결하는 바인딩 및 바인딩 요소 확장을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-111">This area also includes extending the security system, the metadata system, the serialization system, and the bindings and binding elements that connect the application with the underlying channel system.</span></span>  
  
- <span data-ttu-id="9cbe9-112">채널 및 채널 런타임.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-112">The channel and channel runtime.</span></span> <span data-ttu-id="9cbe9-113">이 영역에서는 프로토콜, 전송 및 인코딩 지원을 제공하여 메시지 수준에서 작동하는 시스템을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-113">This extends the system that functions at the message level, providing protocol, transport, and encoding support.</span></span>  
  
- <span data-ttu-id="9cbe9-114">호스트 런타임.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-114">The host runtime.</span></span> <span data-ttu-id="9cbe9-115">이 영역에서는 호스트 애플리케이션 도메인과 채널 및 애플리케이션 런타임의 관계를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-115">This extends the relationship of the hosting application domain to the channel and application runtime.</span></span>  
  
### <a name="extending-the-application-runtime"></a><span data-ttu-id="9cbe9-116">애플리케이션 런타임 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-116">Extending the Application Runtime</span></span>  

 <span data-ttu-id="9cbe9-117">WCF 응용 프로그램에서는 해당 채널을 대상으로 하는 메시지와 응용 프로그램 자체를 대상으로 하는 메시지를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-117">In WCF applications, there is a distinction between messages that are destined for a corresponding channel and messages that are destined for the application itself.</span></span> <span data-ttu-id="9cbe9-118">채널 메시지는 보안 대화 설정, 신뢰할 수 있는 세션 설정과 같은 일부 채널 관련 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-118">Channel messages support some channel-related functionality, such as establishing a secure conversation or establishing a reliable session.</span></span> <span data-ttu-id="9cbe9-119">이러한 메시지는 애플리케이션 런타임에 사용할 수 없으며, 애플리케이션 계층이 포함되기 이전에 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-119">These messages are not available to the application runtime; they are processed before the application layer is involved.</span></span>  
  
 <span data-ttu-id="9cbe9-120">애플리케이션 메시지는 사용자 또는 사용자의 고객이 만든 클라이언트 또는 서비스 작업을 대상으로 하는 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-120">Application messages contain data that is destined for a client or service operation that you or your customer has created.</span></span> <span data-ttu-id="9cbe9-121">이러한 메시지는 애플리케이션 수준 확장 시스템에서 필요에 따라 메시지 또는 개체 형태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-121">These messages are available to the application-level extension system in message or object form, depending upon your needs.</span></span>  
  
 <span data-ttu-id="9cbe9-122">모든 메시지는 채널 시스템을 통해 전달되고, 애플리케이션 메시지만 채널 시스템에서 애플리케이션으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-122">All messages pass through the channel system; only application messages are passed from the channel system into the application.</span></span> <span data-ttu-id="9cbe9-123">새 채널 수준 기능을 만들려면 채널 시스템을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-123">To create new channel-level functionality, you must extend the channel system.</span></span> <span data-ttu-id="9cbe9-124">새 애플리케이션 수준 기능을 만들려면 서비스 또는 클라이언트 런타임(각각 디스패처 및 채널 팩터리)을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-124">To create new application-level functionality, you must extend the service or client runtime (dispatchers and channel factories, respectively).</span></span> <span data-ttu-id="9cbe9-125">응용 프로그램 런타임을 확장 하는 방법에 대 한 자세한 내용은 [ServiceHost 확장 및 서비스 모델 계층](./extending/extending-servicehost-and-the-service-model-layer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-125">For more information about extending the application runtime, see [Extending ServiceHost and the Service Model Layer](./extending/extending-servicehost-and-the-service-model-layer.md).</span></span>  
  
#### <a name="extending-security"></a><span data-ttu-id="9cbe9-126">보안 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-126">Extending Security</span></span>  

 <span data-ttu-id="9cbe9-127">토큰 및 자격 증명과 같은 사용자 지정 보안 메커니즘을 빌드하려면 보안 시스템을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-127">To build custom security mechanisms such as tokens and credentials, you must extend the security system.</span></span> <span data-ttu-id="9cbe9-128">자세한 내용은 [보안 확장](./extending/extending-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-128">For more information, see [Extending Security](./extending/extending-security.md).</span></span>  
  
#### <a name="extending-metadata"></a><span data-ttu-id="9cbe9-129">메타데이터 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-129">Extending Metadata</span></span>  

 <span data-ttu-id="9cbe9-130">메타데이터를 기본값과 다르게 노출하려면 메타데이터 시스템을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-130">To expose your metadata in differently than the default, you must extend the metadata system.</span></span> <span data-ttu-id="9cbe9-131">자세한 내용은 [메타 데이터 시스템 확장](./extending/extending-the-metadata-system.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-131">For more information, see [Extending the Metadata System](./extending/extending-the-metadata-system.md).</span></span>  
  
#### <a name="extending-serialization"></a><span data-ttu-id="9cbe9-132">Serialization 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-132">Extending Serialization</span></span>  

 <span data-ttu-id="9cbe9-133">사용자 지정 인코더를 빌드하거나, 데이터 서로게이트를 제공하거나, 전송된 데이터에 대한 사용자 지정과 관련된 다른 작업을 수행하려면 serialization 시스템을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-133">To build custom encoders, provide data surrogates, or other work involving the customization of transferred data, you must extend the serialization system.</span></span> <span data-ttu-id="9cbe9-134">자세한 내용은 [인코더 및 Serializer 확장](./extending/extending-encoders-and-serializers.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-134">For more information, see [Extending Encoders and Serializers](./extending/extending-encoders-and-serializers.md).</span></span>  
  
#### <a name="extending-bindings"></a><span data-ttu-id="9cbe9-135">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="9cbe9-135">Extending Bindings</span></span>  

 <span data-ttu-id="9cbe9-136">전송 또는 프로토콜 채널을 애플리케이션 계층에 연결하려면 바인딩 시스템을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-136">To associate transport or protocol channels with the application layer, you must extend the binding system.</span></span> <span data-ttu-id="9cbe9-137">자세한 내용은 [바인딩 확장](./extending/extending-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-137">For more information, see [Extending Bindings](./extending/extending-bindings.md).</span></span>  
  
### <a name="extending-the-channel-system"></a><span data-ttu-id="9cbe9-138">채널 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-138">Extending the Channel System</span></span>  

 <span data-ttu-id="9cbe9-139">사용자 지정 전송 또는 프로토콜 기능을 지 원하는 채널을 만들려면 [채널 계층 확장](./extending/extending-the-channel-layer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-139">To create channels that support custom transports or protocol functionality, see [Extending the Channel Layer](./extending/extending-the-channel-layer.md).</span></span>  
  
### <a name="extending-the-service-hosting-system"></a><span data-ttu-id="9cbe9-140">서비스 호스팅 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-140">Extending the Service Hosting System</span></span>  

 <span data-ttu-id="9cbe9-141">서비스 차원 애플리케이션 모델을 수정하려면 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 클래스를 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-141">To modify the service-wide application model, you must extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9cbe9-142">자세한 내용은 [ServiceHost 확장 및 서비스 모델 계층](./extending/extending-servicehost-and-the-service-model-layer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-142">For more information, see [Extending ServiceHost and the Service Model Layer](./extending/extending-servicehost-and-the-service-model-layer.md).</span></span>  
  
 <span data-ttu-id="9cbe9-143">호스팅 애플리케이션 도메인과 서비스 호스트 간의 관계를 수정하려면 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 클래스를 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-143">To modify the relationship between the hosting application domain and the service host, you must extend the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9cbe9-144">자세한 내용은 [ServiceHostFactory를 사용 하 여 호스팅 확장](./extending/extending-hosting-using-servicehostfactory.md)(영문)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbe9-144">For more information, see [Extending Hosting Using ServiceHostFactory](./extending/extending-hosting-using-servicehostfactory.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbe9-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cbe9-145">See also</span></span>

- [<span data-ttu-id="9cbe9-146">WCF 확장</span><span class="sxs-lookup"><span data-stu-id="9cbe9-146">Extending WCF</span></span>](./extending/index.md)
