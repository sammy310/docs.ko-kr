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
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379745"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle 메서드
이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phThreadHandle`  
 제한이 이 스레드의 활성 부분에 대 한 핸들 인 HTHREAD에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 핸들은 프로세스가 실행 될 때 변경 될 수 있으며 스레드의 다른 부분에 대해 다를 수 있습니다.  
  
 이 핸들은 디버깅 API에서 소유 합니다. 디버거는 사용 하기 전에이를 복제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
