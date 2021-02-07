---
description: '자세히 알아보기: ICLRErrorReportingManager:: BeginCustomDump 메서드'
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
ms.openlocfilehash: 3f8498068d50ffc6ea00cf4f08f969c92f010d6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689484"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump 메서드

오류 보고에 대 한 사용자 지정 힙 덤프의 구성을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwFlavor`  
 진행 사용자 지정 힙 덤프를 빌드할 힙 덤프의 종류를 나타내는 [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) 값입니다.  
  
 `dwNumItems`  
 진행 `items` 배열의 길이입니다. `dwFlavor`가 DUMP_FLAVOR_Mini 되지 않은 경우는 `dwNumItems` 0 이어야 합니다.  
  
 `items`  
 진행 미니 덤프에 추가할 항목을 지정 하는 [Custom덤프 항목](customdumpitem-structure.md) 인스턴스의 배열입니다. `dwFlavor`가 DUMP_FLAVOR_Mini 되지 않은 경우는 `items` null 이어야 합니다.  
  
 `dwReserved`  
 진행 나중에 사용 하도록 예약 되어 있습니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `BeginCustomDump`메서드는 사용자 지정 힙 덤프 구성을 설정 합니다. [Endcustomdump](iclrerrorreportingmanager-endcustomdump-method.md) 메서드는 사용자 지정 힙 덤프 구성을 지우고 연결 된 상태를 해제 합니다. 사용자 지정 힙 덤프가 완료 된 후이 메서드를 호출 해야 합니다.  
  
> [!IMPORTANT]
> 호출 하지 못하면 `EndCustomDump` 메모리 누수가 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CustomDumpItem 구조체](customdumpitem-structure.md)
- [ECustomDumpFlavor 열거형](ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)
