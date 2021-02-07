---
description: '자세히 알아보기: ICorDebugChain:: GetReason 메서드'
title: ICorDebugChain::GetReason 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: 0952d09db6d43f7970ba9e8c46c409fb2cd4b131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694971"
---
# <a name="icordebugchaingetreason-method"></a>ICorDebugChain::GetReason 메서드

이 호출 체인의 genesis 이유를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pReason`  
 제한이 이 호출 체인의 genesis에 대 한 이유를 나타내는 CorDebugChainReason 열거형의 값 (비트 조합)에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
