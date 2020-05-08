---
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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895218"
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
 이 응용 프로그램 <xref:System.AppDomain?displayProperty=nameWithType> 도메인에 대 한 관리 되는 개체가 생성 되지 않은 경우 `S_FALSE` 이 메서드 `NULL` 는 `*ppObject`을 반환 하 고에 위치 합니다.  
  
## <a name="remarks"></a>설명  
 프로세스의 각 응용 프로그램 도메인은이를 나타내는 <xref:System.AppDomain?displayProperty=nameWithType> 런타임에 관리 되는 개체를 가질 수 있습니다. 이 함수는이 관리 되 <xref:System.AppDomain?displayProperty=nameWithType> 는 개체에 해당 하는 ICorDebugValue 인터페이스 개체를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
