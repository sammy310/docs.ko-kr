---
title: LockClrVersion 함수
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008497"
---
# <a name="lockclrversion-function"></a>LockClrVersion 함수
호스트에서 CLR을 명시적으로 초기화 하기 전에 프로세스 내에서 사용할 CLR (공용 언어 런타임) 버전을 확인할 수 있습니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hostCallback`  
 진행 초기화 될 때 CLR에 의해 호출 되는 함수입니다.  
  
 `pBeginHostSetup`  
 진행 초기화가 시작 됨을 CLR에 알리기 위해 호스트에서 호출 하는 함수입니다.  
  
 `pEndHostSetup`  
 진행 초기화가 완료 되었음을 CLR에 알리기 위해 호스트에서 호출 하는 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|하나 이상의 인수가 null입니다.|  
  
## <a name="remarks"></a>설명  
 CLR을 초기화 하기 전에 호스트에서를 호출 합니다 `LockClrVersion` . `LockClrVersion`는 세 개의 매개 변수를 사용 합니다 .이 매개 변수는 모두 [Flockclrversioncallback](flockclrversioncallback-function-pointer.md)형식의 콜백입니다. 이 형식은 다음과 같이 정의 됩니다.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 다음 단계는 런타임을 초기화할 때 발생 합니다.  
  
1. 호스트는 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 다른 런타임 초기화 함수 중 하나를 호출 합니다. 또는 호스트에서 COM 개체 활성화를 사용 하 여 런타임을 초기화할 수 있습니다.  
  
2. 런타임에서는 매개 변수로 지정 된 함수를 호출 합니다 `hostCallback` .  
  
3. 에서 지정한 함수는 `hostCallback` 다음과 같은 일련의 호출을 수행 합니다.  
  
    - 매개 변수에서 지정 하는 함수 `pBeginHostSetup` 입니다.  
  
    - `CorBindToRuntimeEx`(또는 다른 런타임 초기화 함수).  
  
    - [ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).  
  
    - 매개 변수에서 지정 하는 함수 `pEndHostSetup` 입니다.  
  
 에서로의 모든 `pBeginHostSetup` 호출은 `pEndHostSetup` 동일한 논리 스택을 사용 하는 단일 스레드나 파이버에서 발생 해야 합니다. 이 스레드는가 호출 되는 스레드와 다를 수 있습니다 `hostCallback` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
