---
description: '자세히 알아보기: ICLRReferenceAssemblyEnum:: Get 메서드'
title: ICLRReferenceAssemblyEnum::Get 메서드
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
ms.openlocfilehash: ea4e71631a9ebb381f721b78f17507603891a032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637302"
---
# <a name="iclrreferenceassemblyenumget-method"></a>ICLRReferenceAssemblyEnum::Get 메서드

제공 된 인덱스에서 어셈블리 id를 가져옵니다.  
  
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
 [in, out] 버퍼의 크기 `pwzBuffer` 입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Get` 성공적으로 반환 되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer`가 너무 작습니다.|  
|ERROR_NO_MORE_ITEMS|열거형에 항목이 더 이상 포함 되어 있지 않습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `Get` 는 일반적으로 두 번 호출 됩니다. 첫 번째 호출은에 대해 null 값을 제공 하 `pwzBuffer` 고 `pcchBufferSize` 에 적절 한 크기로 설정 합니다 `pwzBuffer` . 두 번째 호출은 적절 한 크기 `pwzBuffer` 를 제공 하 고 완료 시 정식 어셈블리 id 데이터를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum 인터페이스](iclrreferenceassemblyenum-interface.md)
