---
description: '자세히 알아보기: IMetaDataImport:: FindMethod 메서드'
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
ms.openlocfilehash: 0d2866554fcb4dcf3984310e4da24d501f1fc7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803557"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 메서드

지정 된로 묶여 <xref:System.Type> 있고 지정 된 이름과 메타 데이터 시그니처가 있는 메서드의 MethodDef 토큰에 대 한 포인터를 가져옵니다.  
  
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
 진행 `mdTypeDef` 검색할 멤버를 둘러싸는 형식 (클래스 또는 인터페이스)에 대 한 토큰입니다. 이 값이 이면 `mdTokenNil` 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 진행 검색할 메서드의 이름입니다.  
  
 `pvSigBlob`  
 진행 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 진행 의 크기 (바이트) `pvSigBlob` 입니다.  
  
 `pmb`  
 제한이 일치 하는 MethodDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 바깥쪽 클래스 또는 인터페이스 ( `td` ), 이름 ( `szName` ) 및 선택적으로 시그니처 ()를 사용 하 여 메서드를 지정 `pvSigBlob` 합니다. 클래스 또는 인터페이스에 동일한 이름을 가진 메서드가 여러 개 있을 수 있습니다. 이 경우 메서드의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.  
  
 서명이 특정 범위에 바인딩되기 때문에에 전달 된 시그니처는 `FindMethod` 현재 범위에서 생성 되어야 합니다. 시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다. 토큰은 로컬 TypeDef 테이블의 인덱스입니다. 현재 범위의 컨텍스트 외부에서 런타임 서명을 작성 하 고 해당 시그니처를 입력을 위한 입력으로 사용할 수 없습니다 `FindMethod` .  
  
 `FindMethod` 클래스 또는 인터페이스에서 직접 정의 된 메서드만 찾습니다. 상속 된 메서드를 찾을 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
