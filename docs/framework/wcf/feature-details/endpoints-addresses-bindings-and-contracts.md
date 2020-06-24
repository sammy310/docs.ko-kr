---
title: '엔드포인트: 주소, 바인딩 및 계약'
description: 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 하는 서비스 끝점을 통해 WCF 서비스와의 모든 통신을 수행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247314"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="3ad4d-103">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="3ad4d-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="3ad4d-104">WCF (Windows Communication Foundation) 서비스와의 모든 통신은 서비스의 *끝점* 을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="3ad4d-105">끝점은 WCF 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="3ad4d-106">각 엔드포인트는 다음 네 가지 속성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="3ad4d-107">엔드포인트를 찾을 위치를 나타내는 주소</span><span class="sxs-lookup"><span data-stu-id="3ad4d-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="3ad4d-108">클라이언트가 엔드포인트와 통신할 수 있는 방법을 지정하는 바인딩</span><span class="sxs-lookup"><span data-stu-id="3ad4d-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="3ad4d-109">사용 가능한 작업을 식별하는 계약</span><span class="sxs-lookup"><span data-stu-id="3ad4d-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="3ad4d-110">엔드포인트의 로컬 구현 세부 정보를 지정하는 동작 집합</span><span class="sxs-lookup"><span data-stu-id="3ad4d-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="3ad4d-111">이 항목에서는이 끝점 구조에 대해 설명 하 고 WCF 개체 모델에 표시 되는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="3ad4d-112">엔드포인트의 구조</span><span class="sxs-lookup"><span data-stu-id="3ad4d-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="3ad4d-113">각 엔드포인트는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="3ad4d-114">주소: 주소는 엔드포인트를 고유하게 식별하고 잠재 고객에게 서비스가 있는 위치를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="3ad4d-115">클래스에 의해 WCF 개체 모델에 표시 됩니다 <xref:System.ServiceModel.EndpointAddress> .</span><span class="sxs-lookup"><span data-stu-id="3ad4d-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="3ad4d-116"><xref:System.ServiceModel.EndpointAddress> 클래스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="3ad4d-117">서비스의 주소를 나타내는 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="3ad4d-118">서비스의 보안 ID 및 선택적 메시지 헤더의 컬렉션을 나타내는 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="3ad4d-119">선택적 메시지 헤더는 엔드포인트 확인 및 엔드포인트와의 상호 작용을 위해 자세한 추가 주소 지정 정보를 제공하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="3ad4d-120">자세한 내용은 [끝점 주소 지정](../specifying-an-endpoint-address.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="3ad4d-121">바인딩: 바인딩은 엔드포인트와 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="3ad4d-122">다음 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-122">This includes:</span></span>

  - <span data-ttu-id="3ad4d-123">사용할 전송 프로토콜(예: TCP 또는 HTTP)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="3ad4d-124">메시지에 사용할 인코딩(예: 텍스트 또는 이진)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="3ad4d-125">필요한 보안 요구 사항(예: SSL 또는 SOAP 메시지 보안)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="3ad4d-126">자세한 내용은 [WCF 바인딩 개요](../bindings-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="3ad4d-127">바인딩은 WCF 개체 모델에서 추상 기본 클래스로 표현 됩니다 <xref:System.ServiceModel.Channels.Binding> .</span><span class="sxs-lookup"><span data-stu-id="3ad4d-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="3ad4d-128">대부분의 시나리오의 경우 사용자는 시스템 제공 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="3ad4d-129">자세한 내용은 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="3ad4d-130">계약: 계약에서는 엔드포인트가 클라이언트에 노출하는 기능을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="3ad4d-131">계약에서는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-131">A contract specifies:</span></span>

  - <span data-ttu-id="3ad4d-132">클라이언트가 호출할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="3ad4d-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="3ad4d-133">메시지 형식</span><span class="sxs-lookup"><span data-stu-id="3ad4d-133">The form of the message.</span></span>

  - <span data-ttu-id="3ad4d-134">작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3ad4d-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="3ad4d-135">클라이언트가 예상할 수 있는 처리 또는 응답 메시지 형식</span><span class="sxs-lookup"><span data-stu-id="3ad4d-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="3ad4d-136">계약을 정의 하는 방법에 대 한 자세한 내용은 [서비스 계약 디자인](../designing-service-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="3ad4d-137">동작: 엔드포인트 동작을 사용하여 서비스 엔드포인트의 로컬 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="3ad4d-138">끝점 동작은 WCF 런타임 빌드 프로세스에 참여 하 여이를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="3ad4d-139">엔드포인트 동작의 예는 <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> 속성이며, 이 속성을 사용하여 SOAP 또는 WSDL(웹 서비스 기술 언어) 주소 이외의 다른 수신 대기 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="3ad4d-140">자세한 내용은 [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="3ad4d-141">엔드포인트 정의</span><span class="sxs-lookup"><span data-stu-id="3ad4d-141">Defining Endpoints</span></span>

<span data-ttu-id="3ad4d-142">구성을 통해 코드를 명령적으로 또는 선언적으로 사용하여 서비스의 엔드포인트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="3ad4d-143">자세한 내용은 [방법: 구성에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-configuration.md) 및 [방법: 코드에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-code.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ad4d-144">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3ad4d-144">In This Section</span></span>

<span data-ttu-id="3ad4d-145">이 단원에서는 바인딩, 엔드포인트 및 주소의 용도에 대해 설명하고 바인딩 및 엔드포인트를 구성하는 방법과 `ClientVia` 동작 및 `ListenUri` 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="3ad4d-146">[주소로](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="3ad4d-147">WCF에서 끝점의 주소를 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="3ad4d-148">[바인딩하](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="3ad4d-149">바인딩을 사용하여 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="3ad4d-150">[계약은](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="3ad4d-151">계약이 서비스 메서드를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="3ad4d-152">[방법: 구성에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="3ad4d-153">구성에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="3ad4d-154">[방법: 코드에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="3ad4d-155">코드에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="3ad4d-156">[방법: Svcutil.exe를 사용 하 여 컴파일된 서비스 코드 유효성 검사](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="3ad4d-157">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용 하 여 서비스를 호스팅하지 않고 서비스 구현 및 구성에서 오류를 검색 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ad4d-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ad4d-158">See also</span></span>

- [<span data-ttu-id="3ad4d-159">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="3ad4d-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="3ad4d-160">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="3ad4d-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
