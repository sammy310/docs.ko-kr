---
title: ICorDebugAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179084"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName 메서드
응용 프로그램 도메인의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다. 이 값을 0으로 설정하여 이 메서드를 쿼리 모드에 넣습니다.  
  
 `pcchName`  
 【아웃】 이름 크기 또는 실제로 반환된 문자 수에 `szName`대한 포인터입니다. 쿼리 모드에서 이 값을 사용하면 호출자가 이름에 할당할 버퍼의 큰 정도를 알 수 있습니다.  
  
 `szName`  
 【아웃】 응용 프로그램 도메인의 이름을 저장하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 디버거는 `GetName` 이름에 필요한 버퍼의 크기를 얻기 위해 메서드를 한 번 호출합니다. 디버거는 버퍼를 할당한 다음 메서드를 두 번째로 호출하여 버퍼를 채웁니다. 이름의 크기를 얻기 위해 첫 번째 호출을 *쿼리 모드라고*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
