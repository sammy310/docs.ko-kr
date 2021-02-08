---
description: '자세히 알아보기: EClrOperation 열거형'
title: EClrOperation 열거형
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 9f75762a400955b5f36fb2a337f283e36a32658c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785564"
---
# <a name="eclroperation-enumeration"></a>EClrOperation 열거형

호스트에서 정책 작업을 적용할 수 있는 작업 집합을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|호스트는가 <xref:System.AppDomain> 정상이 아닌 (강제) 방식으로 언로드될 때 수행할 정책 작업을 지정할 수 있습니다.|  
|`OPR_AppDomainUnload`|호스트는가 언로드될 때 수행할 정책 작업을 지정할 수 있습니다 <xref:System.AppDomain> .|  
|`OPR_FinalizerRun`|호스트는 종료 자가 실행 될 때 수행할 정책 작업을 지정할 수 있습니다.|  
|`OPR_ProcessExit`|호스트는 프로세스가 종료 될 때 수행할 정책 동작을 지정할 수 있습니다.|  
|`OPR_ThreadAbort`|호스트는 스레드가 중단 될 때 수행할 정책 동작을 지정할 수 있습니다.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|호스트는 중요 한 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|호스트는 중요 하지 않은 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.|  
  
## <a name="remarks"></a>설명  

 CLR (공용 언어 런타임) 안정성 인프라는 중요 한 코드 영역에서 발생 하는 중단 및 리소스 할당 오류와 중요 하지 않은 코드 영역에서 발생 하는 오류를 구분 합니다. 이러한 구분은 호스트에서 코드에 오류가 발생 하는 위치에 따라 다른 정책을 설정할 수 있도록 설계 되었습니다.  
  
 *중요 한 코드 영역은* CLR에서 작업 중단 또는 리소스에 대 한 요청 완료 실패로 인해 현재 작업에만 영향을 줄 수 있음을 보장할 수 없는 공간입니다. 예를 들어 태스크가 잠금을 보유 하 고 있고 메모리 할당 요청을 수행할 때 실패를 나타내는 HRESULT를 수신 하는 경우에는의 안정성을 보장 하기 위해 해당 작업을 중단 하는 것 만으로는 충분 하지 않습니다 .에는 <xref:System.AppDomain> <xref:System.AppDomain> 동일한 잠금을 기다리는 다른 태스크가 포함 될 수 있기 때문입니다. 현재 작업을 중단 하면 다른 작업의 응답이 중지 될 수 있습니다. 이러한 경우, 호스트는 잠재적 불안정성이 아닌 전체를 언로드하는 기능이 필요 합니다 <xref:System.AppDomain> .  
  
 반면, *중요 하지 않은 코드 영역은* CLR에서 중단 또는 실패가 오류가 발생 한 작업에만 영향을 줄 수 있도록 보장 하는 영역입니다.  
  
 또한 CLR은 정상 및 정상 (강제) 중단을 구분 합니다. 일반적으로 정상 또는 정상 abort는 작업을 중단 하기 전에 예외 처리 루틴 및 종료자를 실행 하는 데 모든 노력을 하지만, 잘못 된 abort는 이러한 보장이 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrFailure 열거형](eclrfailure-enumeration.md)
- [EPolicyAction 열거형](epolicyaction-enumeration.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
- [IHostPolicyManager 인터페이스](ihostpolicymanager-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
