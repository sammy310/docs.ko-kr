---
description: '자세히 알아보기: ICorProfilerInfo11 인터페이스'
title: ICorProfilerInfo11 인터페이스
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 083714b67d83291f1faada3f673df13f16ef3856
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805625"
---
# <a name="icorprofilerinfo11-interface"></a>ICorProfilerInfo11 인터페이스

 프로세스의 환경 변수를 가져오고 설정 하는 메서드를 제공 하는 [ICorProfilerInfo10](icorprofilerinfo10-interface.md) 의 서브 클래스입니다.
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetEnvironmentVariable 메서드](icorprofilerinfo11-getenvironmentvariable-method.md)|환경 변수를 가져옵니다.|
|[SetEnvironmentVariable 메서드](icorprofilerinfo11-setenvironmentvariable-method.md)|환경 변수를 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  

## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
