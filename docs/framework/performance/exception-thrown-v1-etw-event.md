---
title: 예외가 throw된 V1 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723019"
---
# <a name="exception-thrownv1-etw-event"></a>예외가 throw된 V1 ETW 이벤트
이 이벤트는 throw된 예외에 대한 정보를 캡처합니다.  
  
 다음 표에서는 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다. 자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|  
|`ExceptionKeyword`(0x8000)|경고(2)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|이벤트(event)|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|관리되는 예외가 throw됩니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|----------------|---------------|-----------------|  
|예외 형식|win:UnicodeString|예외 형식, 예: `System.NullReferenceException`.|  
|예외 메시지|win:UnicodeString|실제 예외 메시지입니다.|  
|EIPCodeThrow|win:Pointer|예외가 발생한 명령 포인터입니다.|  
|ExceptionHR|win:UInt32|예외 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)입니다.|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (참조 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md) Visual Basic 설명서에서).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (프로세스 상태가 손상 되었음을; 참조 [손상 된 상태 예외 처리](https://go.microsoft.com/fwlink/?LinkId=179681) msdn).<br /><br /> 0x10: IsCLSCompliant (에서 파생 되는 예외가 <xref:System.Exception> CLS 규격이 고, 그렇지 않으면는 CLS 규격이 아니므로).|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
## <a name="see-also"></a>참고자료

- [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)
