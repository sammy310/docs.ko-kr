---
description: '자세히 알아보기: ICorDebugVariableSymbol:: GetSlotIndex 메서드'
title: ICorDebugVariableSymbol::GetSlotIndex 메서드
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3b5cba06a5e80ffa323d2e6521e9ec4666f6f5f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790557"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>ICorDebugVariableSymbol::GetSlotIndex 메서드

지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pSlotIndex`  
 [out] 지역 변수의 슬롯 인덱스에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 성공하는 경우 `S_OK`입니다. 변수가 함수 인수인 경우 `E_FAIL`입니다.  
  
## <a name="remarks"></a>설명  

 지역 변수의 관리되는 슬롯 인덱스를 사용하여 변수의 메타데이터 정보를 검색할 수 있습니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugVariableSymbol 인터페이스](icordebugvariablesymbol-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
