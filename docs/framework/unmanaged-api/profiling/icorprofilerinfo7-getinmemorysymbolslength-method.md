---
title: 'ICorProfilerInfo7:: Getinmemory기호 Slength 메서드'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 299a7495d9ca9215ad21301a3ac525fa6e49a01b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130338"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7:: Getinmemory기호 Slength 메서드
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림의 길이를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.  
  
 Pcount기호 바이트  
 제한이 메서드가 반환 될 때 스트림의 길이 (바이트)를 포함 하는 `DWORD` 값에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 메모리 스트림의 길이가 0 인 경우에도이를 확인할 수 있는 경우 `S_OK`을 반환 합니다.  
  
 메서드는 <xref:System.Reflection.Emit?displayProperty=nameWithType>를 사용 하 여 메서드를 만든 경우 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.  
  
## <a name="remarks"></a>주의  
 모듈에 메모리 내 기호가 있으면 스트림의 길이가 `pCountSymbolBytes`에 배치 됩니다. 모듈에 메모리 내 기호가 없으면를 `*pCountSymbolBytes = 0`합니다.  
  
> [!NOTE]
> 현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다. 리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
