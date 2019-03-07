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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a74e99e0b669c1b3d8e36d881391f27ef71ae306
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493546"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>ICorProfilerInfo::GetClassFromToken 메서드
메타 데이터 토큰을 지정 하는 클래스의 ID를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] 클래스를 포함 하는 모듈의 ID입니다.  
  
 `typeDef`  
 [in] `mdTypeDef` 클래스를 참조 하는 메타 데이터 토큰입니다.  
  
 `cTypeArgs`  
 [out] 클래스 ID에 대 한 포인터  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용 되지 않습니다. 대신 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` 모든 형식에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
