---
title: ICLRRuntimeInfo::IsLoadable 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 13b4e00cf002abca625dbdda010f7d8994360687
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762541"
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable 메서드
프로세스에 이미 로드 되어 있을 수 있는 다른 런타임을 고려 하 여이 인터페이스와 연결 된 런타임을 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbLoadable`  
 [out] `true` 이 런타임을 현재 프로세스로 로드할 수 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pbLoadable`가 null인 경우|  
  
## <a name="remarks"></a>설명  
 다른 런타임이 이미 프로세스에 로드 되어 있고이 인터페이스와 연결 된 런타임을 in-process side-by-side 실행에 대해 로드할 수 있는 경우는을 `pbLoadable` 반환 `true` 합니다. 두 런타임을 함께 실행할 수 없는 경우는를 `pbLoadable` 반환 `false` 합니다. 예를 들어 clr (공용 언어 런타임) 버전 4는 CLR 버전 2.0 또는 CLR 버전 1.1과 동일한 프로세스에서 함께 실행할 수 있습니다. 그러나 CLR 버전 1.1 및 CLR 버전 2.0는 side-by-side로 실행할 수 없습니다.  
  
 프로세스에 로드 된 런타임이 없으면이 메서드는 항상를 반환 `true` 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
