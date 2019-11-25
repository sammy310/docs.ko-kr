---
title: Serialization 바인더 사용
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138651"
---
# <a name="usage-of-serialization-binder"></a>Serialization 바인더 사용
이 샘플에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 사용하여 제네릭 형식이 serialize될 때 이 형식의 버전을 변경하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 서로 다른 버전의 .NET Framework를 대상으로 하는 두 엔터티가 이진 포맷터 및 serialization 바인더를 사용 하 여 통신할 수 있는 방법을 보여 줍니다.  
  
이 샘플은 .NET Remoting을 사용 하 여 개발 되었습니다. 이는 .NET Framework 4를 대상으로 하는 서버로 구성 됩니다 .이 서버는 제네릭 형식을 사용 하는 계약을 구현 하 고 두 개의 다른 클라이언트 .NET Framework 2.0를 대상으로 하며 다른 하나는 .NET Framework 4입니다.  
  
 서버에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 이진 포맷터에 연결하여 serialization 시 형식 버전을 적절하게 변경할 수 있도록 하므로 두 클라이언트 모두 해당 형식을 올바르게 역직렬화할 수 있습니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 클라이언트를 실행 하려면 솔루션을 마우스 오른쪽 단추로 클릭 하 고 (프로젝트 6 개) SBGenericsVTS **속성**을 선택 합니다.  
  
2. **공용 속성**에서 **시작 프로젝트**를 선택한 다음 **여러 개의 시작 프로젝트**를 선택 합니다.  
  
3. **서버** 를 먼저 선택 하 고 **Client20** 한 다음 **Client40**를 선택 합니다. 이러한 3 개의 프로젝트에 대 한 **시작** 작업을 선택 하 고 나머지는 **없음**으로 설정 합니다.  
  
4. **확인** 을 클릭 한 다음 f5 키를 눌러 샘플을 실행 합니다.
