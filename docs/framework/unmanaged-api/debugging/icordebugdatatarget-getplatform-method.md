---
title: ICorDebugDataTarget::GetPlatform 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679795"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform 메서드

대상 프로세스가 실행 되는 프로세서 아키텍처 및 운영 체제를 포함 하 여 플랫폼에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pTargetPlatform`  
 제한이 대상 플랫폼을 설명 하는 [Cordebugplatformenum](cordebugplatform-enumeration.md) 열거형에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `CorDebugPlatformEnum`열거형 반환 값은 [ICorDebug](icordebug-interface.md) 인터페이스에서 포인터 크기, 주소 공간 레이아웃, 레지스터 집합, 명령 형식, 컨텍스트 레이아웃 및 호출 규칙 등 대상 프로세스의 세부 정보를 확인 하는 데 사용 됩니다.  
  
 이 `pTargetPlatform` 값은 사용 중인 실제 하드웨어를 지정 하는 대신 대상에 대해 에뮬레이트하는 플랫폼을 참조할 수 있습니다. 예를 들어 Windows 운영 체제 64 비트 버전의 WOW (Windows on Windows) 환경에서 실행 되는 프로세스는 `CORDB_PLATFORM_WINDOWS_X86` [Cordebugplatformenum](cordebugplatform-enumeration.md) 열거형의 값을 사용 해야 합니다.  
  
 이 메서드는 성공 해야 합니다. 실패 한 경우 대상 플랫폼을 사용할 수 없습니다. 메서드는 다음과 같은 이유로 실패할 수 있습니다.  
  
- 대상에 대해 에뮬레이트하는 플랫폼을 사용할 수 없습니다.  
  
- 대상 플랫폼의 실제 하드웨어를 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugDataTarget 인터페이스](icordebugdatatarget-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
