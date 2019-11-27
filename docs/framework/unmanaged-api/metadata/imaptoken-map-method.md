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
ms.openlocfilehash: fd362beb9f8fd7a1f2076eb6490a96c0358520e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432142"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map 메서드
메타 데이터 시그니처를 사용 하 여 어셈블리 간의 관계를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkImp`  
 진행 가져온 코드 개체를 나타내는 메타 데이터 토큰입니다.  
  
 `tkEmit`  
 진행 내보낸 코드 개체를 나타내는 메타 데이터 토큰입니다.  
  
## <a name="remarks"></a>주의  
 병합 하는 동안 토큰 다시 맵이 발생 하면 원래 토큰은 가져온 (원본) 메타 데이터 범위에서 범위가 지정 되 고 새 토큰은 내보낸 (대상) 메타 데이터 범위에서 범위가 지정 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMapToken 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
