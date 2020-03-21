---
title: StrongNameTokenFromPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175059"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey 함수
공개 키를 나타내는 토큰을 가져옵니다. 강력한 이름 토큰은 공개 키의 단축된 형식입니다.  
  
 이 함수는 더 이상 사용되지 않습니다. 대신 [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbPublicKeyBlob`  
 【인】 강력한 이름 서명을 생성하는 데 사용되는 키 쌍의 공용 부분을 포함하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조입니다.  
  
 `cbPublicKeyBlob`  
 【인】 의 크기(바이트)입니다. `pbPublicKeyBlob`  
  
 `ppbStrongNameToken`  
 【아웃】 에 전달된 키에 해당하는 `pbPublicKeyBlob`강력한 이름 토큰입니다. 공통 언어 런타임은 토큰을 반환할 메모리를 할당합니다. 호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용하여 이 메모리를 해제해야 합니다.  
  
 `pcbStrongNameToken`  
 【아웃】 반환된 강력한 이름 토큰의 크기(바이트)입니다.  
  
## <a name="return-value"></a>Return Value  
 `true`성공적인 완료시; 그렇지 `false`않으면 .  
  
## <a name="remarks"></a>설명  
 강력한 이름 토큰은 메타데이터에 키 정보를 저장할 때 공간을 절약하는 데 사용되는 공개 키의 단축된 형식입니다. 특히 강력한 이름 토큰은 종속 어셈블리를 참조하기 위해 어셈블리 참조에 사용됩니다.  
  
 `StrongNameTokenFromPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** mscoree.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameTokenFromPublicKey 메서드](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey 메서드](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob 구조체](publickeyblob-structure.md)
