---
title: ICorProfilerInfo5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495629"
---
# <a name="icorprofilerinfo5-interface"></a>ICorProfilerInfo5 인터페이스
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 코드 프로파일러가 CLR (공용 언어 런타임)과 통신 하 여 이벤트 모니터링을 제어 하는 데 사용할 메서드를 제공 하는 [ICorProfilerInfo4](icorprofilerinfo4-interface.md) 의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[GetEventMask2 메서드](icorprofilerinfo5-geteventmask2-method.md)|프로파일러가 CLR에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.|  
|[SetEventMask2 메서드](icorprofilerinfo5-seteventmask2-method.md)|프로파일러가 CLR에서 이벤트 알림을 받으려는 이벤트 형식을 지정하는 값을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스에서 사용할 수 있는 메서드는 [ICorProfilerInfo:: geteventmask](icorprofilerinfo-geteventmask-method.md) 및 [ICorProfilerInfo:: seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드를 대체 하기 위한 것입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
