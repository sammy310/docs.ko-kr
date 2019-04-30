---
title: ICLRErrorReportingManager::BeginCustomDump 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cb6cd8d31e01ea2f1749a6cb4d17173679f0c06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984791"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump 메서드
오류 보고에 대 한 사용자 지정 힙 덤프 구성을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwFlavor`  
 [in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) 사용자 지정 힙 덤프를 작성 하는 힙 덤프의 종류를 나타내는 값입니다.  
  
 `dwNumItems`  
 [in] 길이 `items` 배열입니다. 하는 경우 `dwFlavor` DUMP_FLAVOR_Mini, 아닙니다 `dwNumItems` 0 이어야 합니다.  
  
 `items`  
 [in] 배열을 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 경우 미니 덤프에 추가할 항목을 지정 합니다. 하는 경우 `dwFlavor` DUMP_FLAVOR_Mini, 아닙니다 `items` null 이어야 합니다.  
  
 `dwReserved`  
 [in] 사용 하도록 예약 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `BeginCustomDump` 메서드는 사용자 지정 힙 덤프 구성을 설정 합니다. 합니다 [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) 메서드를 사용자 지정 힙 덤프 구성 지워지고 연결 된 모든 상태를 해제 합니다. 사용자 지정 힙 덤프에서 완료 된 후 호출 되어야 합니다.  
  
> [!IMPORTANT]
>  호출 하지 못하면 `EndCustomDump` 메모리 누수를 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [CustomDumpItem 구조체](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [ECustomDumpFlavor 열거형](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
