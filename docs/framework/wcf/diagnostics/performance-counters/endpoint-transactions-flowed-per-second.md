---
title: '끝점: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916255"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="9180c-102">끝점: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="9180c-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="9180c-103">카운터 이름: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="9180c-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9180c-104">설명</span><span class="sxs-lookup"><span data-stu-id="9180c-104">Description</span></span>  
 <span data-ttu-id="9180c-105">이 엔드포인트에서 작업에 적용된 초당 트랜잭션의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9180c-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="9180c-106">엔드포인트에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="9180c-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="9180c-107">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9180c-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9180c-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9180c-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
