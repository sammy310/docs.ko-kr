---
description: '자세히 알아보기: ICorDebugCode 인터페이스'
title: ICorDebugCode 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: ce67c48501783bbe00152f0ba2c224e6e7dde6d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711156"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode 인터페이스

MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](icordebugcode-createbreakpoint-method.md)|지정 된 오프셋에 중단점을 만듭니다.|  
|[GetAddress 메서드](icordebugcode-getaddress-method.md)|이가 나타내는 코드 세그먼트의 RVA (상대 가상 주소)를 가져옵니다 `ICorDebugCode` .|  
|[GetCode 메서드](icordebugcode-getcode-method.md)|지정 된 함수에 대 한 코드를 모두 가져오고 디스어셈블리에 맞게 형식이 지정 됩니다. 이 메서드는 더 이상 사용 되지 않습니다. 대신 [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) 를 사용 합니다.|  
|[GetEnCRemapSequencePoints 메서드](icordebugcode-getencremapsequencepoints-method.md)|구현되지 않았습니다.|  
|[GetFunction 메서드](icordebugcode-getfunction-method.md)|이와 연결 된 "ICorDebugFunction"를 가져옵니다 `ICorDebugCode` .|  
|[GetILToNativeMapping 메서드](icordebugcode-getiltonativemapping-method.md)|MSIL 오프셋과 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.|  
|[GetSize 메서드](icordebugcode-getsize-method.md)|이가 나타내는 이진 코드의 크기 (바이트)를 가져옵니다 `ICorDebugCode` .|  
|[GetVersionNumber 메서드](icordebugcode-getversionnumber-method.md)|이가 나타내는 코드의 버전을 식별 하는 1부터 사용 하는 번호를 가져옵니다 `ICorDebugCode` .|  
|[IsIL 메서드](icordebugcode-isil-method.md)|이이 MSIL로 컴파일 되었는지 여부를 나타내는 값을 가져옵니다 `ICorDebugCode` .|  
  
## <a name="remarks"></a>설명  

 `ICorDebugCode` MSIL 또는 네이티브 코드를 나타낼 수 있습니다. MSIL 코드를 나타내는 "ICorDebugFunction" 개체에는 0 개 또는 하나의 개체가 연결 될 수 있습니다 `ICorDebugCode` . 네이티브 코드를 나타내는 "ICorDebugFunction" 개체에는 연결 된 개체가 여러 개 있을 수 있습니다 `ICorDebugCode` .  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugCode3 인터페이스](icordebugcode3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
