---
description: '자세히 알아보기: ICorDebugAppDomain:: GetObject 메서드'
title: ICorDebugAppDomain::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: 59389e2a4ca72f8dcdd7117213e968440d30aaa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754214"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject 메서드

CLR (공용 언어 런타임) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppObject`  
 제한이 CLR 응용 프로그램 도메인을 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 <xref:System.AppDomain?displayProperty=nameWithType>이 응용 프로그램 도메인에 대 한 관리 되는 개체가 생성 되지 않은 경우이 메서드는 `S_FALSE` 을 반환 하 고 `NULL` 에 위치 `*ppObject` 합니다.  
  
## <a name="remarks"></a>설명  

 프로세스의 각 응용 프로그램 도메인은이를 나타내는 런타임에 관리 되는 개체를 가질 수 있습니다 <xref:System.AppDomain?displayProperty=nameWithType> . 이 함수는이 관리 되는 개체에 해당 하는 ICorDebugValue 인터페이스 개체를 가져옵니다 <xref:System.AppDomain?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
