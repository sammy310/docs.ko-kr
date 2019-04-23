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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153324"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림에서 바이트를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
 [in] 메모리 스트림이 포함 된 모듈의 식별자입니다.  
  
 `symbolsReadOffset`  
 [in] 바이트 읽기를 시작 하는 메모리 내 스트림 내의 오프셋입니다.  
  
 `pSymbolBytes`  
 [out] 데이터를 복사할 대상 버퍼에 대 한 포인터입니다. 버퍼 있어야 `countSymbolBytes` 사용 가능한 공간입니다.  
  
 `countSymbolBytes`  
 [in] 복사할 바이트 수입니다.  
  
 `pCountSymbolBytesRead`  
 [out] 메서드는 반환 될 때 실제 읽은 바이트 수를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`에서 읽을 바이트 수를 0이 아닌 경우.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`를 사용 하 여 모듈을 만든 경우 <xref:System.Reflection.Emit>합니다.  
  
## <a name="remarks"></a>설명  
 합니다 `ReadInMemorySymbols` 메서드 판독 하 려 `countSymbolBytes` 오프셋에서 시작 하는 데이터의 `symbolsReadOffset` 메모리 스트림 내에서. 데이터를 복사할 `pSymbolBytes`, 것으로 예상 되는 `countSymbolBytes` 사용 가능한 공간입니다.     `pCountSymbolsBytesRead` 실제 읽은 작은 일 수 있는 바이트 수가 포함 보다 `countSymbolBytes` 스트림의 맨 끝에 도달한 경우입니다.  
  
> [!NOTE]
>  현재 구현에서는 Reflection.Emit을 지원 하지 않습니다. 메서드가 반환 하는 경우 모듈을 Reflection.Emit을 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
