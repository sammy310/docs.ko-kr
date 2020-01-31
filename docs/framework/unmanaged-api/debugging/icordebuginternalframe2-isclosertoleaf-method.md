---
title: ICorDebugInternalFrame2::IsCloserToLeaf 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 5dd93dcc29ace6573e313f732c45af0dfbb900e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782221"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf 메서드
`this` 내부 프레임이 지정 된 ICorDebugFrame 개체 보다 리프에 가까이 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFrameToCompare`  
 진행 비교 `ICorDebugFrame` 개체에 대 한 포인터입니다.  
  
 `pIsCloser`  
 [out] `this` 내부 프레임이 `pFrameToCompare`으로 지정 된 프레임 보다 리프에 가까이 있으면 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|비교가 성공적으로 수행 되었습니다.|  
|E_FAIL|비교를 수행할 수 없습니다.|  
|E_INVALIDARG|`pFrameToCompare` 또는 `pIsCloser`이 null입니다.|  
  
## <a name="remarks"></a>주의  
 `IsCloserToLeaf`를 사용 하 여 스택의 다른 프레임과 내부 프레임을 인터리브 하는 정책을 구현할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugInternalFrame2 인터페이스](icordebuginternalframe2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
