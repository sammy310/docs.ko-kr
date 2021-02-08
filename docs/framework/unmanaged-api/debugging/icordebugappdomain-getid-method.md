---
description: '자세히 알아보기: ICorDebugAppDomain:: GetId 메서드'
title: ICorDebugAppDomain::GetId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
ms.openlocfilehash: ea660aa08e93e4ce2d97f1e7ae05b261db91118f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772469"
---
# <a name="icordebugappdomaingetid-method"></a>ICorDebugAppDomain::GetId 메서드

응용 프로그램 도메인의 고유 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pId`  
 제한이 응용 프로그램 도메인의 고유 식별자입니다.  
  
## <a name="remarks"></a>설명  

 응용 프로그램 도메인에 대 한 식별자는 포함 하는 프로세스 내에서 고유 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
