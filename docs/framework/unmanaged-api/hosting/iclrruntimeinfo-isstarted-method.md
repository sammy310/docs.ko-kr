---
description: '자세히 알아보기: ICLRRuntimeInfo:: IsStarted 메서드'
title: ICLRRuntimeInfo::IsStarted 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 22059ecbded9eae9659cdaae8b9b92f2d7df0650
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753850"
---
# <a name="iclrruntimeinfoisstarted-method"></a>ICLRRuntimeInfo::IsStarted 메서드

런타임이 시작 되었는지 여부를 나타냅니다. 즉, [ICLRRuntimeHost:: Start 메서드가](iclrruntimehost-start-method.md) 호출 되었고 성공 했는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pbStarted`  
 [out] `true` 이 런타임이 시작 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
 `pdwStartupFlags`  
 제한이 런타임을 시작 하는 데 사용 된 플래그를 반환 합니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_NOTIMPL|CLR (공용 언어 런타임) 버전은 .NET Framework 4의 CLR 버전 보다 이전 버전입니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 .NET Framework 4의 CLR 버전 이전 CLR 버전에서는 작동 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
