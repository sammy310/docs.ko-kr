---
description: Version-Tolerant Serialization 콜백에 대해 자세히 알아보세요.
title: 버전 독립적 Serialization 콜백
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: 8ee53e96b90ae6b0f2993a543fc129d75eb3481f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756008"
---
# <a name="version-tolerant-serialization-callbacks"></a>버전 독립적 Serialization 콜백

데이터 계약 프로그래밍 모델에서는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 및 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 클래스에서 지원하는 버전 독립적 serialization 콜백 메서드를 완전히 지원합니다.  
  
## <a name="version-tolerant-attributes"></a>버전 독립적 특성  

 4개의 콜백 특성이 있습니다. 각 특성은 다양한 시기에 serialization/deserialization 엔진에서 호출하는 메서드에 적용할 수 있습니다. 다음 표에서는 각 특성을 사용하는 시기에 대해 설명합니다.  
  
|attribute|해당 메서드를 호출하는 시기|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|형식을 serialize하기 전에 호출됩니다.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|형식을 serialize한 후에 호출됩니다.|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|형식을 역직렬화하기 전에 호출됩니다.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|형식을 역직렬화한 후에 호출됩니다.|  
  
 메서드에서는 <xref:System.Runtime.Serialization.StreamingContext> 매개 변수를 받아야 합니다.  
  
 이 메서드는 주로 버전 지정 또는 초기화에 사용됩니다. deserialization을 수행하는 동안에는 생성자가 호출되지 않습니다. 따라서 들어오는 스트림에 이러한 멤버의 데이터가 없는 경우(예: 데이터가 일부 데이터 멤버가 없는 이전 버전의 형식으로부터 오는 경우) 데이터 멤버가 의도한 기본값으로 올바르게 초기화되지 않을 수 있습니다. 이 문제를 해결하려면 다음 예제처럼 <xref:System.Runtime.Serialization.OnDeserializingAttribute>로 표시된 콜백 메서드를 사용합니다.  
  
 위의 각 콜백 특성에서 형식 당 1개의 메서드만 표시할 수 있습니다.  
  
### <a name="example"></a>예제  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [버전 허용 Serialization](../../../standard/serialization/version-tolerant-serialization.md)
