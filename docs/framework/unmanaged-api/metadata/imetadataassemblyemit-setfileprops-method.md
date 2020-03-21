---
title: IMetaDataAssemblyEmit::SetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176034"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>IMetaDataAssemblyEmit::SetFileProps 메서드
지정된 `File` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `file`  
 【인】 수정할 `File` 메타데이터 구조를 지정하는 메타데이터 토큰입니다.  
  
 `pbHashValue`  
 【인】 파일과 연결된 해시 데이터에 대한 포인터입니다.  
  
 `cbHashValue`  
 【인】 의 바이트 크기입니다. `pbHashValue`  
  
 `dwFileFlags`  
 【인】 파일의 다양한 특성을 지정하는 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 `File` 메타데이터 구조를 만들려면 [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) 메서드를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
