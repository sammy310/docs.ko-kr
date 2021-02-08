---
description: '자세한 정보: IMetaDataEmit:: Set Setprops 메서드'
title: IMetaDataEmit::SetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 1e2786a21a1024f32328e36878a1a2427af54f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771888"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps 메서드

[IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md)에 대 한 이전 호출로 정의 된 사용 권한 집합의 메타 데이터 서명 기능을 설정 하거나 업데이트 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 데코레이팅 할 개체를 나타내는 메타 데이터 토큰입니다.  
  
 `dwAction`  
 진행 사용할 선언적 보안의 형식을 지정 하는 [CorDeclSecurity](cordeclsecurity-enumeration.md) 값입니다.  
  
 `pvPermission`  
 진행 권한 BLOB입니다.  
  
 `cbPermission`  
 진행 의 크기 (바이트)입니다 `pvPermission` .  
  
 `ppm`  
 제한이 `mdPermission` 업데이트 된 사용 권한을 나타내는 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
