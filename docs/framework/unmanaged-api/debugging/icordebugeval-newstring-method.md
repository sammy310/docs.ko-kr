---
description: '자세히 알아보기: ICorDebugEval:: NewString 메서드'
title: ICorDebugEval::NewString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 21eb49900d84cb1ad1f68a701998a4a778c3ef17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693839"
---
# <a name="icordebugevalnewstring-method"></a>ICorDebugEval::NewString 메서드

지정 된 내용을 사용 하 여 새 문자열 인스턴스를 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `string`  
 진행 문자열의 내용에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
