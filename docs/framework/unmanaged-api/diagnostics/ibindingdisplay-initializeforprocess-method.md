---
description: '자세히 알아보기: IBindingDisplay:: InitializeForProcess 메서드'
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
ms.openlocfilehash: cf7f0f4d057659089bd7da173e5fac98a7c00dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800411"
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

 디버거는 `InitializeForProcess` 만들 때 메서드를 호출 하 여 바인딩 디스플레이를 초기화 합니다. `InitializeForProcess` 생성 시에는의 다른 메서드가 호출 되기 전에를 호출 해야 합니다 `IBindingDisplay` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** BindingDisplay. h  
  
 **라이브러리:** BindingDisplay .idl  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IBindingDisplay 인터페이스](ibindingdisplay-interface.md)
