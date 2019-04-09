---
title: ICorDebugCode3::GetReturnValueLiveOffset 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03ee275336d3ae71f63d82add694fe1308efbe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125939"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset 메서드
지정된 된 IL 오프셋에 대 한 디버거 함수에서 반환 값을 얻을 수 있도록 중단점을 배치할 위치 네이티브 오프셋을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ILoffset`  
 IL 오프셋입니다. 함수 호출 사이트 여야 합니다 또는 함수 호출이 실패 합니다.  
  
 `bufferSize`  
 저장할 수 있는 바이트 수가 `pOffsets`합니다.  
  
 `pFetched`  
 실제로 반환 된 오프셋 수에 대 한 포인터입니다. 일반적으로 해당 값은 1 이지만 단일 IL 지침은 여러 매핑할 수 있습니다 `CALL` 어셈블리 명령입니다.  
  
 `pOffsets`  
 네이티브 오프셋의 배열입니다. 일반적으로 `pOffsets` 단일 IL 지침은 여러 여러 맵을 매핑할 수 있지만 단일 오프셋이 포함 `CALL` 어셈블리 명령입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 함께 사용 합니다 [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 참조 형식을 반환 하는 메서드의 반환 값을 가져오는 방법입니다. 이 메서드는 함수 호출 사이트에 대 한 오프셋 IL 전달 하나 이상의 네이티브 오프셋을 반환 합니다. 디버거는 함수의 이러한 네이티브 오프셋에서 중단점을 설정할 수 있습니다. 디버거가 중단점 중 하나에 도달 하면 전달 하면이 메서드를 전달 하는 동일한 IL 오프셋 합니다 [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 반환 값을 가져오는 방법입니다. 디버거가 모든 중단점을 설정 하는 것을 지워야 합니다.  
  
> [!WARNING]
>  합니다 `ICorDebugCode3::GetReturnValueLiveOffset` 및 [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드 참조 형식만 대 한 반환 값 정보를 가져올 수 있습니다. 값 형식에서 반환 값 정보 검색 (에서 파생 되는 모든 형식 즉, <xref:System.ValueType>) 지원 되지 않습니다.  
  
 반환 된 `HRESULT` 다음 표에 나와 있는 값입니다.  
  
|`HRESULT` 값|설명|  
|---------------------|-----------------|  
|`S_OK`|명령 실행 성공|  
|`CORDBG_E_INVALID_OPCODE`|지정된 된 IL 오프셋된 사이트 호출 명령이 아니거나 함수가 반환 `void`합니다.|  
|`CORDBG_E_UNSUPPORTED`|지정된 된 IL 오프셋은 적절 한 호출 이지만 반환 형식은 반환 값 가져오기에 대 한 지원 되지 않습니다.|  
  
 `ICorDebugCode3::GetReturnValueLiveOffset` 메서드는 x86 기반 및 AMD64 시스템입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [GetReturnValueForILOffset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
