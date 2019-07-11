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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ba3fd634b108c996e848f48000ffcd0600b00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774591"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="9f760-102">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="9f760-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="9f760-103">공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f760-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f760-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="9f760-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9f760-105">Members</span></span>  
  
|<span data-ttu-id="9f760-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9f760-106">Member</span></span>|<span data-ttu-id="9f760-107">Description</span><span class="sxs-lookup"><span data-stu-id="9f760-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="9f760-108">서명 알고리즘에 대 한 식별자 (형식 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="9f760-109">해시 알고리즘에 대 한 식별자 (형식의 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="9f760-110">바이트의 키 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="9f760-111">CryptoAPI에 의해 반환 된 형식으로 키 값을 포함 하는 가변 길이 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f760-112">설명</span><span class="sxs-lookup"><span data-stu-id="9f760-112">Remarks</span></span>  
 <span data-ttu-id="9f760-113">합니다 `PublicKeyBlob` 구조체를 사용 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)를 [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), 함수와 다른 강력한 이름 공개/개인 키 쌍의 공개 키를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f760-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f760-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f760-114">Requirements</span></span>  
 <span data-ttu-id="9f760-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f760-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f760-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9f760-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9f760-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9f760-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f760-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f760-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f760-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f760-119">See also</span></span>

- [<span data-ttu-id="9f760-120">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="9f760-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="9f760-121">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="9f760-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
