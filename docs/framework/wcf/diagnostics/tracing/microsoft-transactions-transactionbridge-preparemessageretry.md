---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: d5ebe3e1ccce7a85073e2de19d915d116f709b2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286970"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a>Microsoft.Transactions.TransactionBridge.PrepareMessageRetry

준비 메시지 재시도를 응답하지 않는 참가자에게 보냈습니다.  
  
## <a name="description"></a>Description  

 로컬 트랜잭션 관리자가 주어진 시간 내에 응답을 받지 못해서 준비 메시지를 하위 참가자에게 다시 전송해야 할 경우에 추적됩니다.  
  
## <a name="troubleshooting"></a>문제 해결  

 응답을 제시간에 전달하지 못하도록 하는 잠재적인 네트워크 문제 또는 제품 문제를 조사합니다.  이러한 메시지 중 대부분이 표시되면 이는 인프라 문제 또는 비정상적으로 긴 응답 시간을 나타낼 수 있습니다. 두 가지 문제 모두 시스템 내의 트랜잭션 처리량을 심각하게 감소시킬 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
