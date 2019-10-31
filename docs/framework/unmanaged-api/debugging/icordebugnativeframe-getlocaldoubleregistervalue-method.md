---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: a45061b6a3105565fdbb36173731b3c3dfe5aa4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137292"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드
이 네이티브 프레임의 지정 된 두 레지스터에 저장 된 인수 또는 지역 변수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `highWordReg`  
 진행 값의 상위 단어가 포함 된 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.  
  
 `lowWordReg`  
 진행 값의 하위 단어를 포함 하는 레지스터를 지정 하는 `CorDebugRegister` 열거형의 값입니다.  
  
 `cbSigBlob`  
 진행 `pvSigBlob` 매개 변수에서 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수입니다.  
  
 `pvSigBlob`  
 진행 값 형식의 이진 메타 데이터 서명을 가리키는 `PCCOR_SIGNATURE` 값입니다.  
  
 `ppValue`  
 제한이 지정 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 네이티브 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 `GetLocalDoubleRegisterValue` 메서드를 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
