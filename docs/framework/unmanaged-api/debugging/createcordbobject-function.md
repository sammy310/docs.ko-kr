---
title: CreateCordbObject 함수
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179225"
---
# <a name="createcordbobject-function"></a>CreateCordbObject 함수
원격 프로세스에서 관리되는 디버깅 세션을 인스턴스화하는 기능을 제공하는 디버거[인터페이스(ICorDebug)를](icordebug-interface.md)만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `iDebuggerVersion`  
 [in] 대상 프로세스의 디버거 버전입니다. 원격 디버깅의 경우 이 매개 변수는 CorDebugVersion_2_0이어야 합니다.  
  
 `ppCordb`  
 【아웃】 [ICorDebug](icordebug-interface.md) 인터페이스에 캐스팅되고 반환되는 개체에 대한 포인터를 포인터로 합니다.  
  
## <a name="return-value"></a>Return Value  
 S_OK  
 프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.  
  
 E_INVALIDARG  
 `ppCordb`가 null이거나 `iDebuggerVersion`이 CorDebugVersion_2_0이 아닙니다.  
  
 E_OUTOFMEMORY  
 `ppCordb`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="remarks"></a>설명  
 반환되는 [ICorDebug](icordebug-interface.md) `ppCordb` 인터페이스는 관리되는 모든 디버깅 서비스에 대한 최상위 디버깅 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코어클러원격디버깅인터페이스.h  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET 프레임워크 버전:** 3.5 SP1
