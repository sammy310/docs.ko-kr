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
# <a name="msmq"></a>MSMQ

MSMQ 애플리케이션에서는 대기 중인 채널에서 MSMQ로, 그리고 MSMQ에서 대기 중인 채널로 추가 동작이 전송되지 않습니다.  
  
 또한 보내기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.  
  
 받기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.  
  
 수신 작업에 필요한 전송은 다른 전송 (수신 바이트->메시지 > 작업)과 유사 하 게 실행 됩니다.
