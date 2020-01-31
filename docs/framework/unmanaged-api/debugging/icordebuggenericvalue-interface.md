---
title: ICorDebugGenericValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794466"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue 인터페이스

모든 값에 적용 되는 "ICorDebugValue"의 서브 클래스입니다. 이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetValue 메서드](icordebuggenericvalue-getvalue-method.md)|값을 지정 된 버퍼에 복사 합니다.|  
|[SetValue 메서드](icordebuggenericvalue-setvalue-method.md)|지정 된 버퍼에서 새 값을 복사 합니다.|  
  
## <a name="remarks"></a>주의  
 `ICorDebugGenericValue`은 원격으로 가능 하지 않으므로 하위 인터페이스입니다.  
  
 참조 형식의 경우 값은 참조의 내용이 아닌 참조입니다.  
  
 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
