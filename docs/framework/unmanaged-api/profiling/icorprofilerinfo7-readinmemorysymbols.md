---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868345"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림에서 바이트를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.  
  
 `symbolsReadOffset`  
 진행 바이트 읽기를 시작할 메모리 내 스트림 내의 오프셋입니다.  
  
 `pSymbolBytes`  
 제한이 데이터가 복사 될 버퍼에 대 한 포인터입니다. 버퍼에 사용 가능한 공간이 `countSymbolBytes` 있어야 합니다.  
  
 `countSymbolBytes`  
 진행 복사할 바이트 수입니다.  
  
 `pCountSymbolBytesRead`  
 제한이 메서드가 반환 될 때 읽은 실제 바이트 수를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 0이 아닌 바이트 수를 읽은 경우 `S_OK`합니다.  
  
 <xref:System.Reflection.Emit>를 사용 하 여 모듈을 만든 경우 `CORPROF_E_MODULE_IS_DYNAMIC`합니다.  
  
## <a name="remarks"></a>주의  
 `ReadInMemorySymbols` 메서드는 메모리 내 스트림 내의 오프셋 `symbolsReadOffset`에서 시작 하는 데이터 `countSymbolBytes`를 읽으려고 시도 합니다. 데이터는 `pSymbolBytes`에 복사 됩니다 .이는 사용 가능한 공간 `countSymbolBytes` 있는 것으로 예상 됩니다.     `pCountSymbolsBytesRead`는 읽은 실제 바이트 수를 포함 하며 스트림의 끝에 도달 하는 경우 `countSymbolBytes` 보다 적을 수 있습니다.  
  
> [!NOTE]
> 현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다. 리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo7 인터페이스](icorprofilerinfo7-interface.md)
