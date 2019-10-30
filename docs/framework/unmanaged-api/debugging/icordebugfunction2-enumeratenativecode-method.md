---
title: ICorDebugFunction2::EnumerateNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
ms.openlocfilehash: d5b24ee02a682b38dcf0cb3449f0dff197e91bf9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137825"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>ICorDebugFunction2::EnumerateNativeCode 메서드
이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문을 포함 하는 ICorDebugCodeEnum 개체에 대 한 인터페이스 포인터를 가져옵니다.  
  
> [!NOTE]
> `EnumerateNativeCode`은 .NET Framework의 현재 버전에서 구현 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorDebug.idl, CorDebug.h
