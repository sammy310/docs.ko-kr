---
title: ICorDebugAppDomain::IsAttached 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 898398b731832e698a43eb270bbdc63bb3867bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702175"
---
# <a name="icordebugappdomainisattached-method"></a>ICorDebugAppDomain::IsAttached 메서드

디버거가 응용 프로그램 도메인에 연결 되어 있는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pbAttached`  
 [out] `true` 디버거가 응용 프로그램 도메인에 연결 되어 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 디버거가 응용 프로그램 도메인에 연결 될 때까지 ICorDebugController 메서드를 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
