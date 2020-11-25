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
ms.openlocfilehash: a0abc7168ff7bffdbb835c1c1bc93de9df6e381c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694869"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory 메서드

이 프로세스에 대해 지정 된 메모리 영역을 읽습니다.  
  
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
 진행 `CORDB_ADDRESS` 읽을 메모리의 기준 주소를 지정 하는 값입니다.  
  
 `size`  
 진행 메모리에서 읽을 바이트 수입니다.  
  
 `buffer`  
 제한이 메모리의 콘텐츠를 받는 버퍼입니다.  
  
 `read`  
 제한이 지정 된 버퍼로 전송 된 바이트 수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `ReadMemory`메서드는 주로 interop 디버깅에서 디버기의 관리 되지 않는 부분에 사용 되는 메모리 영역을 검사 하는 데 사용 됩니다. 이 메서드를 사용 하 여 MSIL (Microsoft 중간 언어) 코드 및 네이티브 JIT 컴파일된 코드를 읽을 수도 있습니다.  
  
 관리 되는 모든 중단점은 매개 변수에서 반환 되는 데이터에서 제거 됩니다 `buffer` . [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)에 의해 설정 된 네이티브 중단점에 대해서는 조정이 수행 되지 않습니다.  
  
 프로세스 메모리의 캐싱이 수행 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
