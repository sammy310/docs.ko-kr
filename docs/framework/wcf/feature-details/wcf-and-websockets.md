---
title: WCF 및 웹 소켓
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: df4a251eb5a570c9fedf19d385a027e23481afed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594948"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="51d69-102">WCF 및 웹 소켓</span><span class="sxs-lookup"><span data-stu-id="51d69-102">WCF and WebSockets</span></span>
<span data-ttu-id="51d69-103">.NET Framework 4.5부터 Windows Communication Foundation에서 WebSocket을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51d69-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="51d69-104">WebSocket은 표준 HTTP 포트 80 및 443에서 양방향 통신을 가능하게 하는 효율적 표준 기반 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="51d69-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="51d69-105">표준 HTTP 포트를 사용하면 WebSocket이 매개자를 통해 웹에서 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51d69-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="51d69-106">WebSocket 전송에서 통신을 지원하기 위해</span><span class="sxs-lookup"><span data-stu-id="51d69-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="51d69-107"><xref:System.ServiceModel.NetHttpBinding> 및 <xref:System.ServiceModel.NetHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="51d69-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="51d69-108">속성에 액세스 하 여에서 Websocket 별 설정을 구성할 수 있습니다 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> .</span><span class="sxs-lookup"><span data-stu-id="51d69-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="51d69-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="51d69-109">In This Section</span></span>  
 [<span data-ttu-id="51d69-110">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="51d69-110">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="51d69-111"><xref:System.ServiceModel.NetHttpBinding> 및 해당 구성 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51d69-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="51d69-112">방법: WebSocket을 통해 통신하는 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="51d69-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="51d69-113">WebSocket을 통해 통신하는 WCF 서비스를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51d69-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="51d69-114">참고</span><span class="sxs-lookup"><span data-stu-id="51d69-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="51d69-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="51d69-115">Related Sections</span></span>
