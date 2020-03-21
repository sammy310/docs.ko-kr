---
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175605"
---
# <a name="imetadataemitsetparent-method"></a>IMetaDataEmit::SetParent 메서드
[IMetaDataEmit::DefineMemberRef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)대한 사전 호출에 의해 정의된 지정된 멤버가 [IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 사전 호출에 정의된 대로 지정된 형식의 멤버임을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mr`  
 【인】 새 `mdMemberRef` 부모를 받을 토큰입니다.  
  
 `tk`  
 【인】 새 `mdToken` 상위에 대한 것입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
