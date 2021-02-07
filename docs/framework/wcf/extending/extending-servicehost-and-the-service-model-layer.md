---
description: '자세한 정보: ServiceHost 및 서비스 모델 계층 확장'
title: ServiceHost 및 서비스 모델 계층 확장
ms.date: 03/30/2017
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
ms.openlocfilehash: 446c02fbbb2391a4cc9c08c9e42f2194dfbcf9b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735064"
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="d1425-103">ServiceHost 및 서비스 모델 계층 확장</span><span class="sxs-lookup"><span data-stu-id="d1425-103">Extending ServiceHost and the Service Model Layer</span></span>

<span data-ttu-id="d1425-104">서비스 모델 계층은 기본 채널에서 들어오는 메시지를 끌어와서 애플리케이션 코드에서 이를 메서드 호출로 변환하여 결과를 다시 호출자에게 보내는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-104">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="d1425-105">서비스 모델 확장은 클라이언트 또는 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장명 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-105">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1425-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d1425-106">In This Section</span></span>  

 [<span data-ttu-id="d1425-107">클라이언트 확장</span><span class="sxs-lookup"><span data-stu-id="d1425-107">Extending Clients</span></span>](extending-clients.md)  
 <span data-ttu-id="d1425-108">사용자 지정 확장을 클라이언트 애플리케이션에 삽입할 수 있는 클래스뿐 아니라 클라이언트 런타임을 가로채고 수정할 수 있는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-108">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="d1425-109">예를 들어, 사용자 지정 클라이언트 메시지 로깅, 사용자 지정 메시지 serialization 등을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-109">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="d1425-110">디스패처 확장</span><span class="sxs-lookup"><span data-stu-id="d1425-110">Extending Dispatchers</span></span>](extending-dispatchers.md)  
 <span data-ttu-id="d1425-111">사용자 지정 확장을 서비스 애플리케이션에 삽입할 수 있는 클래스뿐 아니라 서비스 런타임을 가로채고 수정할 수 있는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-111">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="d1425-112">예를 들어, 사용자 지정 서비스 로깅, 서비스 측 메시지 유효성 검사, 사용자 지정 디스패치 등을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-112">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="d1425-113">확장 가능한 개체</span><span class="sxs-lookup"><span data-stu-id="d1425-113">Extensible Objects</span></span>](extensible-objects.md)  
 <span data-ttu-id="d1425-114">5개의 확장 가능한 개체 및 <xref:System.ServiceModel.IExtensibleObject%601> 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-114">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="d1425-115">새 기능과 함께 기존 런타임 클래스를 확장하거나 새 상태를 개체에 추가하기 위해 확장명 가능한 개체 패턴이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-115">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="d1425-116">확장명 가능한 개체 중 하나에 연결된 확장은 이 개체에서 액세스할 수 있는 확장명 가능한 일반 개체에 연결된 공유 상태 및 기능에 액세스하는 처리 시에 매우 다른 단계에서 동작을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-116">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="d1425-117">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="d1425-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="d1425-118">WCF 런타임에서 설정을 변경 하거나 확장을 삽입 하려면 동작을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-118">To change settings on or insert extensions in the WCF runtime, you use Behaviors.</span></span> <span data-ttu-id="d1425-119">WCF에는 스로틀, 인스턴스 만들기 그리고 서비스 및 작업의 여러 사항을 제어하기 위한 시스템 구현 동작이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-119">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="d1425-120">이 단원에서는 사용자 지정 동작을 만드는 방법 및 프로그램 방식과 구성 파일을 사용하여 해당 동작을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-120">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="d1425-121">ServiceHostFactory를 사용하여 호스팅 확장명</span><span class="sxs-lookup"><span data-stu-id="d1425-121">Extending Hosting Using ServiceHostFactory</span></span>](extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="d1425-122"><xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>와 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>를 확장하는 방법 및 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 클래스를 사용하여 호스트 환경을 사용자 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1425-122">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d1425-123">참고</span><span class="sxs-lookup"><span data-stu-id="d1425-123">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1425-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d1425-124">Related Sections</span></span>
