---
title: IHostIoCompletionManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 095872f8d4bd4f7d3351b8b3e3f8f8445b615cd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501540"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager 인터페이스
CLR (공용 언어 런타임)이 호스트에서 제공 하는 i/o 완료 포트와 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[Bind 메서드](ihostiocompletionmanager-bind-method.md)|I/o 완료 포트에 핸들을 바인딩합니다.|  
|[CloseIoCompletionPort 메서드](ihostiocompletionmanager-closeiocompletionport-method.md)|에 대 한 이전 호출을 통해 만든 포트를 닫습니다 `CreateIoCompletionPort` .|  
|[CreateIoCompletionPort 메서드](ihostiocompletionmanager-createiocompletionport-method.md)|호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.|  
|[GetAvailableThreads 메서드](ihostiocompletionmanager-getavailablethreads-method.md)|현재 요청을 처리 하 고 있지 않은 i/o 완료 스레드 수를 가져옵니다.|  
|[GetHostOverlappedSize 메서드](ihostiocompletionmanager-gethostoverlappedsize-method.md)|호스트가 i/o 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.|  
|[GetMaxThreads 메서드](ihostiocompletionmanager-getmaxthreads-method.md)|호스트가 i/o 요청을 처리 하기 위해 할당할 수 있는 최대 스레드 수를 가져옵니다.|  
|[GetMinThreads 메서드](ihostiocompletionmanager-getminthreads-method.md)|호스트가 서비스 i/o 요청에 제공 하는 최소 스레드 수를 가져옵니다.|  
|[InitializeHostOverlapped 메서드](ihostiocompletionmanager-initializehostoverlapped-method.md)|호스트에 i/o 요청에 대 한 사용자 지정 데이터를 초기화할 수 있는 기회를 제공 합니다.|  
|[SetCLRIoCompletionManager 메서드](ihostiocompletionmanager-setclriocompletionmanager-method.md)|호스트에 CLR에서 구현 하는 [Iclriocompletionmanager](iclriocompletionmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.|  
|[SetMaxThreads 메서드](ihostiocompletionmanager-setmaxthreads-method.md)|호스트에서 i/o 요청을 처리 하는 데 많은 스레드의 최대 수를 설정 합니다.|  
|[SetMinThreads 메서드](ihostiocompletionmanager-setminthreads-method.md)|호스트에서 i/o 완료에 대해 할당할 최소 스레드 수를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostIoCompletionManager``ICLRIoCompletionManager`는 CLR에서 구현 하는 인터페이스에 해당 합니다. CLR은의 메서드를 호출 `IHostIoCompletionManager` 하 여 호스트에서 제공 하는 포트에 핸들을 바인딩하고 호스트는의 메서드를 호출 하 여 `ICLRIoCompletionManager` i/o 요청 완료를 보고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 인터페이스](hosting-interfaces.md)
