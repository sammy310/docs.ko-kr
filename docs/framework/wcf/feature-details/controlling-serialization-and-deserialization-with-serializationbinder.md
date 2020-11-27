---
title: SerializationBinder를 사용하여 serialization 및 deserialization 제어
ms.date: 07/14/2020
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
ms.openlocfilehash: be4068411e2154db53a9616df6cf4d83803954e6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293743"
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>SerializationBinder를 사용하여 serialization 및 deserialization 제어

> [!WARNING]
> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 는 안전 하지 않으며 안전 하 게 만들 수 ***없습니다*** . 자세한 내용은 [Binaryformatter 보안 가이드](../../../standard/serialization/binaryformatter-security-guide.md)를 참조 하세요.

serialization 도중에, 포맷터는 올바른 형식 및 버전의 개체 인스턴스를 만드는 데 필요한 정보를 전송합니다. 이 정보에는 일반적으로 개체에 대한 어셈블리 이름 및 전체 형식 이름이 포함됩니다. 기본적으로 deserialization은 이 정보를 사용하여 동일한 개체의 인스턴스를 만듭니다. deserialization을 수행하는 컴퓨터에 원본 클래스가 없거나, 원본 클래스가 어셈블리 간에 이동했거나, 서버와 클라이언트에 서로 다른 버전의 클래스가 필요한 경우 일부 사용자는 직렬화 및 역직렬화할 클래스를 제어해야 할 수 있습니다. 자세한 내용은 [Serialization 바인더 사용](../samples/usage-of-serialization-binder.md)을 참조 하세요.  
  
> [!WARNING]
> 이 기능은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 또는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 때만 사용할 수 있습니다.  
  
## <a name="using-serializationbinder"></a>SerializationBinder 사용  

 <xref:System.Runtime.Serialization.SerializationBinder>는 serialization 및 deserialization 중에 사용되는 실제 형식을 제어하는 데 사용되는 추상 클래스입니다. serialization 및 deserialization 중에 사용되는 형식을 제어하려면 <xref:System.Runtime.Serialization.SerializationBinder>에서 클래스를 파생시키고 <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 및 <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 메서드를 재정의합니다. <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 메서드는 <xref:System.Type>을 받아서 어셈블리 및 형식 이름을 반환합니다. <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 메서드는 어셈블리 및 형식 이름을 받아서 <xref:System.Type>을 반환합니다.  
  
## <a name="see-also"></a>참고 항목

- [Serialization 및 Deserialization](serialization-and-deserialization.md)
- [Serialization 바인더 사용](../samples/usage-of-serialization-binder.md)
