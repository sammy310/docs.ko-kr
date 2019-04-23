---
title: ICorProfilerInfo::IsArrayClass 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 350221ae205636cef82581f3fe11367006dd8b2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072174"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass 메서드
지정된 된 클래스 배열 클래스 인지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>매개 변수  
 `classId`  
 [in] 검사할 클래스의 ID입니다.  
  
 `pBaseElemType`  
 [out] 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.  
  
 `pBaseClassId`  
 [out] 사용 가능한 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.  
  
 `pcRank`  
 [out] 배열의 순위 (차원의 수)를 나타내는 정수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 클래스는 배열 클래스 경우의 `IsArrayClass` 메서드는 S_OK HRESULT 및 null이 아닌 출력 매개 변수 값을 반환 합니다. 그렇지 않으면 S_FALSE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
