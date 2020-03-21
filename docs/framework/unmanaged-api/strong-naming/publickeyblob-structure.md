---
title: PublicKeyBlob 구조체
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176957"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob 구조체
이진 형식으로 공개/개인 키 쌍의 공개 키를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`SigAlgId`|공개 키의 `ALG_ID`시그니처 알고리즘(WinCrypt.h에 정의된 형식)의 식별자입니다.|  
|`HashAlgId`|공개 키의 해시 알고리즘(WinCrypt.h에 `ALG_ID`정의된 형식)의 식별자입니다.|  
|`cbPublicKey`|바이트로 구성된 키의 길이입니다.|  
|`PublicKey`|CryptoAPI에서 반환되는 형식의 키 값을 포함하는 가변 길이 바이트 배열입니다.|  
  
## <a name="remarks"></a>설명  
 이 `PublicKeyBlob` 구조는 [StrongNameGetPublicKey,](strongnamegetpublickey-function.md) [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)및 기타 강력한 이름 함수에서 공개/개인 키 쌍의 공개 키를 나타내는 데 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameGetPublicKey 함수](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration 함수](strongnamesignaturegeneration-function.md)
