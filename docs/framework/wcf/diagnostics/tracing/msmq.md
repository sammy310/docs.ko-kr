---
description: '다음에 대 한 자세한 정보: MSMQ'
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 3d694fdab202cd2b3b03c377f72d93c22cbae263
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720581"
---
# <a name="msmq"></a><span data-ttu-id="0e52e-103">MSMQ</span><span class="sxs-lookup"><span data-stu-id="0e52e-103">MSMQ</span></span>

<span data-ttu-id="0e52e-104">MSMQ 애플리케이션에서는 대기 중인 채널에서 MSMQ로, 그리고 MSMQ에서 대기 중인 채널로 추가 동작이 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e52e-104">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="0e52e-105">또한 보내기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e52e-105">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="0e52e-106">받기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e52e-106">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="0e52e-107">수신 작업에 필요한 전송은 다른 전송 (수신 바이트->메시지 > 작업)과 유사 하 게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e52e-107">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
