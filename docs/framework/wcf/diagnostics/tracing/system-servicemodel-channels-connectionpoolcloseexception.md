---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182197"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="7db36-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="7db36-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="7db36-103">이 연결 풀에서 연결을 닫는 동안 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="7db36-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7db36-104">설명</span><span class="sxs-lookup"><span data-stu-id="7db36-104">Description</span></span>  
 <span data-ttu-id="7db36-105">이 오류 수준 추적 오류가 Windows Communication Foundation (WCF)의 연결 풀링 기능에서 사용 하는 연결 풀을 닫는 동안 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7db36-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="7db36-106">이러한 오류의 원인 중 하나는 CloseTimeout 내의 풀 연결 또는 풀 연결 집합을 닫는 데 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7db36-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="7db36-107">이 예외가 throw되면 해당 풀 내의 닫지 않은 나머지 연결이 중단되고 다른 풀 내의 닫지 않은 연결도 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="7db36-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db36-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="7db36-108">See also</span></span>

- [<span data-ttu-id="7db36-109">추적</span><span class="sxs-lookup"><span data-stu-id="7db36-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7db36-110">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7db36-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7db36-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="7db36-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
