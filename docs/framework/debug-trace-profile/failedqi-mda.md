---
title: failedQI MDA
description: .NET의 failedQI MDA (관리 디버깅 도우미)를 검토 합니다 .이는 RCW (런타임 호출 가능 래퍼)의 캐스트 또는 COM 호출이 실패할 때 활성화 될 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: bbd8d5644f8620444d80845b9920b925b6891176
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244329"
---
# <a name="failedqi-mda"></a>failedQI MDA

`failedQI` MDA(관리 디버깅 도우미)는 런타임이 RCW(런타임 호출 가능 래퍼)를 대신하여 COM 인터페이스 포인터에서 `QueryInterface`를 호출할 때 활성화되며 `QueryInterface` 호출이 실패합니다.  
  
## <a name="symptoms"></a>증상  

 RCW에 대한 캐스팅이 실패하거나 RCW에서의 COM 호출이 예기치 않게 실패합니다.  
  
## <a name="cause"></a>원인  
  
- 잘못된 컨텍스트에서 호출했습니다.  
  
- 잘못된 컨텍스트에서 호출이 시도되었기 때문에 등록된 프록시가 `QueryInterface` 호출에 실패합니다.  
  
- OLE 소유 프록시에서 실패 HRESULT가 반환되었습니다.  
  
## <a name="resolution"></a>해결 방법  

 COM 규칙에 MSDN 설명서를 참조하세요.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  

 `QueryInterface` 호출이 실패하는 경우 컨텍스트가 전환되고 `QueryInterface` 호출이 다시 시도되어 잘못된 컨텍스트가 원인인지를 확인합니다.  
  
## <a name="output"></a>출력  

 인터페이스의 관리되는 이름, 인터페이스의 GUID 및 실패 HRESULT입니다.  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [관리 디버깅 도우미를 사용하여 오류 진단](diagnosing-errors-with-managed-debugging-assistants.md)
- [interop 마샬링](../interop/interop-marshaling.md)
