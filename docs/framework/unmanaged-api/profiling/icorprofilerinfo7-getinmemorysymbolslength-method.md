---
title: ICorProfilerInfo7::GetInMemorySymbolsLength Method
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c70b97e7af9fdc76c579c5940e2436232f6bc2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748656"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength Method
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림의 길이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 메모리 스트림이 포함 된 모듈의 식별자입니다.  
  
 pCountSymbolBytes  
 [out] 에 대 한 포인터를 `DWORD` 메서드는 반환 될 때 바이트 스트림의 길이 포함 하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 반환 `S_OK` 경우 메모리 스트림의 길이 확인할 수 있습니다, 영 (0) 인 경우라도 합니다.  
  
 메서드는 반환 `CORPROF_E_MODULE_IS_DYNAMIC` 메서드를 사용 하 여 만들어진 경우 <xref:System.Reflection.Emit?displayProperty=nameWithType>합니다.  
  
## <a name="remarks"></a>설명  
 스트림의 길이에 위치한 모듈에 있는 경우 메모리 내 기호, `pCountSymbolBytes`합니다. 모듈 메모리에 기호가 없으면 `*pCountSymbolBytes = 0`합니다.  
  
> [!NOTE]
>  현재 구현에서는 Reflection.Emit을 지원 하지 않습니다. 메서드가 반환 하는 경우 모듈을 Reflection.Emit을 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
