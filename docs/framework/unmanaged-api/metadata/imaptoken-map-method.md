---
title: IMapToken::Map 메서드
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176073"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map 메서드
메타데이터 서명을 사용하여 어셈블리 간의 관계를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkImp`  
 【인】 가져온 코드 개체를 나타내는 메타데이터 토큰입니다.  
  
 `tkEmit`  
 【인】 내보낸 코드 개체를 나타내는 메타데이터 토큰입니다.  
  
## <a name="remarks"></a>설명  
 병합 중에 토큰 다시 맵이 발생하면 원래 토큰은 가져온(원본) 메타데이터 범위에서 범위가 지정되고 새 토큰은 내보낸(대상) 메타데이터 범위에서 범위가 지정됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMapToken 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
