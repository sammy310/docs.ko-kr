---
description: '자세한 정보: GetAppIdAuthority 함수'
title: GetAppIdAuthority 함수
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: a0c2a7b754c2b014b189f96fd3c27347571cc0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761072"
---
# <a name="getappidauthority-function"></a>GetAppIdAuthority 함수

응용 프로그램 id 및 참조에 대 한 키를 관리 하는 [Iappidauthority](iappidauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppIAppIdAuthority`  
 제한이 반환 된 `IAppIdAuthority` 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAppIdAuthority 인터페이스](iappidauthority-interface.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
