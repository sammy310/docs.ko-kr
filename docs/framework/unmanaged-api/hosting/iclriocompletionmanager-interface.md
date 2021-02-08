---
description: '자세한 정보: Iclrio이상 관리자 인터페이스'
title: ICLRIoCompletionManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b2d18f9c9900d448f0c6517520c303eb4258f8d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789891"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager 인터페이스

호스트가 지정 된 i/o 요청 상태를 CLR (공용 언어 런타임)에 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[OnComplete 메서드](iclriocompletionmanager-oncomplete-method.md)|[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR에 알립니다.|  
  
## <a name="remarks"></a>설명  

 호스트는 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) 인터페이스를 사용 하 여 i/o 완료 추상화를 구현 합니다. CLR은이 인터페이스를 통해 i/o 요청을 만들고, 호스트는 인터페이스를 사용 하 여 이러한 요청의 결과를 런타임에 알립니다 `ICLRIoCompletionManager` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostIoCompletionManager 인터페이스](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
