---
title: IMetaDataEmit::SetCustomAttributeValue 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: 25b7f478ae0bd05b82fa960561fb8534efe2b4db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175670"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a>IMetaDataEmit::SetCustomAttributeValue 메서드
[IMetaDataEmit::DefineCustomAttribute에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)대한 사전 호출에서 정의한 사용자 지정 특성의 값을 설정하거나 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pcv`  
 【인】 대상 사용자 지정 특성의 토큰입니다.  
  
 `pCustomAttribute`  
 【인】 사용자 지정 특성을 포함하는 배열에 대한 포인터입니다.  
  
 `cbCustomAttribute`  
 【인】 사용자 지정 특성의 크기(바이트)입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
