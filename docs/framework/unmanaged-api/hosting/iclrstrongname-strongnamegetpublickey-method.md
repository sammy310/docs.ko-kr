---
title: ICLRStrongName::StrongNameGetPublicKey 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: 5a20bde64830617090c92afe5fae3a603cf9103b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763134"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey 메서드
공개/개인 키 쌍에서 공개 키를 가져옵니다. 키 쌍은 CSP (암호화 서비스 공급자) 내에서 키 컨테이너 이름으로 제공 되거나 원시 바이트 컬렉션으로 제공 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szKeyContainer`  
 진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다. 가 null 인 경우는 `pbKeyBlob` `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정 해야 합니다. 이 경우 [ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) 메서드는 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.  
  
 `pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.  
  
 키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다. 지금은 다른 유형의 키를 지원 하지 않습니다.  
  
 `pbKeyBlob`  
 진행 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍은 Win32 함수에서 만든 형식입니다 `CryptExportKey` . 가 null 인 경우에 `pbKeyBlob` 지정 된 키 컨테이너는 `szKeyContainer` 키 쌍을 포함 하는 것으로 간주 됩니다.  
  
 `cbKeyBlob`  
 진행 의 크기 (바이트)입니다 `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 제한이 반환 된 공개 키 BLOB입니다. `ppbPublicKeyBlob`매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 됩니다. 호출자는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여 메모리를 해제 해야 합니다.  
  
 `pcbPublicKeyBlob`  
 제한이 반환 된 공개 키 BLOB의 크기입니다.  
  
## <a name="return-value"></a>Return Value  
 `S_OK`메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="remarks"></a>설명  
 공개 키가 [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) 구조에 포함 되어 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameTokenFromPublicKey 메서드](iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob 구조체](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
