---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663728"
---
# <a name="msmq"></a><span data-ttu-id="f4614-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="f4614-102">MSMQ</span></span>
<span data-ttu-id="f4614-103">MSMQ 애플리케이션에서는 대기 중인 채널에서 MSMQ로, 그리고 MSMQ에서 대기 중인 채널로 추가 동작이 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4614-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="f4614-104">또한 보내기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4614-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="f4614-105">받기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4614-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="f4614-106">수신 작업에서 필요한 전송은 다른 전송 마찬가지로 실행 됩니다 (수신 메시지를 처리 하는 바이트->-> 작업).</span><span class="sxs-lookup"><span data-stu-id="f4614-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
