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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140612"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob 구조체
공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`SigAlgId`|공개 키의 Wincrypt.h에 정의 된 형식 `ALG_ID`의 서명 알고리즘에 대 한 식별자입니다.|  
|`HashAlgId`|공개 키의 Wincrypt.h에 정의 된 대로 형식 `ALG_ID`의 해시 알고리즘에 대 한 식별자입니다.|  
|`cbPublicKey`|키의 길이 (바이트)입니다.|  
|`PublicKey`|CryptoAPI에서 반환 된 형식의 키 값을 포함 하는 가변 길이 바이트 배열입니다.|  
  
## <a name="remarks"></a>주의  
 `PublicKeyBlob` 구조체는 [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)및 기타 강력한 이름 함수에서 공개/개인 키 쌍의 공개 키를 나타내는 데 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameGetPublicKey 함수](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration 함수](strongnamesignaturegeneration-function.md)
