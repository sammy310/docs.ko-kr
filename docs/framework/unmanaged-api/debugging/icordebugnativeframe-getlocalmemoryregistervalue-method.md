---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137280"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryRegisterValue 메서드
이 네이티브 프레임에 대해 하위 단어 및 상위 단어가 지정 된 레지스터 및 메모리 위치에 각각 저장 되는 인수 또는 지역 변수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `highWordAddress`  
 진행 값의 상위 단어가 포함 된 메모리 위치를 지정 하는 `CORDB_ADDRESS` 값입니다.  
  
 `lowWordRegister`  
 진행 값의 하위 단어를 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.  
  
 `cbSigBlob`  
 진행 `pvSigBlob` 매개 변수에서 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수입니다.  
  
 `pvSigBlob`  
 진행 값 형식의 이진 메타 데이터 서명을 가리키는 `PCCOR_SIGNATURE` 값입니다.  
  
 `ppValue`  
 제한이 지정 된 레지스터 및 메모리 위치에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
