---
title: ICorProfilerInfo::GetFunctionFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863558"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a>ICorProfilerInfo::GetFunctionFromToken 메서드
함수의 ID를 가져옵니다. 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a>주의  
 제네릭 함수 또는 제네릭 형식의 함수에는 `GetFunctionFromToken` 메서드를 사용할 수 없습니다. 이제 사용 되지 않습니다. 모든 함수에 대해 `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
