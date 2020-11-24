---
title: IMetaDataEmit::SetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: d479416f5f1cb4042f9b3fc112e22b67e37d3f78
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672710"
---
# <a name="imetadataemitsetfieldmarshal-method"></a>IMetaDataEmit::SetFieldMarshal 메서드

지정 된 토큰이 참조 하는 필드, 메서드 반환 또는 메서드 매개 변수에 대 한 PInvoke 마샬링 정보를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 대상 데이터 항목에 대 한 토큰입니다. `mdFieldDef`또는 `mdParamDef` 토큰입니다.  
  
 `pvNativeType`  
 진행 관리 되지 않는 형식에 대 한 서명입니다.  
  
 `cbNativeType`  
 진행 의 바이트 수 `pvNativeType` 입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
