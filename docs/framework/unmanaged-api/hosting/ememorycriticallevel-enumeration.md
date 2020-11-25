---
title: EMemoryCriticalLevel 열거형
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 3b9ad4b40ce94420f2ab5fc25335c41dec15dc09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720557"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel 열거형

특정 메모리 할당이 요청 되었지만 충족 될 수 없는 경우 실패의 영향을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAppDomainCritical`|할당을 요청한 도메인에서 관리 코드를 실행 하는 데 할당이 중요 함을 나타냅니다. 메모리를 할당할 수 없는 경우에는 CLR에서 도메인을 계속 사용할 수 있음을 보장할 수 없습니다. 호스트는 할당을 충족 시킬 수 없는 경우 수행할 작업을 결정 합니다. CLR에 `AppDomain` 자동으로 중단 하거나 [ICLRPolicyManager](iclrpolicymanager-interface.md)에서 메서드를 호출 하 여 계속 실행 되도록 허용할 수 있습니다.|  
|`eProcessCritical`|프로세스에서 관리 코드를 실행 하는 데 할당이 중요 함을 나타냅니다. 이 값은 시작 하는 동안 및 종료자를 실행할 때 사용 됩니다. 메모리를 할당할 수 없는 경우 CLR은 프로세스에서 작동할 수 없습니다. 할당이 실패 하는 경우 CLR은 효과적으로 사용 하지 않도록 설정 됩니다. CLR에 대 한 모든 후속 호출은 HOST_E_CLRNOTAVAILABLE와 함께 실패 합니다.|  
|`eTaskCritical`|할당을 요청한 태스크를 실행 하는 데 할당이 중요 함을 나타냅니다. 메모리를 할당할 수 없는 경우 CLR에서 작업을 실행할 수 있음을 보장할 수 없습니다. 오류가 발생 하는 경우 CLR은 <xref:System.Threading.ThreadAbortException> 물리적 작업 시스템 스레드에서을 발생 시킵니다.|  
  
## <a name="remarks"></a>설명  

 [IHostMemoryManager](ihostmemorymanager-interface.md) 및 [IHostMAlloc](ihostmalloc-interface.md) 인터페이스에 정의 된 메모리 할당 메서드는이 형식의 매개 변수를 사용 합니다. 오류의 심각도에 따라 호스트는 할당 요청을 즉시 장애 조치 (failover) 하거나 만족할 때까지 기다릴지 여부를 결정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRMemoryNotificationCallback 인터페이스](iclrmemorynotificationcallback-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
