---
title: Windows Communication Foundation 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: fd6b942dcabad07feda81af63bde23d3b663ce0f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587614"
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="1b254-102">Windows Communication Foundation 바인딩</span><span class="sxs-lookup"><span data-stu-id="1b254-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="1b254-103">WCF (Windows Communication Foundation)는 다른 소프트웨어와 통신 하는 방식에서 응용 프로그램에 대 한 소프트웨어를 작성 하는 방법을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-103">Windows Communication Foundation (WCF) separates how the software for an application is written from how it communicates with other software.</span></span> <span data-ttu-id="1b254-104">바인딩은 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-104">Bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span> <span data-ttu-id="1b254-105">WCF는 바인딩을 사용 하 여 끝점의 기본 연결 표현을 생성 하므로 통신 하는 당사자가 대부분의 바인딩 세부 정보에 동의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-105">WCF uses bindings to generate the underlying wire representation of the endpoint, so most of the binding details must be agreed upon by the parties that are communicating.</span></span> <span data-ttu-id="1b254-106">이를 수행하는 가장 쉬운 방법은 서비스 클라이언트가 서비스 엔드포인트에서 사용하는 동일한 바인딩을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-106">The easiest way to achieve this is for clients of a service to use the same binding that the endpoint for the service uses.</span></span> <span data-ttu-id="1b254-107">이 작업을 수행 하는 방법에 대 한 자세한 내용은 [바인딩을 사용 하 여 서비스 및 클라이언트 구성](../using-bindings-to-configure-services-and-clients.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b254-107">For more information about how to do this, see [Using Bindings to Configure Services and Clients](../using-bindings-to-configure-services-and-clients.md).</span></span>  
  
 <span data-ttu-id="1b254-108">바인딩은 바인딩 요소의 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-108">A binding is made up of a collection of binding elements.</span></span> <span data-ttu-id="1b254-109">각 요소는 엔드포인트가 클라이언트와 통신하는 방법의 일부를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-109">Each element describes some aspect of how the endpoint communicates with clients.</span></span> <span data-ttu-id="1b254-110">바인딩에는 하나 이상의 전송 바인딩 요소, 전송 바인딩 요소가 기본적으로 제공할 수 있는 하나 이상의 메시지 인코딩 바인딩 요소 및 여러 개의 다른 프로토콜 바인딩 요소가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-110">A binding must include at least one transport binding element, at least one message-encoding binding element (which the transport binding element can provide by default), and any number of other protocol binding elements.</span></span> <span data-ttu-id="1b254-111">이 설명에서 런타임을 빌드하는 프로세스를 통해 각 바인딩 요소가 코드를 해당 런타임에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-111">The process that builds a runtime out of this description allows each binding element to contribute code to that runtime.</span></span>  
  
 <span data-ttu-id="1b254-112">WCF는 바인딩 요소를 일반적으로 선택 하는 바인딩을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-112">WCF provides bindings that contain common selections of binding elements.</span></span> <span data-ttu-id="1b254-113">이러한 바인딩을 기본 설정에 사용하거나 사용자 요구 사항에 따라 그러한 기본값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-113">These can be used with their default settings or you can modify those default values according to user requirements.</span></span> <span data-ttu-id="1b254-114">이러한 시스템 제공 바인딩에 바인딩 요소와 해당 설정을 직접 제어할 수 있는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-114">These system-provided bindings have properties that allow direct control over the binding elements and their settings.</span></span> <span data-ttu-id="1b254-115">또한 바인딩의 각 버전에 고유한 이름을 지정하여 여러 버전의 바인딩을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-115">You can also easily work side-by-side with multiple versions of a binding by giving each version of the binding its own name.</span></span> <span data-ttu-id="1b254-116">자세한 내용은 [시스템 제공 바인딩 구성](configuring-system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b254-116">For details, see [Configuring System-Provided Bindings](configuring-system-provided-bindings.md).</span></span>  
  
 <span data-ttu-id="1b254-117">이러한 시스템 제공 바인딩 중 하나에서 제공하지 않는 바인딩 요소의 컬렉션이 필요한 경우 필요한 바인딩 요소의 컬렉션으로 구성된 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-117">If you need a collection of binding elements not provided by one of these system-provided bindings, you can create a custom binding that consists of the collection of binding elements required.</span></span> <span data-ttu-id="1b254-118">이러한 사용자 지정 바인딩은 쉽게 만들 수 있고 새 클래스가 필요하지 않지만 바인딩 요소나 해당 설정을 제어하는 속성을 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-118">These custom bindings are easy to create and do not require a new class, but they do not provide properties for controlling the binding elements or their settings.</span></span> <span data-ttu-id="1b254-119">바인딩 요소에 액세스하고 그러한 요소를 포함하는 컬렉션을 통해 해당 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-119">You can access the binding elements and modify their settings through the collection that contains them.</span></span> <span data-ttu-id="1b254-120">자세한 내용은 [사용자 지정 바인딩](../extending/custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b254-120">For details, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b254-121">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1b254-121">In This Section</span></span>  
 [<span data-ttu-id="1b254-122">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1b254-122">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)  
 <span data-ttu-id="1b254-123">WCF가 일반적인 시나리오를 지원 하기 위해 제공 하는 바인딩을 사용 하 고 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-123">Describes how to use and modify the bindings that WCF provides to support common scenarios.</span></span>  
  
 [<span data-ttu-id="1b254-124">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1b254-124">Using Bindings to Configure Services and Clients</span></span>](../using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="1b254-125">코드에서 명령적으로 서비스 및 클라이언트에 대 한 WCF (Windows Communication Foundation) 바인딩과 구성을 사용 하 여 선언적으로 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-125">Describes how to define Windows Communication Foundation (WCF) bindings for services and clients imperatively in code and declaratively using configuration.</span></span>  
  
 [<span data-ttu-id="1b254-126">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1b254-126">Custom Bindings</span></span>](../extending/custom-bindings.md)  
 <span data-ttu-id="1b254-127"><xref:System.ServiceModel.Channels.CustomBinding>의 정의와 언제 사용되는지에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b254-127">Describes what a <xref:System.ServiceModel.Channels.CustomBinding> is and when it is used.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b254-128">참고</span><span class="sxs-lookup"><span data-stu-id="1b254-128">Reference</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a><span data-ttu-id="1b254-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1b254-129">Related Sections</span></span>  
 [<span data-ttu-id="1b254-130">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="1b254-130">Extending Bindings</span></span>](../extending/extending-bindings.md)
