---
description: '자세히 알아보기: ICorProfilerInfo7:: ApplyMetaData 메서드'
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
ms.openlocfilehash: 3a4554357ede85d936e8bf9c87c6b9c096dab188
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737131"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: ApplyMetaData 메서드

[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메서드에 의해 새로 정의 된 메타 데이터를 `IMetadataEmit::Define*` 지정 된 모듈에 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleID`  
 진행 메타 데이터가 변경 된 모듈의 식별자입니다.  
  
## <a name="remarks"></a>설명  

 [Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백을 수행한 후 메타 데이터를 변경 하는 경우 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.  
  
 `ApplyMetaData` 에서는 다음 유형의 메타 데이터를 추가할 수 있습니다.  
  
- `AssemblyRef`[IMetaDataAssemblyEmit::D efineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md)를 호출 하 여 만드는 레코드입니다. 메서드를 재정의합니다.  
  
- `TypeRef`[IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) 메서드를 호출 하 여 만드는 레코드.  
  
- `TypeSpec` 레코드는 [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드를 호출 하 여 만듭니다.  
  
- `MemberRef`[IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) 메서드를 호출 하 여 만드는 레코드.  
  
- `MemberSpec`[IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) 메서드를 호출 하 여 만드는 레코드.  
  
- `UserString`[IMetaDataEmit::D efineUserString](../metadata/imetadataemit-defineuserstring-method.md) 메서드를 호출 하 여 만드는 레코드입니다.  

.NET Core 3.0부터는 `ApplyMetaData` 다음 유형도 지원 합니다.

- `TypeDef`[IMetaDataEmit::D Efin def](../metadata/imetadataemit-definetypedef-method.md) 메서드를 호출 하 여 만드는 레코드.

- `MethodDef`[IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) 메서드를 호출 하 여 만드는 레코드. 그러나 기존 형식에 가상 메서드를 추가 하는 것은 지원 되지 않습니다. 가상 메서드는 [Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백 전에 추가 해야 합니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo7 인터페이스](icorprofilerinfo7-interface.md)
