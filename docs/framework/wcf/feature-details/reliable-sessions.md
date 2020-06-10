---
title: 신뢰할 수 있는 세션
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590542"
---
# <a name="reliable-sessions"></a>신뢰할 수 있는 세션

이 섹션에서는 Windows Communication Foundation (WCF) 신뢰할 수 있는 세션의 정의, 사용 방법, 사용 방법, 사용 하는 방법 및 사용 시기, 구성 요소를 지 원하는 바인딩 구성 및 모범 사례에 대 한 포인터를 설명 합니다. 다음 표에서는 이 단원의 필수 사항 및 관련 항목에 대한 세부 정보를 요약하여 설명합니다.

신뢰할 수 있는 세션 WCF는 끝점 간에 전송 되는 메시지가 SOAP 또는 전송 중개자를 통해 전송 되도록 하는 기능을 제공 하며,이를 보낸 순서와 동일 하 게 한 번만 배달 됩니다.

WCF 응용 프로그램에서 신뢰할 수 있는 세션을 사용 하려면 기본적으로 또는 옵션으로 신뢰할 수 있는 세션을 지 원하는 WCF의 시스템 제공 바인딩 중 하나를 사용 하거나, 세션을 지 원하는 사용자 지정 바인딩을 직접 만듭니다.

## <a name="in-this-section"></a>섹션 내용

[신뢰할 수 있는 세션 개요](reliable-sessions-overview.md) 신뢰할 수 있는 세션, 사용 시기, 신뢰할 수 있는 세션을 지 원하는 다양 한 바인딩 및 작동 방식에 대해 설명 합니다.

[방법: 신뢰할 수 있는 세션 내에서 메시지 교환](how-to-exchange-messages-within-a-reliable-session.md) 구성에 지정 된 사용자 지정 바인딩을 사용 하 여 HTTP를 통해 신뢰할 수 있는 세션을 만드는 방법을 설명 합니다.

[방법: 신뢰할 수 있는 세션 내에서 메시지 보안](how-to-secure-messages-within-reliable-sessions.md) 신뢰할 수 있는 세션을 보호 하는 방법을 설명 합니다.

[방법: HTTPS를 사용 하 여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](how-to-create-a-custom-reliable-session-binding-with-https.md) HTTPS를 통해 신뢰할 수 있는 세션을 만드는 방법을 설명 합니다.

[신뢰할 수 있는 세션에 대 한 모범 사례](best-practices-for-reliable-sessions.md) 신뢰할 수 있는 세션을 사용 하는 것과 관련 된 몇 가지 모범 사례를 설명 합니다.

## <a name="reference"></a>참고

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>참조

- [큐 및 신뢰할 수 있는 세션](queues-and-reliable-sessions.md)
- [세션, 인스턴스 및 동시성](sessions-instancing-and-concurrency.md)
