---
title: 'ICorDebugSymbolProvider:: GetTypeProps 메서드'
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: c87d9f6d0a719dae5e532e9c0369a7f9fc03748a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133675"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a>ICorDebugSymbolProvider:: GetTypeProps 메서드
vtable에 RVA(상대 가상 주소)가 제공된 경우 해당 제네릭 매개 변수의 서명 수와 같은 형식의 속성 정보를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tableRva`  
 [in] vtable의 RVA(상대 가상 주소)입니다.  
  
 `cbSignature`  
 [in] `signature` 배열의 크기입니다. 설명 부분을 참조하세요.  
  
 `pcbSignature`  
 [out] [out] 반환된 `signature` 배열의 크기에 대한 포인터입니다.  
  
 `signature`  
 [out] 모든 제네릭 매개 변수의 typespec 서명을 보유하는 버퍼입니다.  
  
## <a name="remarks"></a>주의  
 형식의 `signature` 배열에 필요한 크기를 가져오려면 `cbSignature` 인수를 0으로 설정 하 고를 **null**로 `signature` 합니다. 메서드가 반환되면 `signature` 배열에 필요한 바이트 수가 `pcbSignature`에 포함됩니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [GetMethodProps 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [ICorDebugSymbolProvider 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
