---
description: '자세히 알아보기: ICorDebugFunction:: GetNativeCode 메서드'
title: ICorDebugFunction::GetNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 8938e11a5fdc3aa693faf04eec639941475d95ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692448"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode 메서드

이 ICorDebugFunction 인스턴스로 표시 되는 함수에 대 한 네이티브 코드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppCode`  
 제한이 이 함수에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터 이거나,이 함수가 JIT (just-in-time) 컴파일되지 않은 MSIL (Microsoft 중간 언어) 코드 인 경우 null입니다.  
  
## <a name="remarks"></a>설명  

 이 인스턴스가 나타내는 함수가 `ICorDebugFunction` 제네릭 형식의 경우와 같이 두 번 이상 JIT 컴파일된 경우 `GetNativeCode` 임의의 네이티브 코드 개체를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
