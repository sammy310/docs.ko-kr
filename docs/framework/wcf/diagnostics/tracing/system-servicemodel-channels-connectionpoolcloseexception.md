---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 0a312d192546655dc327667c00f4f2bbc0c15fdb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602052"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
이 연결 풀에서 연결을 닫는 동안 예외가 발생했습니다.  
  
## <a name="description"></a>Description  
 이 오류 수준 추적은 Windows Communication Foundation (WCF)의 연결 풀링 기능에서 사용 하는 연결 풀을 닫는 동안 오류가 발생 했음을 나타냅니다. 이러한 오류의 원인 중 하나는 CloseTimeout 내의 풀 연결 또는 풀 연결 집합을 닫는 데 실패한 것입니다. 이 예외가 throw되면 해당 풀 내의 닫지 않은 나머지 연결이 중단되고 다른 풀 내의 닫지 않은 연결도 중단됩니다.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
