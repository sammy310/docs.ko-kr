---
title: ICorDebugILFrame3::GetReturnValueForILOffset 메서드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178810"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset 메서드
함수의 반환 값을 캡슐화하는 "ICorDebugValue" 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ILOffset`  
 IL 오프셋입니다. 주의 섹션을 참조하십시오.  
  
 `ppReturnValue`  
 함수 호출의 반환 값에 대한 정보를 제공하는 "ICorDebugValue" 인터페이스 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드와 함께 사용 되어 메서드의 반환 값을 가져옵니다. 다음 두 코드 예제와 같이 반환 값이 무시되는 메서드의 경우 특히 유용합니다. 첫 번째 예제에서는 메서드를 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 호출하지만 메서드의 반환 값을 무시합니다.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 두 번째 예제에서는 디버깅에서 훨씬 더 일반적인 문제를 보여 줍니다. 메서드는 메서드 호출에서 인수로 사용되므로 디버거가 호출된 메서드를 단계화할 때만 반환 값에 액세스할 수 있습니다. 대부분의 경우, 특히 호출된 메서드가 외부 라이브러리에서 정의된 경우 불가능합니다.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드함수 오프셋함수 호출 사이트에 전달 하면 하나 이상의 네이티브 오프셋을 반환 합니다. 그런 다음 디버거는 함수의 이러한 네이티브 오프셋에 중단점을 설정할 수 있습니다. 디버거가 중단점 중 하나에 도달하면 반환 값을 얻기 위해 이 메서드에 전달한 것과 동일한 IL 오프셋을 전달할 수 있습니다. 그런 다음 디버거가 설정한 모든 중단점을 지워야 합니다.  
  
> [!WARNING]
> [ICorDebugCode3:GetReturnValueLiveOffset 메서드](icordebugcode3-getreturnvalueliveoffset-method.md) 및 `ICorDebugILFrame3::GetReturnValueForILOffset` 메서드를 사용하면 참조 형식에 대해서만 반환 값 정보를 얻을 수 있습니다. 값 형식(즉, 파생되는 모든 <xref:System.ValueType>형식)에서 반환 값 정보를 검색하는 것은 지원되지 않습니다.  
  
 매개 변수에 `ILOffset` 의해 지정된 IL 오프셋은 함수 호출 사이트에 있어야 하며, 디버그지는 동일한 IL 오프셋에 대해 [ICorDebugCode3:GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드에서 반환되는 네이티브 오프셋의 중단점 집합에서 중지되어야 합니다. 지정된 IL 오프셋의 올바른 위치에서 디버그가 중지되지 않으면 API가 실패합니다.  
  
 함수 호출이 값을 반환하지 않으면 API가 실패합니다.  
  
 이 `ICorDebugILFrame3::GetReturnValueForILOffset` 방법은 x86 기반 및 AMD64 시스템에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetReturnValueLiveOffset 메서드](icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3 인터페이스](icordebugilframe3-interface.md)
