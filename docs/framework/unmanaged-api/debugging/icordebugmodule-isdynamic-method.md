---
description: '자세히 알아보기: ICorDebugModule:: IsDynamic 메서드'
title: ICorDebugModule::IsDynamic 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 06ecb7aaffbe73da29bbdbba9446839db54c58c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660104"
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic 메서드

이 모듈이 동적 모듈 인지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pDynamic`  
 [out] `true` 이 모듈이 동적 이면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 모듈이 로드 된 후에도 동적 모듈에서 새 클래스를 추가 하 고 기존 클래스를 삭제할 수 있습니다. [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백은 클래스가 추가 되거나 삭제 된 경우 디버거에 알립니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
