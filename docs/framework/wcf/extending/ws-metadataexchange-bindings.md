---
title: WS-MetadataExchange 바인딩
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293990"
---
# <a name="ws-metadataexchange-bindings"></a>WS-MetadataExchange 바인딩

이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.  
  
## <a name="the-default-bindings"></a>기본 바인딩  
  
|기본 바인딩 이름|바인딩 생성 방법|  
|--------------------------|------------------------------------|  
|mexHttpBinding|전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.|  
|mexHttpsBinding|전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.|  
|mexNamedPipeBinding|기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.|  
|mexTcpBinding|기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.|
