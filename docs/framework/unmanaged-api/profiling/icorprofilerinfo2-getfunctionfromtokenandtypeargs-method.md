---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 945cf84e6f6201879514e29a21f7f5462aa33fdb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868670"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드
지정 된 메타 데이터 토큰, 포함 하는 클래스 및 형식 인수의 `ClassID` 값을 사용 하 여 함수의 `FunctionID`를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 진행 함수가 상주 하는 모듈의 ID입니다.  
  
 `funcDef`  
 진행 함수를 참조 하는 `mdMethodDef` 메타 데이터 토큰입니다.  
  
 `classId`  
 진행 함수를 포함 하는 클래스의 ID입니다.  
  
 `cTypeArgs`  
 진행 지정 된 함수에 대 한 형식 매개 변수의 수입니다. 제네릭이 아닌 함수의 경우이 값은 0 이어야 합니다.  
  
 `typeArgs`  
 진행 각각 함수의 인수인 `ClassID` 값의 배열입니다. `cTypeArgs`가 0으로 설정 된 경우 `typeArgs`의 값은 NULL 일 수 있습니다.  
  
 `pFunctionID`  
 제한이 지정 된 함수의 `FunctionID`에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `mdMethodDef` 메타 데이터 토큰 대신 `mdMethodRef` 메타 데이터를 사용 하 여 `GetFunctionFromTokenAndTypeArgs` 메서드를 호출 하면 예기치 않은 결과가 발생할 수 있습니다. 호출자는 `mdMethodRef`를 전달할 때 `mdMethodDef`를 확인 해야 합니다.  
  
 함수가 아직 로드 되지 않은 경우 `GetFunctionFromTokenAndTypeArgs`를 호출 하면 로드가 발생 하며이는 많은 컨텍스트에서 위험한 작업입니다. 예를 들어 모듈이 나 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에서 순환적으로 자신 로드를 시도 하는 경우 무한 루프가 발생할 수 있습니다.  
  
 일반적으로 `GetFunctionFromTokenAndTypeArgs`는 사용 하지 않는 것이 좋습니다. 프로파일러가 특정 함수에 대 한 이벤트에 관심이 있는 경우 해당 함수의 `ModuleID` 및 `mdMethodDef`을 저장 하 고, [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 를 사용 하 여 지정 된 `FunctionID`이 원하는 함수의 함수 인지 여부를 확인 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
