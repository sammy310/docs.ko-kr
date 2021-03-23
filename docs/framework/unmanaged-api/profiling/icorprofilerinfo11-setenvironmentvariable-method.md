---
description: '자세히 알아보기: ICorProfilerInfo11:: SetEnvironmentVariable 메서드'
title: 'ICorProfilerInfo11:: SetEnvironmentVariable 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.SetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 77dc3fc992dec037881573323822dc11481a56be
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805608"
---
# <a name="icorprofilerinfo11setenvironmentvariable-method"></a>ICorProfilerInfo11:: SetEnvironmentVariable 메서드

프로세스의 환경 변수를 설정 합니다. Windows가 아닌 플랫폼에서 런타임은 환경 변수의 내부 캐시를 유지 하 여 스레드 안전을 보장 합니다. 즉, 프로파일러가 새 환경 변수를 호출 하는 경우 `setenv` 프로세스에서 실행 되는 관리 코드에 의해 선택 되지 않습니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT SetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in, string] const WCHAR *szValue);
```  
  
## <a name="parameters"></a>매개 변수

`szName` 진행 설정할 환경 변수의 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.

`szValue` 진행 설정할 환경 변수의 값을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo11 인터페이스](icorprofilerinfo11-interface.md)
