---
title: ICorProfilerInfo::GetClassFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863955"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>ICorProfilerInfo::GetClassFromToken 메서드
메타 데이터 토큰이 지정 된 경우 클래스의 ID를 가져옵니다. 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 진행 클래스가 포함 된 모듈의 ID입니다.  
  
 `typeDef`  
 진행 클래스를 참조 하는 `mdTypeDef` 메타 데이터 토큰입니다.  
  
 `cTypeArgs`  
 제한이 클래스 ID에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 사용 되지 않습니다. 대신 모든 형식에 대해 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
