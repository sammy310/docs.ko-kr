---
description: '자세히 알아보기: System.servicemodel. ConnectionPoolCloseException'
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: a65739cc872f3cd175d76e9113380f9f4185d498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644634"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="06888-103">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="06888-103">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="06888-104">이 연결 풀에서 연결을 닫는 동안 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="06888-104">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="06888-105">설명</span><span class="sxs-lookup"><span data-stu-id="06888-105">Description</span></span>  

 <span data-ttu-id="06888-106">이 오류 수준 추적은 Windows Communication Foundation (WCF)의 연결 풀링 기능에서 사용 하는 연결 풀을 닫는 동안 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06888-106">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="06888-107">이러한 오류의 원인 중 하나는 CloseTimeout 내의 풀 연결 또는 풀 연결 집합을 닫는 데 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06888-107">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="06888-108">이 예외가 throw되면 해당 풀 내의 닫지 않은 나머지 연결이 중단되고 다른 풀 내의 닫지 않은 연결도 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="06888-108">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06888-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06888-109">See also</span></span>

- [<span data-ttu-id="06888-110">추적</span><span class="sxs-lookup"><span data-stu-id="06888-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="06888-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="06888-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="06888-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="06888-112">Administration and Diagnostics</span></span>](../index.md)
