---
title: ICorDebugInternalFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: 9e333d71505a055cfe27df2c79a102c939bafc9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788472"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2 인터페이스
ICorDebugFrame 개체에 상대적인 스택 주소 및 위치를 비롯하여 내부 프레임에 대한 정보를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetFrameAddress 메서드](icordebuginternalframe2-getframeaddress-method.md)|내부 프레임의 스택 주소를 반환 합니다.|  
|[IsCloserToLeaf 메서드](icordebuginternalframe2-isclosertoleaf-method.md)|`this` 내부 프레임이 지정 된 ICorDebugFrame 개체 보다 리프에 가까이 있는지 확인 합니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 ICorDebugInternalFrame 인터페이스를 확장 합니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
