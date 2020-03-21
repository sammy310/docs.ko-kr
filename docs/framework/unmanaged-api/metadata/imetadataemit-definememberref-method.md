---
title: IMetaDataEmit::DefineMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175839"
---
# <a name="imetadataemitdefinememberref-method"></a>IMetaDataEmit::DefineMemberRef 메서드
현재 범위 외부의 모듈 멤버에 대한 참조를 정의하고 해당 참조 정의에 대한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkImport`  
 【인】 멤버가 전역이 아닌 경우 대상 멤버의 클래스 또는 인터페이스에 대한 토큰입니다. 멤버가 전역인 경우 `mdModuleRef` 해당 다른 파일에 대한 토큰입니다.  
  
 `szName`  
 【인】 대상 멤버의 이름입니다.  
  
 `pvSigBlob`  
 【인】 대상 멤버의 서명입니다.  
  
 `cbSigBlob`  
 【인】 의 바이트 `pvSigBlob`수입니다.  
  
 `pmr`  
 【아웃】 할당된 토큰입니다. `mdMemberRef`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
