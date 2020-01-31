---
title: ICorProfilerInfo2::GetContextStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: d99e5000cdd0d7252764554025815dbace2289f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868683"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress 메서드
지정 된 컨텍스트 범위에 있는 지정 된 컨텍스트 정적 필드의 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>매개 변수  
 `classId`  
 진행 요청 된 컨텍스트 정적 필드를 포함 하는 클래스의 ID입니다.  
  
 `fieldToken`  
 진행 요청 된 컨텍스트 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `contextId`  
 진행 요청 된 컨텍스트 정적 필드에 대 한 범위인 컨텍스트의 ID입니다.  
  
 `ppAddress`  
 제한이 지정 된 컨텍스트 내에 있는 정적 필드의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `GetContextStaticAddress` 메서드는 다음 중 하나를 반환할 수 있습니다.  
  
- 지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.  
  
- 가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다. 이러한 주소는 가비지 수집 후에 무효화 될 수 있으므로 가비지 수집 후 프로파일러는 이러한 주소를 유효한 것으로 가정 하지 않아야 합니다.  
  
 클래스의 클래스 생성자가 `GetContextStaticAddress` 완료 되기 전에는 정적 필드 중 일부는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있는 경우에도 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
