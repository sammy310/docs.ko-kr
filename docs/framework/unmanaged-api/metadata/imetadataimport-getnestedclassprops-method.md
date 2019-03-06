---
title: IMetaDataImport::GetNestedClassProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6462496a8804d9aa5304107a6c01122b745038fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500254"
---
# <a name="imetadataimportgetnestedclassprops-method"></a>IMetaDataImport::GetNestedClassProps 메서드
부모에 대 한 TypeDef 토큰을 가져옵니다 <xref:System.Type> 중첩 형식을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tdNestedClass`  
 [in] 나타내는 하는 TypeDef 토큰을 <xref:System.Type> 부모 클래스를 반환 하도록 토큰에 대 한 합니다.  
  
 `ptdEnclosingClass`  
 [out] 에 대 한 TypeDef 토큰에 대 한 포인터를 <xref:System.Type> 는 `tdNestedClass` 에 중첩 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
