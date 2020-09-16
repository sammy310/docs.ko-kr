---
title: 예외가 throw된 V1 ETW 이벤트
description: ExceptionThrown_V1 ETW 이벤트에 대 한 자세한 정보를 확인 합니다. Throw 된 예외에 대해 필드 이름, 데이터 형식 및 설명과 같은 이벤트 데이터가 제공 됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f4ae277b5dfb09d2676755fec2208b63906ead84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554673"
---
# <a name="exception-thrown_v1-etw-event"></a>예외가 throw된 V1 ETW 이벤트
이 이벤트는 throw된 예외에 대한 정보를 캡처합니다.  
  
 다음 표에서는 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다. 자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.  
  
|이벤트를 발생시키기 위한 키워드|Level|  
|-----------------------------------|-----------|  
|`ExceptionKeyword`(0x8000)|경고(2)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|관리되는 예외가 throw됩니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|Description|  
|----------------|---------------|-----------------|  
|예외 유형|win:UnicodeString|예외 형식, 예: `System.NullReferenceException`.|  
|예외 메시지|win:UnicodeString|실제 예외 메시지입니다.|  
|EIPCodeThrow|win:Pointer|예외가 발생한 명령 포인터입니다.|  
|ExceptionHR|win:UInt32|예외 [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)입니다.|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException(Visual Basic 설명서에서 [CLR ETW Events](clr-etw-events.md) 참조).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (프로세스 상태가 손상 되었음을 나타냅니다. [손상 된 상태 예외 처리](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)를 참조 하세요.)<br /><br /> 0x10: IsCLSCompliant(<xref:System.Exception>에서 파생된 예외는 CLS와 호환됨, 그러지 않으면 CLS와 호환되지 않음).|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
## <a name="see-also"></a>참조

- [CLR ETW 이벤트](clr-etw-events.md)
