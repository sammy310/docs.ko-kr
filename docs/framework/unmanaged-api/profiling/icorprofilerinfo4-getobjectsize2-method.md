---
title: ICorProfilerInfo4::GetObjectSize2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 441f7743ba01884592393ce9382348fbecaeaa9d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861881"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2 메서드
지정 된 개체의 크기를 반환 합니다. `ULONG`표현할 수 있는 것 보다 큰 개체의 크기를 보고 하 여 [ICorProfilerInfo:: GetObjectSize](icorprofilerinfo-getobjectsize-method.md) 메서드를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 진행 개체의 ID입니다.  
  
 `pcSize`  
 제한이 개체의 크기 (바이트)에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 동일한 유형의 개체 마다 크기가 같은 경우가 많습니다. 그러나 배열 또는 문자열과 같은 일부 형식에는 각 개체에 대해 다른 크기를 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
