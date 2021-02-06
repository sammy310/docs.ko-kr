---
description: 자세한 내용은 EnlistTransactionFailure를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: f0645d0f7bfc2787f4bce254ea8d6e3143dc0406
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644608"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure

WS-AT 프로토콜 서비스가 제공된 코디네이션 컨텍스트를 사용하여 트랜잭션에 참여하지 못했습니다.  
  
## <a name="description"></a>설명  

 제공된 2PC(2단계 커밋) 프로토콜에 대한 트랜잭션에 MSDTC가 참여할 수 없을 때 추적됩니다.  이는 트랜잭션이 더 이상 존재하지 않거나, 참여가 허용되지 않거나, 인리스트먼트가 너무 많이 있을 경우 발생할 수 있습니다.  
  
## <a name="troubleshooting"></a>문제 해결  

 추적 메시지 내의 상태 문자열을 검사하여 실행 가능한 항목이 있는지 확인하세요.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
