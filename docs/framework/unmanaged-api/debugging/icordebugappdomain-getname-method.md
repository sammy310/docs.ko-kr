---
description: '자세히 알아보기: ICorDebugAppDomain:: GetName 메서드'
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
ms.openlocfilehash: 56995f544e1576534e35b899a659ed409972305f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772434"
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
 [in] `szName` 배열의 크기입니다. 이 메서드를 쿼리 모드로 전환 하려면이 값을 0으로 설정 합니다.  
  
 `pcchName`  
 제한이 에서 실제로 반환 된 이름의 크기나 문자 수에 대 한 포인터입니다 `szName` . 쿼리 모드에서이 값은 호출자가 이름에 할당할 버퍼의 크기를 알 수 있도록 합니다.  
  
 `szName`  
 제한이 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  

 디버거는 메서드를 `GetName` 한 번 호출 하 여 이름에 필요한 버퍼 크기를 가져옵니다. 디버거는 버퍼를 할당 한 다음 메서드를 두 번 호출 하 여 버퍼를 채웁니다. 이름 크기를 가져오기 위한 첫 번째 호출은 *쿼리 모드* 라고 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
