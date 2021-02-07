---
description: TxCompletionStatusAbortedOnSessionClose에 대해 자세히 알아보세요.
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: d47dc1a87c7f44b58f70f9590b4233f1e0a9074e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735714"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose

세션을 닫고 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute가 false로 설정되었을 때 지정된 트랜잭션이 완료되지 않았기 때문에 해당 트랜잭션이 중단되었습니다.  
  
## <a name="description"></a>설명  

 현재 활성 세션을 닫고 트랜잭션이 완료되지 않았으며 TransactionAutoCompleteOnSessionClose가 `false`로 설정된 경우 추적됩니다.  
  
## <a name="troubleshooting"></a>문제 해결  

 이 추적은 조사해야 하는 발생 가능한 애플리케이션 버그를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
