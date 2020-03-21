---
title: IMetaDataImport::FindMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175423"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef 메서드
지정된 <xref:System.Type> 이름과 메타데이터 서명이 있는 멤버 참조에 대한 MemberRef 토큰에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 검색할 멤버 참조를 둘러싸는 클래스 또는 인터페이스에 대한 TypeRef 토큰입니다. 이 값이 `mdTokenNil`이경우 전역 변수 또는 전역 함수 참조에 대해 조회가 수행됩니다.  
  
 `szName`  
 【인】 검색할 멤버 참조의 이름입니다.  
  
 `pvSigBlob`  
 【인】 멤버 참조의 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `cbSigBlob`  
 【인】 의 바이트 크기입니다. `pvSigBlob`  
  
 `pmr`  
 【아웃】 일치하는 MemberRef 토큰에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 enclosing 클래스 또는 인터페이스 (),`td`해당 이름`szName`() 및 선택적으로`pvSigBlob`해당 서명 ()을 사용 하 여 멤버를 지정 합니다.  
  
 전달된 서명은 서명이 특정 범위에 바인딩되어 있으므로 현재 범위에서 생성되어야 `FindMemberRef` 합니다. 서명은 둘러싸는 클래스 또는 값 형식을 식별하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블에 대한 인덱스입니다. 현재 범위의 컨텍스트 외부에서 런타임 서명을 작성하고 해당 서명을 `FindMemberRef`에 대한 입력으로 사용할 수 없습니다.  
  
 `FindMemberRef`클래스 또는 인터페이스에서 직접 정의된 멤버 참조만 찾습니다. 상속된 멤버 참조를 찾을 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
