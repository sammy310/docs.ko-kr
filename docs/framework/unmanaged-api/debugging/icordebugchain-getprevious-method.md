---
title: ICorDebugChain::GetPrevious 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fdcdf23dfee01e8bad1c95adb4de66f270d5e00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645268"
---
# <a name="icordebugchaingetprevious-method"></a>ICorDebugChain::GetPrevious 메서드
스레드에 대 한 이전 프레임 체인을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppChain`  
 [out] 이전이 스레드에 대 한 프레임 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다. 이 체인의 첫 번째 체인 경우 `ppChain` null입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
