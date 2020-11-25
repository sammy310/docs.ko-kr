---
title: ICLRRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 50e777bde34eb0122ca537da4b73a5e507ce7a7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728799"
---
# <a name="iclrruntimehoststop-method"></a>ICLRRuntimeHost::Stop 메서드

CLR (공용 언어 런타임)에서 코드 실행을 중지 합니다.  
  
> [!IMPORTANT]
> 이 메서드는 호스트에 대 한 리소스를 해제 하거나 응용 프로그램 도메인을 언로드하거나 스레드를 소멸 시 키 지 않습니다. 이러한 리소스를 해제 하려면 프로세스를 종료 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Stop` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
