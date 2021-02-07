---
description: '자세히 알아보기: ICorDebugFrame:: GetCaller 메서드'
title: ICorDebugFrame::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: a042341f6edfa0e8f6ca00f758107852f9e381cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693046"
---
# <a name="icordebugframegetcaller-method"></a>ICorDebugFrame::GetCaller 메서드

현재 체인에서이 프레임을 호출한 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppFrame`  
 제한이 호출 하는 프레임을 나타내는 개체의 주소에 대 한 포인터입니다 `ICorDebugFrame` . 호출 된 프레임이 현재 체인에서 가장 바깥쪽 프레임 이면이 값은 null입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
