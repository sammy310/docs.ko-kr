---
description: '자세히 알아보기: ICorProfilerInfo11:: GetEnvironmentVariable 메서드'
title: 'ICorProfilerInfo11:: GetEnvironmentVariable 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.GetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 635c5fb67b880c39f15fbc194a51a706d9ef7fe4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805833"
---
# <a name="icorprofilerinfo11getenvironmentvariable-method"></a>ICorProfilerInfo11:: GetEnvironmentVariable 메서드

프로세스에서 환경 변수를 가져옵니다. Windows가 아닌 플랫폼에서 런타임은 환경 변수의 내부 캐시를 유지 하 여 스레드 안전을 보장 합니다. 즉,을 호출 `getenv` 하면 시작 후 프로세스에서 실행 되는 관리 코드에 의해 설정 된 새 환경 변수 또는 업데이트 된 환경 변수는 읽지 않습니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT GetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in]         ULONG cchValue,
                [out]        ULONG *pcchValue,
                [out, annotation("_Out_writes_to_(cchValue, *pcchValue)")]
                             WCHAR szValue[]);
```  
  
## <a name="parameters"></a>매개 변수

`szName` 진행 가져올 환경 변수의 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.

`cchValue` 진행 의 길이 (문자) `szValue` 입니다.

`pcchValue` 제한이 의 총 문자 길이에 대 한 포인터 `szValue` 입니다.

`szValue` 제한이 호출자가 와이드 문자 버퍼를 제공 했습니다. 함수가 반환 될 때 버퍼에는 환경 변수 값이 포함 됩니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo11 인터페이스](icorprofilerinfo11-interface.md)
