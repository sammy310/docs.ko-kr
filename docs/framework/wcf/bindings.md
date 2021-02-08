---
description: '다음에 대 한 자세한 정보: 바인딩 Windows Communication Foundation'
title: Windows Communication Foundation 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
ms.openlocfilehash: 1d21fb9593917b50a22bd0b0bf0f4506fd99b8df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781170"
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="8a6bd-103">Windows Communication Foundation 바인딩</span><span class="sxs-lookup"><span data-stu-id="8a6bd-103">Windows Communication Foundation Bindings</span></span>

<span data-ttu-id="8a6bd-104">바인딩은 Windows Communication Foundation (WCF) 서비스 끝점이 다른 끝점과 통신 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-104">Bindings specify how a Windows Communication Foundation (WCF) service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="8a6bd-105">가장 기본적으로 바인딩은 HTTP 또는 TCP와 같은 사용할 전송을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-105">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="8a6bd-106">바인딩을 통해 보안 및 트랜잭션 지원과 같은 다른 특징을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-106">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a6bd-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8a6bd-107">In This Section</span></span>  

 [<span data-ttu-id="8a6bd-108">WCF 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="8a6bd-108">WCF Bindings Overview</span></span>](bindings-overview.md)  
 <span data-ttu-id="8a6bd-109">WCF 바인딩의 역할, 시스템에서 제공 하는 바인딩, 정의 또는 수정할 수 있는 방법에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-109">Overview of what WCF bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="8a6bd-110">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="8a6bd-110">System-Provided Bindings</span></span>](system-provided-bindings.md)  
 <span data-ttu-id="8a6bd-111">WCF에 포함 된 바인딩 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-111">A list of bindings included with WCF.</span></span> <span data-ttu-id="8a6bd-112">이러한 바인딩은 대부분의 보안 및 메시지 패턴 요구 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-112">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="8a6bd-113">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8a6bd-113">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="8a6bd-114">WCF 바인딩에는 클라이언트가 서비스 끝점에 연결 하는 데 사용 해야 하는 중요 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-114">A WCF binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="8a6bd-115">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8a6bd-115">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="8a6bd-116">구성을 통해 관리자와 설치 관리자가 서비스 엔드포인트에 대한 바인딩을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6bd-116">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8a6bd-117">참고</span><span class="sxs-lookup"><span data-stu-id="8a6bd-117">Reference</span></span>  

 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="8a6bd-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8a6bd-118">Related Sections</span></span>  

 [<span data-ttu-id="8a6bd-119">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="8a6bd-119">Endpoints: Addresses, Bindings, and Contracts</span></span>](./feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="8a6bd-120">바인딩</span><span class="sxs-lookup"><span data-stu-id="8a6bd-120">Bindings</span></span>](./feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a6bd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a6bd-121">See also</span></span>

- [<span data-ttu-id="8a6bd-122">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="8a6bd-122">Custom Bindings</span></span>](./extending/custom-bindings.md)
