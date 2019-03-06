---
title: ICorProfilerInfo::GetObjectSize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42e86b1eac788b709432d39e320ebea49c696c14
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481706"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize 메서드
지정된 된 개체의 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 개체의 ID입니다.  
  
 `pcSize`  
 [out] 개체의 크기 (바이트)에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  이 메서드는 사용되지 않습니다. 반환 COR_E_OVERFLOW 개체에 대 한 4GB 보다 큰 64 비트 플랫폼에서 합니다. 사용 된 [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) 메서드 대신 합니다.  
  
 동일한 유형의 다른 개체에는 동일한 크기가 있는 경우가 많습니다. 그러나 배열 또는 문자열 같은 일부 유형의 경우에 각 개체에 대해 다른 크기가 있을 수 있습니다.  
  
 반환 되는 크기는 `GetObjectSize` 메서드는 개체가 가비지 컬렉션 힙에 후 나타날 수 있는 맞춤 안쪽 여백을 포함 되지 않습니다. 사용 하는 경우는 `GetObjectSize` 메서드 가비지 컬렉션 힙에 개체에서 개체를 수동으로 필요에 따라 패딩 맞춤을 추가 합니다.  
  
-   32 비트 Windows에서 COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, 및 COR_PRF_GC_GEN_2 4 바이트 맞춤을 사용 하 고 COR_PRF_GC_LARGE_OBJECT_HEAP 8 바이트 정렬을 사용 합니다.  
  
-   64 비트 Windows에 맞춤은 항상 8 바이트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
