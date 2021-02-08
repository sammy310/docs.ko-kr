---
description: '자세히 알아보기: IMetaDataEmit:: SetParamProps 메서드'
title: IMetaDataEmit::SetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 35e839b05b3671c6c09f315ac636971c386e766e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772026"
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps 메서드

[IMetaDataEmit::D efineParam](imetadataemit-defineparam-method.md)에 대 한 이전 호출로 정의 된 메서드 매개 변수의 기능을 설정 하거나 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pd`  
 진행 대상 매개 변수에 대 한 토큰입니다.  
  
 `szName`  
 진행 유니코드의 매개 변수 이름입니다.  
  
 `dwParamFlags`  
 진행 매개 변수에 대 한 플래그입니다.  
  
 `dwCPlusTypeFlag`  
 진행 상수 값에 대 한 ELEMENT_TYPE_ *입니다.  
  
 `pValue`  
 진행 매개 변수에 대 한 상수 값입니다.  
  
 `cchValue`  
 진행 의 (유니코드) 문자 크기입니다 `pValue` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
