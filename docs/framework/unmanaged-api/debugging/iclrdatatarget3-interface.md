---
title: ICLRDataTarget3 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: f7635dc3fad9b3de30fa052c7d2e67a7e6953fb3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789048"
---
# <a name="iclrdatatarget3-interface"></a>ICLRDataTarget3 인터페이스
예외 정보에 대 한 액세스를 제공 하는 [ICLRDataTarget2](iclrdatatarget2-interface.md) 의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetExceptionRecord 메서드](iclrdatatarget3-getexceptionrecord-method.md)|공용 언어 런타임(CLR)에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 예외 레코드 검색을 제공합니다.|  
|[GetExceptionContextRecord 메서드](iclrdatatarget3-getexceptioncontextrecord-method.md)|CLR에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 컨텍스트 레코드 검색을 제공합니다.|  
|[GetExceptionThreadID 메서드](iclrdatatarget3-getexceptionthreadid-method.md)|CLR 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다. 예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다. 대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>참조

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
- [ICLRDataTarget2 인터페이스](iclrdatatarget2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
