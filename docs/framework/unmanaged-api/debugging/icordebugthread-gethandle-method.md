---
title: ICorDebugThread::GetHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994021"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle 메서드
이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phThreadHandle`  
 [out] 이 스레드의 활성 부분의 핸들 인는 HTHREAD 포인터입니다.  
  
## <a name="remarks"></a>설명  
 프로세스를 실행 하 고 스레드의 부분 마다 다를 수 핸들을 변경할 수 있습니다.  
  
 디버깅 API에서이 핸들을 소유 합니다. 디버거 사용 하기 전에 복제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
