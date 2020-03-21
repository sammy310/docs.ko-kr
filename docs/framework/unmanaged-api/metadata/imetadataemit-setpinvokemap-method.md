---
title: IMetaDataEmit::SetPinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175592"
---
# <a name="imetadataemitsetpinvokemap-method"></a>IMetaDataEmit::SetPinvokeMap 메서드
[IMetaDataEmit::DefinePinvokeMap에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)대한 사전 호출에서 정의한 대로 메서드의 PInvoke 서명의 기능을 설정하거나 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 【인】 `mdToken` 매핑 정보가 적용되는  
  
 `dwMappingFlags`  
 【인】 PInvoke가 매핑을 수행하는 데 사용하는 플래그입니다. 이것은 값의 `CorPinvokeMap` 비트 마스크입니다.  
  
 `szImportName`  
 【인】 네이티브 DLL에서 대상 내보내기의 이름입니다.  
  
 `mrImportDLL`  
 【인】 관리되지 않는 대상 DLL에 대한 `mdModuleRef` 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
