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
ms.openlocfilehash: 71e2bc1d60e050d817429db5bc6926b3b16c637c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431412"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 메서드
문자열 개체의 레이아웃 정보를 가져옵니다. 이 메서드는 .NET Framework 4에서 더 이상 사용 되지 않으며 [ICorProfilerInfo3:: GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드로 대체 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBufferLengthOffset`  
 제한이 문자열의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다. 길이는 `DWORD`로 저장 됩니다.  
  
> [!NOTE]
> 이 매개 변수는 버퍼의 길이가 아니라 문자열 자체의 길이를 반환 합니다. 버퍼의 길이는 더 이상 사용할 수 없습니다.  
  
 `PStringLengthOffset`  
 제한이 문자열 자체의 길이를 저장 하는 `ObjectID` 포인터를 기준으로 하는 위치의 오프셋에 대 한 포인터입니다. 길이는 `DWORD`로 저장 됩니다.  
  
 `pBufferOffset`  
 제한이 와이드 문자 문자열을 저장 하는 `ObjectID` 포인터를 기준으로 하는 버퍼의 오프셋에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetStringLayout` 메서드는 `ObjectID` 포인터를 기준으로 다음이 저장 된 위치의 오프셋을 가져옵니다.  
  
- 문자열 버퍼의 길이입니다.  
  
- 문자열 자체의 길이입니다.  
  
- 와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.  
  
 문자열이 null로 종료 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
