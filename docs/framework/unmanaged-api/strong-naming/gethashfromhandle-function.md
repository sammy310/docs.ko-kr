---
title: GetHashFromHandle 함수
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48dd987896536006fe81bc01528cadb507123e27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203407"
---
# <a name="gethashfromhandle-function"></a>GetHashFromHandle 함수
지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Gethashfromhandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hFile`  
 [in] 해시 될 파일의 핸들입니다.  
  
 `piHashAlg`  
 [out에서] 해시 알고리즘을 지정 하는 상수입니다. 기본 알고리즘에 0을 사용 합니다.  
  
 `pbHash`  
 [out] 반환 된 해시 버퍼입니다.  
  
 `cchHash`  
 [in] 요청 된 최대 크기인 `pbHash`합니다.  
  
 `pchHash`  
 [out] 반환 된 바이트의 크기, `pbHash`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [GetHashFromHandle 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
