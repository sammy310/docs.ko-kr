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
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440483"
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
 [in] \(서명을 정의 됨) 가져오기 어셈블리에 대 한 인터페이스입니다.  
  
 `pbHashValue`  
 진행 어셈블리에 대 한 해시 blob입니다.  
  
 `cbHashValue`  
 진행 `pbHashValue`바이트 수입니다.  
  
 `import`  
 진행 메타 데이터 가져오기 범위에 대 한 인터페이스입니다.  
  
 `pbSigBlob`  
 진행 가져올 서명입니다.  
  
 `cbSigBlob`  
 진행 `pbSigBlob`의 크기 (바이트)입니다.  
  
 `pAssemEmit`  
 진행 내보내기 어셈블리에 대 한 인터페이스입니다.  
  
 `emit`  
 진행 내보내기 메타 데이터 범위에 대 한 인터페이스입니다.  
  
 `pvTranslatedSig`  
 제한이 번역 된 서명 blob을 저장할 버퍼입니다.  
  
 `cbTranslatedSigMax`  
 진행 `pvTranslatedSig`의 용량 (바이트)입니다.  
  
 `pcbTranslatedSig`  
 제한이 번역 된 시그니처의 실제 바이트 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
