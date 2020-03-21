---
title: IMetaDataImport::GetFieldProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177243"
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps 메서드
지정한 FieldDef 토큰이 참조하는 필드와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mb`  
 【인】 관련 메타데이터를 가져오는 필드를 나타내는 FieldDef 토큰입니다.  
  
 `pClass`  
 【아웃】 필드에 속한 클래스의 형식을 나타내는 TypeDef 토큰에 대한 포인터입니다.  
  
 `szField`  
 【아웃】 필드의 이름입니다.  
  
 `cchField`  
 【인】 *szField에*대 한 버퍼의 넓은 문자의 크기입니다.  
  
 `pchField`  
 【아웃】 반환된 버퍼의 실제 크기입니다.  
  
 `pdwAttr`  
 【아웃】 필드의 메타데이터와 연결된 플래그입니다.  
  
 `ppvSigBlob`  
 【인】 필드를 설명하는 이진 메타데이터 값에 대한 포인터입니다.  
  
 `pcbSigBlob`  
 【아웃】 의 바이트 크기입니다. `ppvSigBlob`  
  
 `pdwCPlusTypeFlag`  
 【아웃】 필드의 값 형식을 지정하는 플래그입니다.  
  
 `ppValue`  
 【아웃】 필드에 대한 상수 값입니다.  
  
 `pcchValue`  
 【아웃】 문자열이 없는 경우 `ppValue`의 chars 또는 0의 크기입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
