---
title: 'ICorProfilerInfo7:: ApplyMetaData 메서드'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130360"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: ApplyMetaData 메서드
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 `IMetadataEmit::Define*` 메서드에 의해 새로 정의 된 메타 데이터를 지정 된 모듈에 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 진행 메타 데이터가 변경 된 모듈의 식별자입니다.  
  
## <a name="remarks"></a>주의  
 [Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백을 수행한 후 메타 데이터를 변경 하는 경우 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.  
  
 `ApplyMetaData`는 다음 형식의 메타 데이터를 추가 하는 것만 지원 합니다.  
  
- `AssemblyRef` 레코드- [IMetaDataAssemblyEmit::D efineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)를 호출 하 여 만듭니다. 메서드를 재정의합니다.  
  
- `TypeRef` 레코드- [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 메서드를 호출 하 여 만듭니다.  
  
- `TypeSpec` 레코드- [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드를 호출 하 여 만듭니다.  
  
- `MemberRef` 레코드- [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드를 호출 하 여 만듭니다.  
  
- `MemberSpec` 레코드- [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) 메서드를 호출 하 여 만듭니다.  
  
- `UserString` 레코드- [IMetaDataEmit::D efineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드를 호출 하 여 만듭니다.  

.NET Core 3.0부터 `ApplyMetaData`는 다음 유형도 지원 합니다.

- [IMetaDataEmit::D Efin def](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드를 호출 하 여 만드는 레코드를 `TypeDef` 합니다.

- `MethodDef` 레코드- [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) 메서드를 호출 하 여 만듭니다. 그러나 기존 형식에 가상 메서드를 추가 하는 것은 지원 되지 않습니다. 가상 메서드는 [Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 전에 추가 해야 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
