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
ms.openlocfilehash: de6d46897f3d3266bf708528efd712ca7db8ea4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438833"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize 메서드
지정 된 개체의 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 진행 개체의 ID입니다.  
  
 `pcSize`  
 제한이 개체의 크기 (바이트)에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
  
> [!IMPORTANT]
> 이 메서드는 사용되지 않습니다. 64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 COR_E_OVERFLOW를 반환 합니다. 대신 [ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) 메서드를 사용 합니다.  
  
 동일한 유형의 개체 마다 크기가 같은 경우가 많습니다. 그러나 배열 또는 문자열과 같은 일부 형식에는 각 개체에 대해 다른 크기를 사용할 수 있습니다.  
  
 `GetObjectSize` 메서드에서 반환 되는 크기에는 개체가 가비지 컬렉션 힙에 있는 후에 나타날 수 있는 맞춤 패딩이 포함 되지 않습니다. `GetObjectSize` 메서드를 사용 하 여 가비지 수집 힙의 개체에서 개체로 이동 하는 경우 필요에 따라 맞춤 안쪽 여백을 수동으로 추가 합니다.  
  
- 32 비트 Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 및 COR_PRF_GC_GEN_2 4 바이트 맞춤을 사용 하 고 COR_PRF_GC_LARGE_OBJECT_HEAP에서는 8 바이트 맞춤을 사용 합니다.  
  
- 64 비트 Windows에서는 맞춤이 항상 8 바이트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
