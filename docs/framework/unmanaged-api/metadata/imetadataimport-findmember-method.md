---
title: IMetaDataImport::FindMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 777d7bf51db3e6984f30e31c46ac115301d13faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478975"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 메서드
토큰을 가져옵니다 memberdef 묶여 있는 메서드나 필드에 대 한 지정 된 <xref:System.Type> 지정 된 이름 및 메타 데이터 서명을 하 고 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 [in] 검색할 멤버를 포함 하는 인터페이스를 클래스에 대 한 TypeDef 토큰입니다. 이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 [in] 검색할 멤버의 이름입니다.  
  
 `pvSigBlob`  
 [in] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 [in] 크기 (바이트) `pvSigBlob`합니다.  
  
 `pmb`  
 [out] 일치 하는 MemberDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정할 수 (`td`), 해당 이름 (`szName`), 및 해당 서명 필요에 따라 (`pvSigBlob`). 클래스 또는 인터페이스에 이름이 같은 여러 멤버가 있을 수 있습니다. 이 경우 고유한 일치 항목을 찾을 멤버의 시그니처를 전달 합니다.  
  
 에 전달 된 서명을 `FindMember` 시그니처는 특정 범위에 바인딩되므로 현재 범위에서 생성 해야 합니다. 시그니처는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블의 인덱스입니다. 현재 범위의 컨텍스트 외부 런타임 시그니처를 만들어 없으며를 사용 하 여 해당 서명을 입력으로 `FindMember`입니다.  
  
 `FindMember` 클래스 또는 인터페이스에서 직접 정의 된 멤버를 찾습니다. 상속 된 멤버는 찾지 않습니다.  
  
> [!NOTE]
>  `FindMember` 도우미 메서드입니다. 호출한 [imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); 호출 하는 일치 하는 항목을 찾지 못하면 `FindMember` 호출 [imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
