---
description: '자세히 알아보기: ICorDebugFrame:: GetStackRange 메서드'
title: ICorDebugFrame::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 1f1278e0c00addc3c14f4e1c8d3ed5aad0381526
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692903"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange 메서드

이 스택 프레임의 절대 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pStart`  
 제한이 `CORDB_ADDRESS` 이 개체가 나타내는 스택 프레임의 시작 주소를 지정 하는에 대 한 포인터입니다 `ICorDebugFrame` .  
  
 `pEnd`  
 제한이 `CORDB_ADDRESS` 이 개체가 나타내는 스택 프레임의 끝 주소를 지정 하는에 대 한 포인터입니다 `ICorDebugFrame` .  
  
## <a name="remarks"></a>설명  

 스택의 주소 범위는 여러 디버깅 엔진에서 수집 된 인터리브 스택 추적을 piecing 하는 데 유용 합니다. 숫자 범위는 스택 프레임의 내용에 대 한 정보를 제공 하지 않습니다. 스택 프레임 위치를 비교 하는 경우에만 의미가 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
