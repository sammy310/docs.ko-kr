---
description: '자세히 알아보기: ICorProfilerInfo4:: GetReJITIDs 메서드'
title: ICorProfilerInfo4::GetReJITIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 60df4cb6023bbee68d2909e1cc0e9de5595ac0b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636405"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs 메서드

아직 할당 된 지정 된 함수의 JIT 다시 컴파일된 모든 버전을 식별 하는 Id 배열을 반환 합니다. 여기에는 나중에 되돌린 하지만 아직 해제 되지 않은 함수의 JIT 다시 컴파일된 버전 (예: 되돌린 함수를 포함 하는 응용 프로그램 도메인이 아직 사용 중인 경우)이 포함 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `functionId`  
 진행 `FunctionID` 버전을 열거할 함수 인스턴스의입니다.  
  
 `cReJitIds`  
 진행 배열에 할당 된 JIT 다시 컴파일된 Id의 수입니다 `reJitIds` .  
  
 `pcReJitIds`  
 제한이 JIT 다시 컴파일된 Id의 실제 수입니다.  
  
 `reJitIds`  
 제한이 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자가 할당 한 배열입니다.  
  
## <a name="remarks"></a>설명  

 `GetReJITIDs` 지정 된 함수 인스턴스에 대 한 활성 JIT 다시 컴파일된 Id를 열거 합니다. `ICorProfilerInfo`호출자가 할당 한 버퍼를 허용 하는 다른 함수와 동일한 사용 패턴을 따릅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
