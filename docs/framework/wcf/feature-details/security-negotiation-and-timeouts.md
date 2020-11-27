---
title: 보안 협상 및 시간 제한
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 4ccc7e5539b1a772be6f9edb5a4cb4d94a8d1c1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275985"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="ad9f0-102">보안 협상 및 시간 제한</span><span class="sxs-lookup"><span data-stu-id="ad9f0-102">Security Negotiation and Timeouts</span></span>

<span data-ttu-id="ad9f0-103">클라이언트 및 서비스에서 인증 하는 경우 WCF (Windows Communication Foundation)는 인증의 일부로 서비스 자격 증명이 협상 되는 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9f0-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="ad9f0-104">이러한 시나리오에서는 서비스 자격 증명을 클라이언트에 전파하기 위해 클라이언트와 서비스 간에 잠재적 다중 교환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9f0-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="ad9f0-105"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 속성을 통해 다중 교환이 완료되는 데 걸리는 시간이 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9f0-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="ad9f0-106">하지만 이 시간 제한은 실제로 교환이 단일 요청 응답 시간보다 더 걸린 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9f0-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="ad9f0-107">협상이 단일 라운드트립에서 완료되는 경우에는 시간 제한이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9f0-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad9f0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad9f0-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="ad9f0-109">방법: 최대 클럭 오차 설정</span><span class="sxs-lookup"><span data-stu-id="ad9f0-109">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)
