---
title: ICLRStrongName::GetHashFromFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176372"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>ICLRStrongName::GetHashFromFileW 메서드
유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 【인】 해시할 파일의 유니코드 이름입니다.  
  
 `piHashAlg`  
 【인, 아웃】 해시를 생성할 때 사용할 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에 의해 정의된 알고리즘입니다. 0으로 설정된 경우 `piHashAlg` 기본 알고리즘 CALG_SHA-1이 사용됩니다.  
  
 `pbHash`  
 【아웃】 생성된 해시를 포함하는 바이트 배열입니다.  
  
 `cchHash`  
 【인】 을 가리키는 버퍼의 최대 `pbHash`크기입니다.  
  
 `pchHash`  
 【아웃】 의 크기(바이트)입니다. `pbHash`  
  
## <a name="return-value"></a>Return Value  
 `S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="remarks"></a>설명  
 이 메서드는 [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) 메서드와 동일 하지만 파일 이름 사양ANSI 대신 유니코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 메타호스트  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetHashFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
