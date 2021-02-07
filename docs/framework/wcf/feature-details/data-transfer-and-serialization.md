---
description: 데이터 전송 및 Serialization에 대해 자세히 알아보세요.
title: 데이터 전송 및 Serialization
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 50e5068efc10d706fb9ce2634998408e48037ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756567"
---
# <a name="data-transfer-and-serialization"></a>데이터 전송 및 Serialization

연결된 시스템에서 서비스 및 클라이언트는 데이터 교환에 의존하여 작업을 수행합니다. 서비스 또는 클라이언트 개발자는 효율적이 고 쉽게 관리할 수 있는 응용 프로그램을 만들기 위해 WCF (Windows Communication Foundation)에서 데이터 및 데이터 serialization을 처리 하는 방법을 이해 해야 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [서비스 계약에서 데이터 전송 지정](specifying-data-transfer-in-service-contracts.md)  
 서비스에서 데이터 전송의 기본 개념에 대해 설명합니다.  
  
 [데이터 계약 사용](using-data-contracts.md)  
 데이터 계약의 정의와 데이터 계약을 만들고 사용하는 방법에 대해 설명합니다.  
  
 [데이터 계약 직렬 변환기](data-contract-serializer.md)  
 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스 또는 <xref:System.Runtime.Serialization.XmlObjectSerializer> 클래스의 확장을 사용하여 데이터의 serialization을 수행하는 방법에 대해 설명합니다.  
  
 [XmlSerializer 클래스 사용](using-the-xmlserializer-class.md)  
 <xref:System.Xml.Serialization.XmlSerializer> 클래스 대신 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용하는 방법 및 이유에 대해 설명합니다.  
  
 [메시지 계약 사용](using-message-contracts.md)  
 메시지 계약에서 SOAP 메시지를 정밀하게 제어하는 방법에 대해 설명합니다.  
  
 [Message 클래스 사용](using-the-message-class.md)  
 Message 클래스 기능을 사용하는 방법에 대해 설명합니다.  
  
 [필터링](filtering.md)  
 여러 조건을 기반으로 메시지 전처리를 사용하는 필터링에 대해 설명합니다.  
  
 [큰 데이터 및 스트리밍](large-data-and-streaming.md)  
 이진 파일과 같은 큰 데이터 블록을 보내는 방법에 대해 설명합니다.  
  
 [데이터에 대한 보안 고려 사항](security-considerations-for-data.md)  
 데이터 전송 및 serialization을 프로그래밍할 때 알고 있어야 하는 항목에 대해 설명합니다.  
  
 [데이터 전송 아키텍처 개요](data-transfer-architectural-overview.md)  
 WCF의 전체 데이터 전송 디자인에 대해 설명 합니다.  
  
## <a name="reference"></a>참고  

 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>관련 단원  

 [인코더 및 Serializer 확장](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>참고 항목

- [모범 사례: 데이터 계약 버전 관리](../best-practices-data-contract-versioning.md)
- [서비스 버전 관리](../service-versioning.md)
