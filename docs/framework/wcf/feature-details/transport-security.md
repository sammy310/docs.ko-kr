---
title: 전송 보안
description: 이러한 참조를 사용 하 여 WFC의 전송 보안 메커니즘, 구현 방법 및 옵션을 이해할 수 있습니다.
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
ms.openlocfilehash: d39aa49906b79b9e12eecf04629080863719f986
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244753"
---
# <a name="transport-security"></a><span data-ttu-id="f2f5e-103">전송 보안</span><span class="sxs-lookup"><span data-stu-id="f2f5e-103">Transport Security</span></span>
<span data-ttu-id="f2f5e-104">WCF (Windows Communication Foundation)의 전송 보안은 선택한 바인딩에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-104">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="f2f5e-105">바인딩이 구현하는 전송은 실제 보안 메커니즘을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-105">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="f2f5e-106">이 단원의 항목에서는 구현된 메커니즘 및 해당 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-106">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2f5e-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f2f5e-107">In This Section</span></span>  
 [<span data-ttu-id="f2f5e-108">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="f2f5e-108">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="f2f5e-109">WCF의 전송 보안에 대 한 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-109">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="f2f5e-110">HTTP 전송 보안</span><span class="sxs-lookup"><span data-stu-id="f2f5e-110">HTTP Transport Security</span></span>](http-transport-security.md)  
 <span data-ttu-id="f2f5e-111">WCF가 SSL(Secure Sockets Layer) (SSL 또는 HTTPS)를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-111">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="f2f5e-112">HTTP 인증 이해</span><span class="sxs-lookup"><span data-stu-id="f2f5e-112">Understanding HTTP Authentication</span></span>](understanding-http-authentication.md)  
 <span data-ttu-id="f2f5e-113">기본, 다이제스트, NTLM(NT LAN Manager) 등과 같은 HTTP 인증 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-113">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="f2f5e-114">전송 보안을 통해 가장 사용</span><span class="sxs-lookup"><span data-stu-id="f2f5e-114">Using Impersonation with Transport Security</span></span>](using-impersonation-with-transport-security.md)  
 <span data-ttu-id="f2f5e-115">전송 보안 모드를 사용하여 수행할 수 있는 5가지 가장 수준에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-115">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="f2f5e-116">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="f2f5e-116">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="f2f5e-117">SSL(전송) 보안용 X.509 인증서가 있는 컴퓨터에서의 포트 구성 기본 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f5e-117">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f2f5e-118">참고</span><span class="sxs-lookup"><span data-stu-id="f2f5e-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="f2f5e-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f2f5e-119">Related Sections</span></span>  
 [<span data-ttu-id="f2f5e-120">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f2f5e-120">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="f2f5e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2f5e-121">See also</span></span>

- [<span data-ttu-id="f2f5e-122">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f2f5e-122">Programming WCF Security</span></span>](programming-wcf-security.md)
