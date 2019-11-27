---
title: ICorProfilerCallback2::RootReferences2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: dffd4365669da61f7b321110ad663c131ce591e6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439675"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2 메서드
가비지 수집이 발생 한 후 루트 참조에 대해 프로파일러에 알립니다. 이 메서드는 [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 메서드를 확장 한 것입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cRootRefs`  
 진행 `rootRefIds`, `rootKinds`, `rootFlags`및 `rootIds` 배열의 요소 수입니다.  
  
 `rootRefIds`  
 진행 각각 정적 개체 또는 스택의 개체를 참조 하는 개체 Id의 배열입니다. `rootKinds` 배열의 요소는 `rootRefIds` 배열에서 해당 요소를 분류 하는 정보를 제공 합니다.  
  
 `rootKinds`  
 진행 가비지 컬렉션 루트의 형식을 나타내는 [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) 값의 배열입니다.  
  
 `rootFlags`  
 진행 가비지 컬렉션 루트의 속성을 설명 하는 [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) 값의 배열입니다.  
  
 `rootIds`  
 진행 `rootKinds` 매개 변수의 값에 따라 가비지 컬렉션 루트에 대 한 추가 정보를 포함 하는 정수를 가리키는 UINT_PTR 값의 배열입니다.  
  
 루트의 형식이 스택이 면 해당 변수를 포함 하는 함수에 대 한 루트 ID입니다. 루트 ID가 0 이면 함수는 CLR의 내부에 있는 명명 되지 않은 함수입니다. 루트의 형식이 핸들 인 경우 루트 ID는 가비지 수집 핸들의입니다. 다른 루트 형식의 경우 ID는 불투명 값 이므로 무시 해야 합니다.  
  
## <a name="remarks"></a>주의  
 `rootRefIds`, `rootKinds`, `rootFlags`및 `rootIds` 배열은 병렬 배열입니다. 즉, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`및 `rootIds[i]` 모두 동일한 루트를 고려 합니다.  
  
 프로파일러에 알리기 위해 `RootReferences`와 `RootReferences2`를 모두 호출 합니다. `RootReferences2` 전달 되는 정보는 `RootReferences`에 전달 된 상위 집합 이므로 프로파일러는 일반적으로 하나의 메서드 또는 다른 메서드를 구현 합니다.  
  
 `rootRefIds`의 항목이 0 일 수 있습니다 .이는 해당 루트 참조가 null이 고 관리 되는 힙에서 개체를 참조 하지 않음을 의미 합니다.  
  
 가비지 수집은 이전 주소에서 새 주소로 개체를 이동 하는 중일 수 있기 때문에 `RootReferences2`에서 반환 하는 개체 Id는 콜백 자체에서 유효 하지 않습니다. 그러므로 프로파일러는 `RootReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다. [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 모든 개체가 새 위치로 이동 되었으며 안전 하 게 검사할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
