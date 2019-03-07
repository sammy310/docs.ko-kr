---
title: ICorProfilerInfo2::GetArrayObjectInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7fe86fbe7ee51e5f53eeea74d7d5a56046de5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484396"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo 메서드
배열 개체에 대 한 자세한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] ID는 유효한 배열 개체입니다.  
  
 `cDimensions`  
 [in] 배열의 순위 (차원의 수)입니다.  
  
 `pDimensionSizes`  
 [out] 각 배열 차원의 크기를 나타내는 정수를 포함 하는 배열입니다.  
  
 `pDimensionLowerBounds`  
 [out] 배열 차원의 바인딩된 아래쪽을 나타내는 각 정수를 포함 하는 배열입니다.  
  
 `ppData`  
 [out] C + + 규칙에 따라 배치 되는 배열에 대해 원시 버퍼의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `pDimensionSizes` 고 `pDimensionLowerBounds` 병렬 배열 되므로 각 배열에 있는 동일한 인덱스에 있는 요소는 동일한 엔터티의 특성입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
