---
description: '자세히 알아보기: GetCLRIdentityManager 함수'
title: GetCLRIdentityManager 함수
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 483cf0499fa162da4c89e350198a5609f9f1bab6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785369"
---
# <a name="getclridentitymanager-function"></a>GetCLRIdentityManager 함수

CLR (공용 언어 런타임)에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `riid`  
 진행 `REFIID` 가져올 인터페이스를 지정 하는 (인터페이스 식별자)입니다. 이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 이어야 합니다.  
  
 `ppManager`  
 제한이 [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) 또는 [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 [GetRealProcAddress](getrealprocaddress-function.md) 함수를 호출 하 여 함수에 대 한 포인터를 가져옵니다 `GetCLRIdentityManager` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorWks.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
