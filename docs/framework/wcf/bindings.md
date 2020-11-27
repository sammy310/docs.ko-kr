---
title: Windows Communication Foundation 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
ms.openlocfilehash: 3ce861404e59d24c2b1e0b548026bc795157fffe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272373"
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="f6d41-102">Windows Communication Foundation 바인딩</span><span class="sxs-lookup"><span data-stu-id="f6d41-102">Windows Communication Foundation Bindings</span></span>

<span data-ttu-id="f6d41-103">바인딩은 Windows Communication Foundation (WCF) 서비스 끝점이 다른 끝점과 통신 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-103">Bindings specify how a Windows Communication Foundation (WCF) service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="f6d41-104">가장 기본적으로 바인딩은 HTTP 또는 TCP와 같은 사용할 전송을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="f6d41-105">바인딩을 통해 보안 및 트랜잭션 지원과 같은 다른 특징을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6d41-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f6d41-106">In This Section</span></span>  

 [<span data-ttu-id="f6d41-107">WCF 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="f6d41-107">WCF Bindings Overview</span></span>](bindings-overview.md)  
 <span data-ttu-id="f6d41-108">WCF 바인딩의 역할, 시스템에서 제공 하는 바인딩, 정의 또는 수정할 수 있는 방법에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-108">Overview of what WCF bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="f6d41-109">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="f6d41-109">System-Provided Bindings</span></span>](system-provided-bindings.md)  
 <span data-ttu-id="f6d41-110">WCF에 포함 된 바인딩 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-110">A list of bindings included with WCF.</span></span> <span data-ttu-id="f6d41-111">이러한 바인딩은 대부분의 보안 및 메시지 패턴 요구 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="f6d41-112">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f6d41-112">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="f6d41-113">WCF 바인딩에는 클라이언트가 서비스 끝점에 연결 하는 데 사용 해야 하는 중요 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-113">A WCF binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="f6d41-114">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="f6d41-114">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="f6d41-115">구성을 통해 관리자와 설치 관리자가 서비스 엔드포인트에 대한 바인딩을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d41-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f6d41-116">참고</span><span class="sxs-lookup"><span data-stu-id="f6d41-116">Reference</span></span>  

 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="f6d41-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f6d41-117">Related Sections</span></span>  

 [<span data-ttu-id="f6d41-118">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="f6d41-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](./feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="f6d41-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="f6d41-119">Bindings</span></span>](./feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6d41-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6d41-120">See also</span></span>

- [<span data-ttu-id="f6d41-121">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f6d41-121">Custom Bindings</span></span>](./extending/custom-bindings.md)
