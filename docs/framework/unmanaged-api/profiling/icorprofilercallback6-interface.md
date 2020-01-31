---
title: ICorProfilerCallback6 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864871"
---
# <a name="icorprofilercallback6-interface"></a>ICorProfilerCallback6 인터페이스
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 공용 언어 런타임에서 어셈블리를 로드 하 고 있음을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAssemblyReferences 메서드](icorprofilercallback6-getassemblyreferences-method.md)|공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
