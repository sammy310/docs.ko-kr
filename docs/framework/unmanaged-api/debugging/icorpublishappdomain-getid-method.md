---
description: '자세히 알아보기: ICorPublishAppDomain:: GetID 메서드'
title: ICorPublishAppDomain::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: b3de19c053b5fcce2af5e0036ee6174b01700aac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721842"
---
# <a name="icorpublishappdomaingetid-method"></a>ICorPublishAppDomain::GetID 메서드

이 [ICorPublishAppDomain](icorpublishappdomain-interface.md)에 대 한 고유 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `puId`  
 제한이 응용 프로그램 도메인의 식별자에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 식별자는 포함 하는 프로세스의 범위 에서만 고유 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorPublishAppDomain 인터페이스](icorpublishappdomain-interface.md)
