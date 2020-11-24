---
title: ICorDebugFrame::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679717"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper 메서드

디버거가이 ICorDebugFrame에 비해 단계별 작업을 수행할 수 있도록 하는 스텝 퍼를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppStepper`  
 제한이 디버거가 현재 프레임에 상대적인 단계별 작업을 수행할 수 있도록 하는 ICorDebugStepper 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 프레임이 활성화 되어 있지 않으면 단계가 완료 되기 전에 스텝 퍼 개체가 프레임으로 돌아가야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
