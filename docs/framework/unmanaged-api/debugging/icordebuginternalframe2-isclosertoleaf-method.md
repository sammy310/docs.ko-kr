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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995503"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf 메서드
확인 여부는 `this` 내부 프레임에 더 가까운 리프 지정된 ICorDebugFrame 개체 보다 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFrameToCompare`  
 [in] 비교에 대 한 포인터 `ICorDebugFrame` 개체입니다.  
  
 `pIsCloser`  
 [out] `true` 경우는 `this` 내부 프레임 보다에 더 가까운 리프 지정한 프레임 `pFrameToCompare`이 고, 그렇지 않으면 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|비교는 성공적으로 수행 되었습니다.|  
|E_FAIL|비교를 수행할 수 없습니다.|  
|E_INVALIDARG|`pFrameToCompare` 또는 `pIsCloser`이 null입니다.|  
  
## <a name="remarks"></a>설명  
 `IsCloserToLeaf` 인터리빙 스택의 다른 프레임을 사용 하 여 내부 프레임에 대 한 정책을 구현 하려면 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugInternalFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
