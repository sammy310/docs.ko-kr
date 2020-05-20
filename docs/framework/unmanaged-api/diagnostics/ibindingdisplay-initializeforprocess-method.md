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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442152"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess 메서드
[IBindingDisplay](ibindingdisplay-interface.md) 개체를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pid`  
 진행 프로세스 식별자입니다.  
  
## <a name="remarks"></a>설명  
 디버거는 `InitializeForProcess` 만들 때 메서드를 호출 하 여 바인딩 디스플레이를 초기화 합니다. `InitializeForProcess`생성 시에는의 다른 메서드가 호출 되기 전에를 호출 해야 합니다 `IBindingDisplay` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** BindingDisplay. h  
  
 **라이브러리:** BindingDisplay .idl  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IBindingDisplay 인터페이스](ibindingdisplay-interface.md)
