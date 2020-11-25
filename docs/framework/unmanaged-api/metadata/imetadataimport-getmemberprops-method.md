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
ms.openlocfilehash: f01d65a339c77e6af3e768c620f17ef0190c1e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733224"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps 메서드

지정 된 <xref:System.Type> 메타 데이터 토큰에서 참조 하는 멤버의 이름, 이진 서명 및 상대 가상 주소를 포함 하 여, 지정 된 멤버 정의에 대 한 메타 데이터에 저장 된 정보를 가져옵니다. 이는 간단한 도우미 메서드입니다. *mb* 가 MethodDef 인 경우 **getmethodprops** 이 호출 됩니다. *mb* 가 FieldDef 인 경우 **getfieldprops** 가 호출 됩니다. 자세한 내용은 다음 방법을 참조 하세요.
  
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
 진행 연결 된 메타 데이터를 가져올 멤버를 참조 하는 토큰입니다.  
  
 `pClass`  
 제한이 멤버의 클래스를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `szMember`  
 제한이 멤버의 이름입니다.  
  
 `cchMember`  
 진행 버퍼의 와이드 문자 크기 `szMember` 입니다.  
  
 `pchMember`  
 제한이 반환 된 이름의 와이드 문자 크기입니다.  
  
 `pdwAttr`  
 제한이 멤버에 적용 된 모든 플래그 값입니다.  
  
 `ppvSigBlob`  
 제한이 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pcbSigBlob`  
 제한이 의 크기 (바이트) `ppvSigBlob` 입니다.  
  
 `pulCodeRVA`  
 제한이 멤버의 상대 가상 주소에 대 한 포인터입니다.  
  
 `pdwImplFlags`  
 제한이 멤버와 연결 된 모든 메서드 구현 플래그입니다.  
  
 `pdwCPlusTypeFlag`  
 제한이 을 표시 하는 플래그입니다 <xref:System.ValueType> . 값 중 하나입니다 `ELEMENT_TYPE_*` .
  
 `ppValue`  
 제한이 이 멤버에서 반환 하는 상수 문자열 값입니다.  
  
 `pcchValue`  
 제한이 의 문자 크기 `ppValue` 이거나, `ppValue` 가 문자열을 포함 하지 않는 경우 0입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
