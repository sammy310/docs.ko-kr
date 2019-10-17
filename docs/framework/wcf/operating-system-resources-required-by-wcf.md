---
title: WCF에 필요한 운영 체제 리소스
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: ac9bd5ed7c2092720c6521d0f78185c3fbf9f94b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318939"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="d5d2d-102">WCF에 필요한 운영 체제 리소스</span><span class="sxs-lookup"><span data-stu-id="d5d2d-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="d5d2d-103">WCF (Windows Communication Foundation)는 작동 하기 위해 운영 체제에서 제공 하는 여러 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2d-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="d5d2d-104">다음 표에서는 이러한 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2d-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="d5d2d-105">리소스</span><span class="sxs-lookup"><span data-stu-id="d5d2d-105">Resource</span></span>|<span data-ttu-id="d5d2d-106">설명</span><span class="sxs-lookup"><span data-stu-id="d5d2d-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d5d2d-107">MSDTC(Microsoft Distributed Transaction Coordinator)</span><span class="sxs-lookup"><span data-stu-id="d5d2d-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="d5d2d-108">OleTx 트랜잭션을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2d-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="d5d2d-109">IIS(인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="d5d2d-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="d5d2d-110">IIS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2d-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="d5d2d-111">WAS(Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="d5d2d-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="d5d2d-112">WAS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2d-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5d2d-113">참조</span><span class="sxs-lookup"><span data-stu-id="d5d2d-113">See also</span></span>

- [<span data-ttu-id="d5d2d-114">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5d2d-114">System Requirements</span></span>](wcf-system-requirements.md)
