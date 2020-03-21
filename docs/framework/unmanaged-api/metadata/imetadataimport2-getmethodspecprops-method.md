---
title: IMetaDataImport2::GetMethodSpecProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 0bfbfec930c193ea05a01bd5bd9f46d2ec6714b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175293"
---
# <a name="imetadataimport2getmethodspecprops-method"></a>IMetaDataImport2::GetMethodSpecProps 메서드
지정된 MethodSpec 토큰에서 참조하는 메서드의 메타데이터 서명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `mi`  
 【인】 메서드의 인스턴스화를 나타내는 MethodSpec 토큰입니다.  
  
 `tkParent`  
 【아웃】 메서드 정의를 나타내는 MethodDef 또는 MethodRef 토큰에 대한 포인터입니다.  
  
 `ppvSigBlob`  
 【아웃】 메서드의 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `pcbSigBlob`  
 【아웃】 의 크기(바이트)입니다. `ppvSigBlob`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
