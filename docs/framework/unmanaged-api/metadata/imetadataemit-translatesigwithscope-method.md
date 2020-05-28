---
title: IMetaDataEmit::TranslateSigWithScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003986"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope 메서드
어셈블리를 현재 범위로 가져오고 병합 된 범위에 대 한 새 메타 데이터 서명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAssemImport`  
 진행 시그니처가 정의 된 가져오기 어셈블리에 대 한 인터페이스입니다.  
  
 `pbHashValue`  
 진행 어셈블리에 대 한 해시 blob입니다.  
  
 `cbHashValue`  
 진행 의 바이트 수 `pbHashValue` 입니다.  
  
 `import`  
 진행 메타 데이터 가져오기 범위에 대 한 인터페이스입니다.  
  
 `pbSigBlob`  
 진행 가져올 서명입니다.  
  
 `cbSigBlob`  
 진행 의 크기 (바이트)입니다 `pbSigBlob` .  
  
 `pAssemEmit`  
 진행 내보내기 어셈블리에 대 한 인터페이스입니다.  
  
 `emit`  
 진행 내보내기 메타 데이터 범위에 대 한 인터페이스입니다.  
  
 `pvTranslatedSig`  
 제한이 번역 된 서명 blob을 저장할 버퍼입니다.  
  
 `cbTranslatedSigMax`  
 진행 의 용량 (바이트)입니다 `pvTranslatedSig` .  
  
 `pcbTranslatedSig`  
 제한이 번역 된 시그니처의 실제 바이트 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
