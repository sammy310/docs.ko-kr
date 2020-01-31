---
title: ICorDebugNativeFrame::CanSetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792798"
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP 메서드
네이티브 코드에서 지정 된 오프셋 위치로 IP (명령 포인터)를 설정 하는 것이 안전한 지 여부를 나타내는 HRESULT를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `nOffset`  
 진행 명령 포인터에 대 한 원하는 설정입니다.  
  
## <a name="remarks"></a>주의  
 [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 메서드를 호출 하기 전에 `CanSetIP` 메서드를 사용 합니다. `CanSetIP`에서 S_OK 이외의 HRESULT를 반환 하는 경우에도 여전히 `ICorDebugNativeFrame::SetIP`를 호출할 수 있지만 디버거는 디버깅 중인 코드의 안전 하 고 올바른 실행을 계속 보장할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조
