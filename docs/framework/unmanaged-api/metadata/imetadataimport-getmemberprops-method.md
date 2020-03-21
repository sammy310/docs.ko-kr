---
title: IMetaDataImport::GetMemberProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177225"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps 메서드
지정된 메타데이터 토큰에서 참조하는 멤버의 이름, 이진 서명 및 상대 <xref:System.Type> 가상 주소를 포함하여 지정된 멤버 정의에 대한 메타데이터에 저장된 정보를 가져옵니다. 이것은 간단한 도우미 메서드: *mb는* MethodDef 인 경우 **GetMethodProps** 가 호출 됩니다. *mb가* 필드데프인 경우 **GetFieldProps가 호출됩니다.** 자세한 내용은 다음 다른 방법을 참조하십시오.
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mb`  
 【인】 관련 메타데이터를 가져오는 멤버를 참조하는 토큰입니다.  
  
 `pClass`  
 【아웃】 멤버의 클래스를 나타내는 메타데이터 토큰에 대한 포인터입니다.  
  
 `szMember`  
 【아웃】 멤버의 이름입니다.  
  
 `cchMember`  
 【인】 버퍼의 넓은 문자의 `szMember` 크기입니다.  
  
 `pchMember`  
 【아웃】 반환 된 이름의 넓은 문자의 크기입니다.  
  
 `pdwAttr`  
 【아웃】 멤버에 적용된 모든 플래그 값입니다.  
  
 `ppvSigBlob`  
 【아웃】 멤버의 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `pcbSigBlob`  
 【아웃】 의 바이트 크기입니다. `ppvSigBlob`  
  
 `pulCodeRVA`  
 【아웃】 멤버의 상대 가상 주소에 대한 포인터입니다.  
  
 `pdwImplFlags`  
 【아웃】 멤버와 연결된 메서드 구현 플래그입니다.  
  
 `pdwCPlusTypeFlag`  
 【아웃】 을 표시하는 플래그입니다. <xref:System.ValueType> 그것은 `ELEMENT_TYPE_*` 값 중 하나입니다.
  
 `ppValue`  
 【아웃】 이 멤버에서 반환되는 상수 문자열 값입니다.  
  
 `pcchValue`  
 【아웃】 문자열을 보유하지 `ppValue`않는 경우 `ppValue` 의 문자 크기 또는 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
