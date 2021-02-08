---
description: '자세히 알아보기: ICorDebugModule2:: SetJITCompilerFlags 메서드'
title: ICorDebugModule2::SetJITCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: 72139c2fefc0eab7e76e38d07558e4386b47bc34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801074"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags 메서드

이 ICorDebugModule2의 JIT (just-in-time) 컴파일을 제어 하는 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwFlags`  
 진행 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  

 `dwFlags`값이 잘못 된 경우 메서드는 `SetJITCompilerFlags` 실패 합니다.  
  
 `SetJITCompilerFlags`이 모듈에 대 한 [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) 콜백 내 에서만 메서드를 호출할 수 있습니다. 콜백이 전달 된 후에 호출 하려고 하면 `ICorDebugManagedCallback::LoadModule` 실패 합니다.  
  
 편집 하며 계속 하기는 64 비트 또는 Win9x 플랫폼에서 지원 되지 않습니다. 따라서 `SetJITCompilerFlags` 에 CORDEBUG_JIT_ENABLE_ENC 플래그가 설정 된 이러한 두 플랫폼 중 하나에서 메서드를 호출 하면 `dwFlags` `SetJITCompilerFlags` [ICorDebugModule2:: Applychanges](icordebugmodule2-applychanges-method.md)와 같이 편집 하며 계속 하기와 관련 된 메서드 및 모든 메서드가 실패 하 게 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
