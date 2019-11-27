---
title: IBindingDisplay::InitializeForProcess 메서드
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: bb796a12868cc3e44394ab493f7838dc48ab4dc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448489"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess 메서드
[IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pid`  
 진행 프로세스 식별자입니다.  
  
## <a name="remarks"></a>주의  
 디버거는 만든 시간에 `InitializeForProcess` 메서드를 호출 하 여 바인딩 표시를 초기화 합니다. `InitializeForProcess` `IBindingDisplay`에서 다른 메서드를 호출 하기 전에 생성 시 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** BindingDisplay. h  
  
 **라이브러리:** BindingDisplay .idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IBindingDisplay 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
