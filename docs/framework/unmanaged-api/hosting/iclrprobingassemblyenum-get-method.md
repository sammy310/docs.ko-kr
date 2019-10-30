---
title: ICLRProbingAssemblyEnum::Get 메서드
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: 2ff1f9428a92d091a51a4cca12d69d98da0ecba2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120527"
---
# <a name="iclrprobingassemblyenumget-method"></a>ICLRProbingAssemblyEnum::Get 메서드
지정 된 인덱스에 있는 어셈블리 id를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwIndex`  
 진행 반환할 어셈블리 id의 인덱스 (0부터 시작)입니다.  
  
 `pwzBuffer`  
 제한이 어셈블리 id 데이터를 포함 하는 버퍼입니다.  
  
 `pcchBufferSize`  
 [in, out] `pwzBuffer` 버퍼의 크기입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Get` 성공적으로 반환 되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` 너무 작습니다.|  
|ERROR_NO_MORE_ITEMS|열거형에 항목이 더 이상 포함 되어 있지 않습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 모든 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 인덱스 0의 id는 프로세서 아키텍처와 관련 된 id입니다. 인덱스 1의 id는 MSIL (Microsoft 중간 언어)에 대 한 아키텍처 중립적인 어셈블리입니다. 인덱스 2의 id에 아키텍처 정보가 없습니다.  
  
 `Get`은 일반적으로 두 번 호출 됩니다. 첫 번째 호출은 `pwzBuffer`에 null 값을 제공 하 고 `pcchBufferSize`을 `pwzBuffer`에 적합 한 크기로 설정 합니다. 두 번째 호출에서는 적절 한 크기의 `pwzBuffer`을 제공 하 고 완료 시 정식 어셈블리 id 데이터를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRProbingAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
