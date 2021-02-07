---
description: '자세히 알아보기: ICorProfilerInfo:: GetThreadContext 메서드'
title: ICorProfilerInfo::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
ms.openlocfilehash: b2970da90250819cc68eee55b70188d4830113a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687274"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a>ICorProfilerInfo::GetThreadContext 메서드

지정 된 스레드와 현재 연결 된 컨텍스트 id를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a>매개 변수  

 `threadId`  
 진행 스레드의 ID입니다.  
  
 `pContextId`  
 제한이 지정 된 스레드와 현재 연결 된 컨텍스트 ID에 대 한 포인터입니다. 스레드에 현재 연결 된 컨텍스트가 없으면이 함수는 CORPROF_E_DATAINCOMPLETE을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
