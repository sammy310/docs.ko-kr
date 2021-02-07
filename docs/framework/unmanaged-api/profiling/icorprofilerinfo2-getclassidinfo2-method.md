---
description: '자세히 알아보기: ICorProfilerInfo2:: GetClassIDInfo2 메서드'
title: ICorProfilerInfo2::GetClassIDInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 44ef38b5f50da0f0aea045bd755614e00dae8c22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760516"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>ICorProfilerInfo2::GetClassIDInfo2 메서드

지정 된 클래스의 개방형 제네릭 정의, `ClassID` 부모 클래스의 및 `ClassID` 클래스의 각 형식 인수 (있는 경우)에 대 한 부모 모듈 및 메타 데이터 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `classId`  
 [in] 정보가 검색되는 클래스의 ID입니다.  
  
 `pModuleId`  
 제한이 지정 된 클래스에 대 한 개방형 제네릭 정의의 부모 모듈 ID에 대 한 포인터입니다.  
  
 `pTypeDefToken`  
 제한이 지정 된 클래스의 개방형 제네릭 정의에 대 한 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pParentClassId`  
 [out] 부모 클래스의 ID에 대한 포인터입니다.  
  
 `cNumTypeArgs`  
 [in] `typeArgs` 배열의 크기입니다.  
  
 `pcNumTypeArgs`  
 [out] 사용 가능한 요소의 총수에 대한 포인터입니다.  
  
 `typeArgs`  
 [out] 각각 클래스의 형식 인수 ID를 나타내는 `ClassID` 값의 배열입니다. 메서드가 반환되면 `typeArgs`에 사용 가능한 `ClassID` 값이 일부 또는 모두 포함됩니다.  
  
## <a name="remarks"></a>설명  

 `GetClassIDInfo2`메서드는 [ICorProfilerInfo:: GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) 메서드와 유사 하지만 `GetClassIDInfo2` 제네릭 형식에 대 한 추가 정보를 가져옵니다.  
  
 프로파일러 코드는 [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) 를 호출 하 여 지정 된 모듈에 대 한 [메타 데이터](../metadata/index.md) 인터페이스를 가져올 수 있습니다. 그런 다음 `pTypeDefToken`에서 참조된 위치로 반환되는 메타데이터 토큰을 사용하여 클래스에 대한 메타데이터에 액세스할 수 있습니다.  
  
 `GetClassIDInfo2`가 반환된 후 `typeArgs` 버퍼가 `ClassID` 값을 모두 포함할 수 있을 만큼 충분히 큰지 확인해야 합니다. 이렇게 하려면 `pcNumTypeArgs`가 가리키는 값을 `cNumTypeArgs` 매개 변수의 값과 비교합니다. `pcNumTypeArgs`이 `cNumTypeArgs`보다 큰 값을 가리키는 경우 더 큰 `typeArgs` 버퍼를 할당하고 `cNumTypeArgs`을 더 큰 새 크기로 업데이트한 후 `GetClassIDInfo2`를 다시 호출합니다.  
  
 또는 길이가 0인 `typeArgs` 버퍼로 `GetClassIDInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다. 그런 다음 `typeArgs` 버퍼 크기를 `pcNumTypeArgs`에 반환된 값으로 설정하고 `GetClassIDInfo2`를 다시 호출합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
