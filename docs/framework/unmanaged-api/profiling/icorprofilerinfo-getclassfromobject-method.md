---
title: ICorProfilerInfo::GetClassFromObject 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d48006011ae50f1157d357a909eb6c93b25baf7e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496055"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a>ICorProfilerInfo::GetClassFromObject 메서드
가져옵니다 합니다 `ClassID` 지정 된 개체의 해당 `ObjectID`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 가져올 개체의 ID를 `ClassID`입니다.  
  
 `pClassId`  
 [out] 반환 된 포인터 `ClassID`합니다.  
  
## <a name="remarks"></a>설명  
 Null `pClassId` 나타내는 `objectId` 형식이 언로드하는 중입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
