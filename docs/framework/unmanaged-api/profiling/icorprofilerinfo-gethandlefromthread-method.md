---
title: ICorProfilerInfo::GetHandleFromThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: 038f922eaaeb7d660cfbdcc0facb89677bdd154e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863545"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a>ICorProfilerInfo::GetHandleFromThread 메서드
스레드의 ID를 Win32 스레드 핸들에 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadId`  
 진행 매핑할 스레드 ID입니다.  
  
 `phThread`  
 제한이 Win32 스레드 핸들에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 프로파일러는 사용 하기 전에 핸들에서 Win32 `DuplicateHandle` 함수를 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
