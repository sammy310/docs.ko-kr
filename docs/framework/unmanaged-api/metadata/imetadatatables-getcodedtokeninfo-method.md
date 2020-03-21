---
title: IMetaDataTables::GetCodedTokenInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177146"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a>IMetaDataTables::GetCodedTokenInfo 메서드
지정된 행 인덱스와 연결된 토큰 배열에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ixCdTkn`  
 【인】 반환할 코딩된 토큰의 종류입니다.  
  
 `pcTokens`  
 【아웃】 `ppTokens`의 길이에 대한 포인터입니다.  
  
 `ppTokens`  
 【아웃】 반환된 토큰 목록을 포함하는 배열에 대한 포인터입니다.  
  
 `ppName`  
 【아웃】 에서 `ixCdTkn`토큰 이름에 대한 포인터에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
