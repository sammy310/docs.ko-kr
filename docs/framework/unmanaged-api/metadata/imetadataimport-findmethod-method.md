---
title: IMetaDataImport::FindMethod 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437889"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 메서드
지정 된 <xref:System.Type>로 묶고 지정 된 이름과 메타 데이터 서명을 가진 메서드에 대 한 MethodDef 토큰에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 진행 검색할 멤버를 둘러싸는 형식 (클래스 또는 인터페이스)에 대 한 `mdTypeDef` 토큰입니다. 이 값이 `mdTokenNil`되 면 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 진행 검색할 메서드의 이름입니다.  
  
 `pvSigBlob`  
 진행 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 진행 `pvSigBlob`의 크기 (바이트)입니다.  
  
 `pmb`  
 제한이 일치 하는 MethodDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스 (`td`), 이름 (`szName`) 및 선택적으로 시그니처 (`pvSigBlob`)를 사용 하 여 메서드를 지정 합니다. 클래스 또는 인터페이스에 동일한 이름을 가진 메서드가 여러 개 있을 수 있습니다. 이 경우 메서드의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.  
  
 서명이 특정 범위에 바인딩되므로 현재 범위에서 `FindMethod` 전달 된 서명이 생성 되어야 합니다. 시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다. 토큰은 로컬 TypeDef 테이블의 인덱스입니다. 현재 범위의 컨텍스트 외부에서 런타임 시그니처를 작성 하 고 해당 서명을 `FindMethod`입력의 입력으로 사용할 수 없습니다.  
  
 `FindMethod`은 클래스 또는 인터페이스에서 직접 정의 된 메서드만 찾습니다. 상속 된 메서드를 찾을 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
