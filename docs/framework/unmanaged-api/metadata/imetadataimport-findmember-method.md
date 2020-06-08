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
ms.openlocfilehash: fce4f3875fbdb110134d6b7f684eff40821f6bdd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503681"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 메서드
지정 된로 묶고 <xref:System.Type> 지정 된 이름과 메타 데이터 시그니처가 있는 필드 또는 메서드에 대 한 MemberDef 토큰에 대 한 포인터를 가져옵니다.  
  
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
 진행 검색할 멤버를 둘러싸는 클래스 또는 인터페이스의 TypeDef 토큰입니다. 이 값이 이면 `mdTokenNil` 전역 변수나 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 진행 검색할 멤버의 이름입니다.  
  
 `pvSigBlob`  
 진행 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 진행 의 크기 (바이트) `pvSigBlob` 입니다.  
  
 `pmb`  
 제한이 일치 하는 MemberDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스 ( `td` ), 이름 ( `szName` ) 및 선택적으로 시그니처 ()를 사용 하 여 멤버를 지정 `pvSigBlob` 합니다. 클래스 또는 인터페이스에 이름이 같은 멤버가 여러 개 있을 수 있습니다. 이 경우 멤버의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.  
  
 서명이 특정 범위에 바인딩되기 때문에에 전달 된 시그니처는 `FindMember` 현재 범위에서 생성 되어야 합니다. 시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다. 토큰은 로컬 TypeDef 테이블의 인덱스입니다. 현재 범위의 컨텍스트 외부에서 런타임 서명을 작성 하 고 해당 시그니처를 입력을 위한 입력으로 사용할 수 없습니다 `FindMember` .  
  
 `FindMember`클래스 또는 인터페이스에서 직접 정의 된 멤버만 찾습니다. 상속 된 멤버를 찾을 수 없습니다.  
  
> [!NOTE]
> `FindMember`는 도우미 메서드입니다. [IMetaDataImport:: FindMethod;를](imetadataimport-findmethod-method.md)호출 합니다. 해당 호출에서 일치 하는 항목을 찾지 못하면은 `FindMember` [IMetaDataImport:: findfield](imetadataimport-findfield-method.md)를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
