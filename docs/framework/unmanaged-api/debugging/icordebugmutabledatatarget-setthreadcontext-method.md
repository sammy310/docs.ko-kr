---
description: '자세히 알아보기: ICorDebugMutableDataTarget:: SetThreadContext 메서드'
title: ICorDebugMutableDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 4674df92b72b44e19eff663c9a17dd8ca4b5a1b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722479"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext 메서드

스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwThreadID`  
 [in] 운영 체제에서 정의된 스레드 식별자입니다.  
  
 `contextSize`  
 [in] 쓸 `pContext` 버퍼의 크기입니다.  
  
 `pContext`  
 [in] 쓸 바이트에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `SetThreadContext` 메서드는 운영 체제에서 정의된 `dwThreadID` 인수로 지정된 스레드에 대한 현재 컨텍스트를 업데이트합니다. 컨텍스트 레코드의 형식은 [ICorDebugDataTarget:: getplatform](icordebugdatatarget-getplatform-method.md) 메서드로 표시 되는 플랫폼에 의해 결정 됩니다. Windows에서는 [컨텍스트](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugMutableDataTarget 인터페이스](icordebugmutabledatatarget-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
