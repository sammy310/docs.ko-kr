---
title: StrongNameGetPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6e9e5c199ad437290d7bf19d65b5f29a0abed5e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780106"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey 함수
개인/공개 키 쌍에서 공개 키를 가져옵니다. 암호화 서비스 공급자 (CSP) 내에서 키 컨테이너 이름으로 또는 원시 바이트 컬렉션으로 키 쌍을 제공할 수 있습니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szKeyContainer`  
 [in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다. 하는 경우 `pbKeyBlob` 이 null 이면 `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정 해야 합니다. 이 경우 `StrongNameGetPublicKey` 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.  
  
 경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.  
  
 키에는 1024 비트 adleman의 Rivest-Shamir (RSA) 키를 서명 해야 합니다. 다른 종류의 키이 이번에 지원 됩니다.  
  
 `pbKeyBlob`  
 [in] 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍이 win32 만들어진 형식을 `CryptExportKey` 함수입니다. 하는 경우 `pbKeyBlob` 가 null 이면 지정 된 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하도록 간주 됩니다.  
  
 `cbKeyBlob`  
 [in] 크기 (바이트)의 `pbKeyBlob`합니다.  
  
 `ppbPublicKeyBlob`  
 [out] 반환 된 공개 키 BLOB입니다. `ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다. 호출자에 게 사용 하 여 메모리를 해제 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.  
  
 `pcbPublicKeyBlob`  
 [out] 반환 된 공개 키 BLOB의 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 공개 키에 포함 된 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.  
  
 경우는 `StrongNameGetPublicKey` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [StrongNameGetPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [PublicKeyBlob 구조체](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
