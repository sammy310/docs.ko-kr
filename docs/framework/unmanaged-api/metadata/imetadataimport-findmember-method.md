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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177278"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 메서드
지정된 <xref:System.Type> 이름과 메타데이터 서명이 있는 필드 또는 메서드에 대한 MemberDef 토큰에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 【인】 검색할 멤버를 둘러싸는 클래스 또는 인터페이스에 대한 TypeDef 토큰입니다. 이 값이 `mdTokenNil`이경우 전역 변수 또는 전역 함수에 대해 조회가 수행됩니다.  
  
 `szName`  
 【인】 검색할 구성원의 이름입니다.  
  
 `pvSigBlob`  
 【인】 멤버의 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `cbSigBlob`  
 【인】 의 바이트 크기입니다. `pvSigBlob`  
  
 `pmb`  
 【아웃】 일치하는 MemberDef 토큰에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 enclosing 클래스 또는 인터페이스 (),`td`해당 이름`szName`() 및 선택적으로`pvSigBlob`해당 서명 ()을 사용 하 여 멤버를 지정 합니다. 클래스 또는 인터페이스에 이름이 같은 구성원이 여러 개 있을 수 있습니다. 이 경우 멤버의 서명을 전달하여 고유한 일치 를 찾습니다.  
  
 전달된 서명은 서명이 특정 범위에 바인딩되어 있으므로 현재 범위에서 생성되어야 `FindMember` 합니다. 서명은 둘러싸는 클래스 또는 값 형식을 식별하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블에 대한 인덱스입니다. 현재 범위의 컨텍스트 외부에서 런타임 서명을 빌드하고 해당 서명을 `FindMember`에 입력에 대한 입력으로 사용할 수 없습니다.  
  
 `FindMember`클래스 또는 인터페이스에서 직접 정의된 멤버만 찾습니다. 상속된 멤버를 찾을 수 없습니다.  
  
> [!NOTE]
> `FindMember`은 도우미 방법입니다. [IMetaDataImport를 호출합니다::FindMethod;](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md) 해당 호출이 일치하는 `FindMember` 호출을 찾지 못하면 [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)를 호출합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
