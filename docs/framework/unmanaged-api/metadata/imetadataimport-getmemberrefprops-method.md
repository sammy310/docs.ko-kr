---
title: IMetaDataImport::GetMemberRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175371"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps 메서드
지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mr`  
 【인】 멤버 참조 토큰에 대 한 관련 된 메타 데이터를 반환 합니다.  
  
 `ptk`  
 【아웃】 멤버를 선언하는 클래스를 나타내는 TypeDef 또는 TypeRef 또는 멤버를 선언하는 모듈 클래스또는 멤버를 나타내는 MethodDef를 나타내는 ModuleRef 토큰입니다.  
  
 `szMember`  
 【아웃】 멤버 이름에 대한 문자열 버퍼입니다.  
  
 `cchMember`  
 【인】 의 넓은 문자로 `szMember`요청된 크기입니다.  
  
 `pchMember`  
 【아웃】 의 넓은 문자로 `szMember`반환 된 크기입니다.  
  
 `ppvSibBlob`  
 【아웃】 멤버에 대한 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `pbSig`  
 【아웃】 의 바이트 크기입니다. `ppvSigBlob`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
