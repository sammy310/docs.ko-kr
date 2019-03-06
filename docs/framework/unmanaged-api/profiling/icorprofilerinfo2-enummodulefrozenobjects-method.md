---
title: ICorProfilerInfo2::EnumModuleFrozenObjects 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a325c3e1aa9c08e00dc2cc38e3f7833fa9f99897
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472579"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>ICorProfilerInfo2::EnumModuleFrozenObjects 메서드
지정된 된 모듈에 고정된 된 개체를 반복할 수 있는 열거자를 가져옵니다. 이 메서드는 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] 열거할 고정된 된 개체를 포함 하는 모듈의 ID입니다.  
  
 `ppEnum`  
 [out] 주소에 대 한 포인터를 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) 고정된 된 개체를 열거 하는 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
