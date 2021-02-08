---
description: 'ICorPublishProcess:: EnumAppDomains 메서드에 대해 자세히 알아보세요.'
title: ICorPublishProcess::EnumAppDomains 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: c7834b23967ab467c1589ee31929bf346b4b3b8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794613"
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains 메서드

이 [ICorPublishProcess](icorpublishprocess-interface.md)에서 참조 하는 프로세스의 응용 프로그램 도메인에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppEnum`  
 제한이 이 프로세스에서 응용 프로그램 도메인의 컬렉션을 반복할 수 있도록 하는 [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) 인스턴스의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 응용 프로그램 도메인 목록은 메서드가 호출 될 때 존재 하는 응용 프로그램 도메인의 스냅숏을 기반으로 합니다 `EnumAppDomains` . 이 메서드는 새 최신 목록을 만들기 위해 두 번 이상 호출 될 수 있습니다. 기존 목록은이 메서드에 대 한 후속 호출의 영향을 받지 않습니다.  
  
 프로세스가 종료 된 경우 `EnumAppDomains` 는 HRESULT 값 CORDBG_E_PROCESS_TERMINATED을 사용 하 여 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorPublishProcess 인터페이스](icorpublishprocess-interface.md)
