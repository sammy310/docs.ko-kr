---
description: '자세한 정보: 트랜잭션 모델'
title: 트랜잭션 모델
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9abccf74ef5b242cfbe63605046e30e397b8eda6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752706"
---
# <a name="transaction-models"></a>트랜잭션 모델

이 항목에서는 트랜잭션 프로그래밍 모델 및 Microsoft가 제공하는 인프라 구성 요소 간의 관계에 대해 설명합니다.  
  
 WCF (Windows Communication Foundation)에서 트랜잭션을 사용 하는 경우 서로 다른 트랜잭션 모델 중에서 선택 하는 것은 아니지만, 통합 및 일관 된 모델의 여러 계층에서 작동 한다는 것을 이해 하는 것이 중요 합니다.  
  
 다음 단원에서는 세 가지 기본 트랜잭션 구성 요소에 대해 설명합니다.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 트랜잭션  

 WCF의 트랜잭션 지원을 통해 트랜잭션 서비스를 작성할 수 있습니다. 또한 응용 프로그램은 WS-AtomicTransaction (WS-AT) 프로토콜에 대 한 지원을 통해 WCF 또는 타사 기술을 사용 하 여 빌드된 웹 서비스로 트랜잭션을 이동할 수 있습니다.  
  
 WCF 서비스 또는 응용 프로그램에서 WCF 트랜잭션 기능은 인프라에서 트랜잭션을 만들고, 전달 하 고, 동기화 하는 방법과 시기를 선언적으로 지정 하는 특성 및 구성을 제공 합니다.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 트랜잭션  

 <xref:System.Transactions> 네임스페이스는 <xref:System.Transactions.Transaction> 클래스 기반의 명시적 프로그래밍 모델과 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 암시적 프로그래밍 모델을 모두 제공합니다. 후자의 경우 인프라에서 자동으로 트랜잭션을 관리합니다.  
  
 이러한 두 모델을 사용 하 여 트랜잭션 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 [트랜잭션 응용 프로그램 작성](https://go.microsoft.com/fwlink/?LinkId=94947)을 참조 하세요.  
  
 WCF 서비스 또는 응용 프로그램에서는 <xref:System.Transactions> 클라이언트 응용 프로그램 내에서 트랜잭션을 만들고 필요한 경우 서비스 내에서 트랜잭션과 명시적으로 상호 작용 하기 위한 프로그래밍 모델을 제공 합니다.  
  
## <a name="msdtc-transactions"></a>MSDTC 트랜잭션  

 MSDTC(Microsoft Distributed Transaction Coordinator)는 분산 트랜잭션을 지원하는 트랜잭션 관리자입니다.  
  
 자세한 내용은 [DTC 프로그래머 참조](/previous-versions/windows/desktop/ms686108(v=vs.85))를 참조 하세요.  
  
 WCF 서비스 또는 응용 프로그램에서 MSDTC는 클라이언트 또는 서비스 내에서 만든 트랜잭션의 조정을 위한 인프라를 제공 합니다.
