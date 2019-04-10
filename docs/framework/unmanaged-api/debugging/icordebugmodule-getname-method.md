---
title: ICorDebugModule::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39467c067e50f2d553b35a41b0f783e0fc82156
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176646"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName 메서드
모듈의 파일 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchname`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 [in] 반환 된 이름의 길이에 대 한 포인터입니다.  
  
 `szName`  
 [out] 반환 된 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 `GetName` 모듈의 파일 이름에는 디스크의 이름과 일치 하는 경우 메서드는 S_OK HRESULT를 반환 합니다. `GetName` 이름이 동적 또는 메모리 내 모듈의 경우와 같이 작성 된 경우는 S_FALSE HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
