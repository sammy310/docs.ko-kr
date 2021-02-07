---
description: '자세히 알아보기: GetIdentityAuthority 함수'
title: GetIdentityAuthority 함수
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: 5126aa9b319af41f7ecd30845a9f74ba69016588
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760998"
---
# <a name="getidentityauthority-function"></a>GetIdentityAuthority 함수

코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppIIdentityAuthority`  
 제한이 반환 된 `IIdentityAuthority` 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IIdentityAuthority 인터페이스](iidentityauthority-interface.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
