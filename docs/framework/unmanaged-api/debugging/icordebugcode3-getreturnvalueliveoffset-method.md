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
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178950"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset 메서드
지정된 IL 오프셋의 경우 디버거가 함수에서 반환 값을 얻을 수 있도록 중단점을 배치해야 하는 네이티브 오프셋을 가져옵니다.  
  
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
 IL 오프셋입니다. 함수 호출 사이트이거나 함수 호출이 실패해야 합니다.  
  
 `bufferSize`  
 저장할 `pOffsets`수 있는 바이트 수입니다.  
  
 `pFetched`  
 실제로 반환된 오프셋 수에 대한 포인터입니다. 일반적으로 해당 값은 1이지만 단일 IL 명령은 `CALL` 여러 어셈블리 명령에 매핑할 수 있습니다.  
  
 `pOffsets`  
 네이티브 오프셋의 배열입니다. 일반적으로 `pOffsets` 단일 IL 명령이 여러 `CALL` 어셈블리 명령에 여러 맵에 매핑할 수 있지만 단일 오프셋이 포함되어 있습니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드와 함께 참조 형식을 반환 하는 메서드의 반환 값을 가져옵니다. IL 오프셋을 함수 호출 사이트에 이 메서드에 전달하면 하나 이상의 네이티브 오프셋이 반환됩니다. 그런 다음 디버거는 함수의 이러한 네이티브 오프셋에 중단점을 설정할 수 있습니다. 디버거가 중단점 중 하나에 도달하면 이 메서드에 전달한 것과 동일한 IL 오프셋을 [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드에 전달하여 반환 값을 얻을 수 있습니다. 그런 다음 디버거가 설정한 모든 중단점을 지워야 합니다.  
  
> [!WARNING]
> `ICorDebugCode3::GetReturnValueLiveOffset` 및 [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드를 사용하면 참조 형식에 대해서만 반환 값 정보를 얻을 수 있습니다. 값 형식(즉, 파생되는 모든 <xref:System.ValueType>형식)에서 반환 값 정보를 검색하는 것은 지원되지 않습니다.  
  
 함수는 다음 `HRESULT` 표에 표시된 값을 반환합니다.  
  
|`HRESULT` 값|Description|  
|---------------------|-----------------|  
|`S_OK`|성공했습니다.|  
|`CORDBG_E_INVALID_OPCODE`|지정된 IL 오프셋 사이트는 호출 명령이 아니거나 함수가 반환됩니다. `void`|  
|`CORDBG_E_UNSUPPORTED`|지정된 IL 오프셋은 적절한 호출이지만 반환 형식은 반환 값을 가져오는 데 지원되지 않습니다.|  
  
 이 `ICorDebugCode3::GetReturnValueLiveOffset` 방법은 x86 기반 및 AMD64 시스템에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetReturnValueForILOffset 메서드](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3 인터페이스](icordebugcode3-interface.md)
