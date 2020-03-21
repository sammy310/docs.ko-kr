---
title: IMetaDataImport::GetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175345"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>IMetaDataImport::GetPermissionSetProps 메서드
지정된 권한 토큰으로 <xref:System.Security.PermissionSet?displayProperty=nameWithType> 표시되는 메타데이터와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pm`  
 【인】 메타데이터 속성을 가져오는 권한 집합을 나타내는 권한 메타데이터 토큰입니다.  
  
 `pdwAction`  
 【아웃】 사용 권한 집합에 대한 포인터입니다.  
  
 `ppvPermission`  
 【아웃】 사용 권한 집합의 이진 메타데이터 시그니처에 대한 포인터입니다.  
  
 `pcbPermission`  
 【아웃】 의 바이트 크기입니다. `ppvPermission`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Security.PermissionSet>
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
