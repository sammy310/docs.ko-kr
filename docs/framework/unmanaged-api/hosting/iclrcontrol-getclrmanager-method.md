---
description: '자세히 알아보기: ICLRControl:: GetCLRManager 메서드'
title: ICLRControl::GetCLRManager 메서드
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: fc24cbdfd4bebfff5c2f8d73a9cd6961a8c94e94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716720"
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager 메서드

호스트가 CLR (공용 언어 런타임)을 구성 하는 데 사용할 수 있는 관리자 형식의 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `riid`  
 진행 `IID` 반환할 관리자 형식의입니다. `IID`지원 되는 값은 다음과 같습니다.  
  
- IID_ICLRDebugManager:를 `ppObject` [ICLRDebugManager](iclrdebugmanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLRErrorReportingManager:를 `ppObject` [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLRGCManager:를 `ppObject` [ICLRGCManager](iclrgcmanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLRHostProtectionManager:를 `ppObject` [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLROnEventManager:를 `ppObject` [ICLROnEventManager](iclroneventmanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLRPolicyManager:를 `ppObject` [ICLRPolicyManager](iclrpolicymanager-interface.md)형식으로 지정 합니다.  
  
- IID_ICLRTaskManager:를 `ppObject` [ICLRTaskManager](iclrtaskmanager-interface.md)형식으로 지정 합니다.  
  
 `ppObject`  
 제한이 요청 된 관리자에 대 한 인터페이스 포인터 이거나, 잘못 된 관리자 형식이 요청 된 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_NOINTERFACE|인터페이스 유형이 지원 되지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
