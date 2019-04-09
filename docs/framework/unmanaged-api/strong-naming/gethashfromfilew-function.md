---
title: GetHashFromFileW 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134617"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW 함수
유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 유니코드 해시 파일의 이름입니다.  
  
 `piHashAlg`  
 [out에서] 해시를 생성할 때 사용할 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다. 경우 `piHashAlg` CALG_SHA-1은 사용 하는 기본 알고리즘 0으로 설정 됩니다.  
  
 `pbHash`  
 [out] 생성된 된 해시를 포함 하는 바이트 배열입니다.  
  
 `cchHash`  
 [in] 가리키는 버퍼의 최대 크기 `pbHash`합니다.  
  
 `pchHash`  
 [out] 크기 (바이트)의 `pbHash`합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 동일 [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)파일 이름 사양이 ANSI 대신 유니코드는 점을 제외 하 고, 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [GetHashFromFileW 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
