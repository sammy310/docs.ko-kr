---
title: ICorProfilerInfo2::GetStringLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d4efa7cb3bc98c54be2889855c3b756fdbf2847
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782239"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 메서드
문자열 개체의 레이아웃 정보를 가져옵니다. 이 메서드는.NET Framework 4에서는 사용 되지 않습니다 및으로 인해 교체 되는 [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBufferLengthOffset`  
 [out] 에 상대적인 위치 오프셋에 대 한 포인터를 `ObjectID` 문자열의 길이 저장 하는 포인터입니다. 로 저장 되는 `DWORD`합니다.  
  
> [!NOTE]
>  이 매개 변수 버퍼의 길이가 아닌 문자열 자체의 길이 반환 합니다. 버퍼의 길이가 더 이상 사용할 수 없습니다.  
  
 `PStringLengthOffset`  
 [out] 에 상대적인 위치 오프셋에 대 한 포인터를 `ObjectID` 자체 문자열의 길이 저장 하는 포인터입니다. 로 저장 되는 `DWORD`합니다.  
  
 `pBufferOffset`  
 [out] 기준으로 버퍼의 오프셋에 대 한 포인터를 `ObjectID` 와이드 문자 문자열을 저장 하는 포인터입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `GetStringLayout` 메서드는 상대적으로 오프셋을 가져옵니다는 `ObjectID` 다음 저장 되는 위치의 포인터:  
  
- 문자열 버퍼의 길이입니다.  
  
- 자체 문자열의 길이입니다.  
  
- 와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.  
  
 문자열은 null로 종료 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
