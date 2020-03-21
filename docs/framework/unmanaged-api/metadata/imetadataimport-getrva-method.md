---
title: IMetaDataImport::GetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177211"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA 메서드
상대 가상 주소(RVA)와 지정된 토큰으로 표시되는 메서드 또는 필드의 구현 플래그를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 【인】 RVA를 반환하는 코드 개체를 나타내는 MethodDef 또는 FieldDef 메타데이터 토큰입니다. 토큰이 FieldDef인 경우 필드는 전역 변수여야 합니다.  
  
 `pulCodeRVA`  
 【아웃】 토큰으로 표시되는 코드 개체의 상대가상 주소에 대한 포인터입니다.  
  
 `pdwImplFlags`  
 【아웃】 메서드에 대 한 구현 플래그에 대 한 포인터입니다. 이 값은 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형의 비트 마스크입니다. `pdwImplFlags` 값은 MethodDef 토큰인 경우에만 `tk` 유효합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
