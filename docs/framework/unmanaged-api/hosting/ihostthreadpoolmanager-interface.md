---
title: IHostThreadPoolManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: bac29b5950f1547c5c60ac716d40d2ef4b1a2cc2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842483"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager 인터페이스
CLR (공용 언어 런타임)이 스레드 풀을 구성 하 고 작업 항목을 스레드 풀에 대기 시킬 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|방법|Description|  
|------------|-----------------|  
|[GetAvailableThreads 메서드](ihostthreadpoolmanager-getavailablethreads-method.md)|현재 작업 항목을 처리 하 고 있지 않은 스레드 풀의 스레드 수를 가져옵니다.|  
|[GetMaxThreads 메서드](ihostthreadpoolmanager-getmaxthreads-method.md)|호스트가 스레드 풀에서 동시에 유지 관리 하는 최대 스레드 수를 가져옵니다.|  
|[GetMinThreads 메서드](ihostthreadpoolmanager-getminthreads-method.md)|호스트에서 요청을 미리 대비 하 여 유지 하는 유휴 스레드의 최소 수를 가져옵니다.|  
|[QueueUserWorkItem 메서드](ihostthreadpoolmanager-queueuserworkitem-method.md)|함수를 실행 하기 위해 큐에 대기 시키고 함수에서 사용할 데이터가 포함 된 개체를 제공 합니다.|  
|[SetMaxThreads 메서드](ihostthreadpoolmanager-setmaxthreads-method.md)|호스트가 스레드 풀에서 유지 관리할 수 있는 스레드의 최대 수를 설정 합니다.|  
|[SetMinThreads 메서드](ihostthreadpoolmanager-setminthreads-method.md)|호스트에서 요청을 예측 하 여 유지 해야 하는 최소 유휴 스레드 수를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 및 메서드에 대 한 호출에 지정 된 값을 사용 하 여 스레드 풀을 구성할 필요가 없습니다 `SetMaxThreads` `SetMinThreads` . 이 경우 호스트는 이러한 메서드에서 E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [호스팅 인터페이스](hosting-interfaces.md)
