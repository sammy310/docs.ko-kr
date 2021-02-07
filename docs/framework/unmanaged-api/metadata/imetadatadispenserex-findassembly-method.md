---
description: '자세히 알아보기: IMetaDataDispenserEx:: FindAssembly 메서드'
title: IMetaDataDispenserEx::FindAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 6bed016e9235281b42f5a3231ef2aff284b6cc3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753603"
---
# <a name="imetadatadispenserexfindassembly-method"></a>IMetaDataDispenserEx::FindAssembly 메서드

이 메서드가 구현되지 않은 경우 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szAppBase`  
 진행 사용 되지 않습니다.  
  
 `szPrivateBin`  
 진행 사용 되지 않습니다.  
  
 `szGlobalBin`  
 진행 사용 되지 않습니다.  
  
 `szAssemblyName`  
 진행 찾을 어셈블리입니다.  
  
 `szName`  
 제한이 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 진행 의 크기 (바이트)입니다 `szName` .  
  
 `pcName`  
 제한이 에서 실제로 반환 되는 문자 수입니다 `szName` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
