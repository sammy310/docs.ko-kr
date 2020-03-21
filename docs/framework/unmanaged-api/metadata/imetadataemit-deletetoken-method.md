---
title: IMetaDataEmit::DeleteToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: 3b8aed6522b1c7eb2d8916f71d8a66b367623765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177601"
---
# <a name="imetadataemitdeletetoken-method"></a>IMetaDataEmit::DeleteToken 메서드
현재 메타데이터 범위에서 지정된 토큰을 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkObj`  
 【인】 삭제할 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
