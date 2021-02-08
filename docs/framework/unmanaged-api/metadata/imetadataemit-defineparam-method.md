---
description: IMetaDataEmit::D efineParam 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit::DefineParam 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 300de3183b329773a8e6813d6b92c6d049d63195
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784095"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam 메서드

지정 된 토큰이 참조 하는 메서드에 대해 지정 된 서명을 사용 하 여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대 한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `md`  
 진행 매개 변수가 정의 되 고 있는 메서드의 토큰입니다.  
  
 `ulParamSeq`  
 진행 매개 변수 시퀀스 번호입니다.  
  
 `szName`  
 진행 유니코드의 매개 변수 이름입니다.  
  
 `dwParamFlags`  
 진행 매개 변수에 대 한 플래그입니다. 값의 비트 마스크입니다 `CorParamAttr` .  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** 상수 값입니다.  
  
 `pValue`  
 진행 매개 변수에 대 한 상수 값입니다.  
  
 `cchValue`  
 진행 의 유니코드 문자 크기입니다 `pValue` .  
  
 `ppd`  
 제한이 `mdParamDef` 할당 된 토큰입니다.  
  
## <a name="remarks"></a>설명  

 매개 변수의 시퀀스 값은 `ulParamSeq` 1로 시작 합니다. 반환 값의 시퀀스 번호는 0입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
