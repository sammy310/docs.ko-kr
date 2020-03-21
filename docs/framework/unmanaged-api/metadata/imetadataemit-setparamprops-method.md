---
title: IMetaDataEmit::SetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177499"
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps 메서드
[IMetaDataEmit::DefineParam에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)대한 사전 호출에 의해 정의된 메서드 매개 변수의 기능을 설정하거나 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pd`  
 【인】 대상 매개 변수에 대한 토큰입니다.  
  
 `szName`  
 【인】 유니코드의 매개 변수 이름입니다.  
  
 `dwParamFlags`  
 【인】 매개 변수의 플래그입니다.  
  
 `dwCPlusTypeFlag`  
 【인】 상수 값에 대한 ELEMENT_TYPE_*입니다.  
  
 `pValue`  
 【인】 매개 변수의 상수 값입니다.  
  
 `cchValue`  
 【인】 의 (유니코드) 문자의 `pValue`크기입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
