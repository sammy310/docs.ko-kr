---
description: '자세히 알아보기: ICorDebugProcess:: GetHandle 메서드'
title: ICorDebugProcess::GetHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: fbc92be53b30d3c70f85fea36e05c6a5514b0f03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722128"
---
# <a name="icordebugprocessgethandle-method"></a>ICorDebugProcess::GetHandle 메서드

프로세스에 대 한 핸들을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phProcessHandle`  
 제한이 프로세스에 대 한 핸들에 해당 하는에 대 한 포인터입니다 `HPROCESS` .  
  
## <a name="remarks"></a>설명  

 검색 된 핸들은 디버깅 인터페이스가 소유 합니다. 디버거는 사용 하기 전에 핸들을 복제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
