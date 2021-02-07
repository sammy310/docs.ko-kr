---
description: '자세히 알아보기: ICorDebugProcess:: WriteMemory 메서드'
title: ICorDebugProcess::WriteMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 6ea48aff2e1ea812d851a228976b458f58a60e14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746626"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory 메서드

이 프로세스의 메모리 영역에 데이터를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>매개 변수  

 `address`  
 진행 `CORDB_ADDRESS` 데이터가 기록 되는 메모리 영역의 기준 주소인 값입니다. 데이터 전송이 발생 하기 전에 시스템에서는 기본 주소에서 시작 하 여 지정 된 크기의 메모리 영역을 쓰기 위해 액세스할 수 있는지 확인 합니다. 액세스할 수 없는 경우 메서드가 실패 합니다.  
  
 `size`  
 진행 메모리 영역에 쓸 바이트 수입니다.  
  
 `buffer`  
 진행 쓸 데이터를 포함 하는 버퍼입니다.  
  
 `written`  
 제한이 이 프로세스의 메모리 영역에 쓴 바이트 수를 받는 변수에 대 한 포인터입니다. `written`가 NULL 이면이 매개 변수는 무시 됩니다.  
  
## <a name="remarks"></a>설명  

 데이터는 모든 중단점 뒤에 자동으로 기록 됩니다. .NET Framework 버전 2.0에서 네이티브 디버거는이 메서드를 사용 하 여 중단점을 명령 스트림에 삽입 해서는 안 됩니다. 대신 [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) 를 사용 합니다.  
  
 `WriteMemory`메서드는 관리 코드 외부 에서만 사용 해야 합니다. 이 메서드는 부적절 하 게 사용 되는 경우 런타임을 손상 시킬 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
