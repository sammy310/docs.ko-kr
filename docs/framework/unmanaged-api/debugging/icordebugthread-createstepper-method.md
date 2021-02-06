---
description: '자세히 알아보기: ICorDebugThread:: CreateStepper 메서드'
title: ICorDebugThread::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: 378ce28281f4f284c36194f993a53598a9de3854
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659363"
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper 메서드

이 ICorDebugThread의 활성 프레임을 단계별로 실행할 수 있도록 하는 ICorDebugStepper 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppStepper`  
 제한이 `ICorDebugStepper` 이 스레드의 활성 프레임을 단계별로 실행할 수 있도록 하는 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 활성 프레임은 비관리 코드 일 수 있습니다.  
  
 `ICorDebugStepper`실제 단계를 수행 하려면 인터페이스를 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
