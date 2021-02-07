---
description: '자세히 알아보기: ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs 메서드'
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 810445d2617beff55e00df6bb30130d81c740ba4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760494"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드

지정 된 `ClassID` 메타 데이터 토큰 및 `ClassID` 모든 형식 인수 값을 사용 하 여 형식의를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleID`  
 진행 형식이 있는 모듈의 ID입니다.  
  
 `typeDef`  
 진행 `mdTypeDef` 형식을 참조 하는 메타 데이터 토큰입니다.  
  
 `cTypeArgs`  
 진행 지정 된 형식에 대 한 형식 매개 변수의 수입니다. 제네릭이 아닌 형식에 대해서는이 값이 0 이어야 합니다.  
  
 `typeArgs`  
 진행 `ClassID` 각각 형식의 인수인 값의 배열입니다. `typeArgs`가 0으로 설정 된 경우 값은 NULL 일 수 있습니다 `cTypeArgs` .  
  
 `pClassID`  
 제한이 지정 된 형식의에 대 한 포인터 `ClassID` 입니다.  
  
## <a name="remarks"></a>설명  

 `GetClassFromTokenAndTypeArgs`메타 데이터 토큰 대신를 사용 하 여 메서드를 호출 하면 `mdTypeRef` `mdTypeDef` 예기치 않은 결과가 발생할 수 있습니다 `mdTypeRef` . 호출자는 `mdTypeDef` 전달 될 때를로 확인 해야 합니다.  
  
 형식이 아직 로드 되지 않은 경우를 호출 하면 `GetClassFromTokenAndTypeArgs` 많은 컨텍스트에서 위험한 작업 인 로드를 트리거합니다. 예를 들어 모듈이 나 기타 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에서 순환적으로 자신 로드를 시도 하는 경우 무한 루프가 발생할 수 있습니다.  
  
 일반적으로는 사용 하지 `GetClassFromTokenAndTypeArgs` 않는 것이 좋습니다. 프로파일러가 특정 형식에 대 한 이벤트에 관심이 있는 경우 해당 형식의 및를 저장 하 `ModuleID` `mdTypeDef` 고, [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) 를 사용 하 여 지정 된가 원하는 형식의 인지 여부를 확인 해야 합니다 `ClassID` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
