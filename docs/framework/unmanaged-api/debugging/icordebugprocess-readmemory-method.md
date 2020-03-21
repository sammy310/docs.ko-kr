---
title: ICorDebugProcess::ReadMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178658"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory 메서드
이 프로세스에 대해 지정된 메모리 영역을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 【인】 읽을 `CORDB_ADDRESS` 메모리의 기본 주소를 지정하는 값입니다.  
  
 `size`  
 【인】 메모리에서 읽을 바이트 수입니다.  
  
 `buffer`  
 【아웃】 메모리의 내용을 받는 버퍼입니다.  
  
 `read`  
 【아웃】 지정된 버퍼로 전송된 바이트 수에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 `ReadMemory` 메서드는 주로 디버지의 관리되지 않는 부분에서 사용 중인 메모리 영역을 검사하기 위해 interop 디버깅에서 사용됩니다. 이 메서드는 Microsoft 중간 언어(MSIL) 코드와 기본 JIT 컴파일된 코드를 읽는 데 사용할 수도 있습니다.  
  
 관리되는 모든 중단점은 `buffer` 매개 변수에 반환되는 데이터에서 제거됩니다. [ICorDebugProcess2:SetUnmanaged 중단점에서](icordebugprocess2-setunmanagedbreakpoint-method.md)설정한 네이티브 중단점에 대해 조정이 수행되지 않습니다.  
  
 프로세스 메모리의 캐싱이 수행되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
